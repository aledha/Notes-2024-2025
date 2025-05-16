In this section, we introduce some methods of numerically approximating solutions to ordinary differential equations (ODEs). Although this section presents a general framework for solving ODEs, we will need to discuss some aspects of the specific ODE system that will be introduced in full in \autoref{sec:cell models}.

An ordinary differential equation (ODE) is a differential equation that is dependent on only one independent variable. Take, for example, the initial value problem (IVP) $$
\begin{equation}
%\label{eq:model ode}
\frac{\text{d}\mathbf{s}}{\text{d}t} =\mathbf{f}(\mathbf{s},t), \qquad \mathbf{s}(t_{0})=\mathbf{s}_{0}.
\end{equation}
$$
Here, $\mathbf{s}_{0}\in \mathbb{R}^d$ is the given initial value, $\mathbf{s} \in \mathbb{R}^d$ is the unknown function of $t$ that we wish to solve for, and $\mathbf{f}:\mathbb{R}^d \times[t_{0},\infty)\to \mathbb{R}^d$ is a known function. The ODE \eqref{eq:model ode} is of \emph{first-order}. That is, it only depends on the first derivative with respect to $t$, and not on higher derivatives such as $\frac{\text{d}^2\mathbf{s}}{\text{d}t^2}$. All ODEs discussed in this thesis will be of first-order.

In a majority of cases, it is impossible to find an analytical solution of \eqref{eq:model ode}, so we turn to numerically approximating the solution. There are a wide range of schemes to numerically approximate ODEs, but we start by introducing the simpler schemes. Let $t_{n}=n \Delta t$ be a time discretization for some time step $\Delta t$, and assume that we know the solution at $\mathbf{s}_{n}=\mathbf{s}(t_{n})$. Then, to find the solution $\mathbf{s}_{n+1}$, we can integrate both sides of \eqref{eq:model ode} over $t \in[t_{n},t_{n+1}]$: $$
\begin{equation}
%\label{eq:model ode int}
\int_{t_{n}}^{t_{n+1}}\frac{\text{d}\mathbf{s}}{\text{d}t} \,\text{d} t=\int_{t_{n}}^{t_{n+1}}\mathbf{f}(\mathbf{s},t)\,\text{d} t.
\end{equation}
$$
We use the fundamental theorem of calculus on the left-hand side of \eqref{eq:model ode int} to reduce it to $$
\begin{align}
\nonumber 
\mathbf{s}_{n+1}-\mathbf{s}_{n} & =\int_{t_{n}}^{t_{n+1}}\mathbf{f}(\mathbf{s},t)\,\text{d} t \\
%\label{eq:ode approx}
\mathbf{s}_{n+1} & =\mathbf{s}_{n} +\int_{t_{n}}^{t_{n+1}}\mathbf{f}(\mathbf{s},t)\,\text{d} t.
\end{align}
$$
Then, we numerically approximate the integral on the right-hand side of \eqref{eq:ode approx}. The simplest approach is a left endpoint approximation of the integral, leading to $$
\begin{equation}
%\label{eq:fwd euler}
\mathbf{s}_{n+1}  \approx \mathbf{s}_{n} +\Delta t\mathbf{f}(\mathbf{s}_{n},t_{n}),
\end{equation}
$$
which is called the \emph{forward Euler method} (FE). This is an \emph{explicit scheme}, meaning that we have an explicit formula for $\mathbf{s}_{n+1}$, which is very easy to implement and numerically cheap to compute. It can be shown \cite{computing} that the forward Euler method is first order accurate in time. That is, the error after $n$ time steps is proportional to $\Delta t$.

One relevant issue with the FE method is its stability properties. The ODE systems we consider in this thesis are what is known as \emph{stiff}. The stiffness of an ODE is an emergent property that is difficult to define. The eigenvalues of the Jacobian of \eqref{eq:model ode} $\mathbf{J}=\frac{ \partial \mathbf{f} }{ \partial \mathbf{s} }(\mathbf{s},t)$ are related to the stiffness. Typically, large negative eigenvalues correlate with the stiffness of the problem \cite{marsh2012}. Some ODE solvers are more susceptible to stiffness, in particular the FE method. Attempting to solve a stiff ODE with one of these susceptible solvers leads to rapid oscillations in the solution if the step size $\Delta t$ is not small enough. 

A method that is more resilient to stiffness is the \emph{backwards Euler method} (BE), which can be obtained by using a right endpoint approximation of the integral in \eqref{eq:ode approx}: $$
\begin{equation}
%\label{eq:bwd euler}
\mathbf{s}_{n+1}  \approx \mathbf{s}_{n} +\Delta t\mathbf{f}(\mathbf{s}_{n+1},t_{n+1}).
\end{equation}
$$
It can be shown \cite{computing}\todo{find source that proves} that the this method is also first order accurate in time. The BE method is an \emph{implicit scheme}, meaning that we cannot write an explicit formula for $\mathbf{s}_{n+1}$, since it appears in the right-hand side function $\mathbf{f}$. Consequentially, we must solve a system of equations. 

For the ODE system introduced in \autoref{sec:cell models}, the dimension of the unknown function $\mathbf{s}$ will be $d=19$ and the right-hand side function $\mathbf{f}$ will be nonlinear. Using the BE method on the system in \autoref{sec:cell models} requires us to solve a system of $18$ nonlinear equations at every time step. This is both hard to implement and computationally costly.

Both the FE method and the BE method are special cases of what is known as the \emph{$\theta$-method}: $$
\begin{equation}
\mathbf{s}_{n+1}\approx \mathbf{s}_{n}+\theta \Delta t\mathbf{f}(\mathbf{s}_{n},t_{n})+(1-\theta)\Delta t\mathbf{f}(\mathbf{s}_{n+1},t_{n+1}).
\end{equation}
$$
When $\theta=1$ we get the FE method, when $\theta=0$ we get the BE method, and when $\theta=\frac{1}{2}$ we get the \emph{Crank-Nicolson scheme} (CN). The CN scheme is second order accurate in time \cite{}, in contrast to the Euler methods. It is also implicit, making it equally hard to implement and numerically costly as the BE method. 

To avoid the instability of the FE method and the numerical cost of the BE (and CN) method, we will use the \emph{Rush-Larsen} (RL) method. This method takes advantage of the \emph{quasi-linearity} of a subset of the variables in $\mathbf{s}$. Let $s_{i}$ be the $i$-th component of $\mathbf{s}$. These are the gating variables, which are controlled by ODEs of the form
$$
\begin{equation} 
%\label{eq:intro gating}
    \frac{\text{d}s_{i}}{\text{d}t} =\alpha_{i}(v)(1-s_{i})-\beta_{i}(v)s_{i},
\end{equation}
$$
where $s_{i}$ are the gating variables, $\alpha_{i}(v)$ is the rate of opening of ion channels, $\beta_{i}(v)$ is the rate of closing of ion channels, and $v$ is the transmembrane voltage (which is also one of the variables in $\mathbf{s}$), and $G$ is the set of indices of the gating variables. As mentioned, this equation will be explained in more detail in \autoref{sec:cell models}. The importance for the discussion in this chapter is that while $\alpha_{i}(v)$ and $\beta_{i}(v)$ are nonlinear functions of $v$, \eqref{eq:intro gating} is linear in $s_{i}$. We call this property quasi-linearity. We rewrite \eqref{eq:intro gating} to \cite{marsh2012}$$
\begin{equation}
%\label{eq:quasilinear}
	\frac{\text{d}s_{i}}{\text{d}t} =\frac{s_{\infty,i}-s_{i}}{\tau_{i}},
\end{equation}
$$
where $s_{\infty,i}(v)=\frac{\alpha_{i}(v)}{\alpha_{i}(v)+\beta_{i}(v)}$ and $\tau_{i}(v)=\frac{1}{\alpha_{i}(v)+\beta_{i}(v)}$. The idea of the RL method is to assume that the transmembrane voltage $v=v_{n}$ is constant over each time step, such that $s_{\infty,i}=s_{\infty,i}(v_{n})$ and $\tau_{i}=\tau_{i}(v_{n})$ are constants and we can treat \eqref{eq:quasilinear} as a linear ODE with the exact solution \cite{marsh2012} $$
\begin{equation}
	%\label{eq:RL}
	s_{n+1,i}=s_{\infty,i}+(s_{n,i}-s_{\infty,i})e^{ -\Delta t/\tau_{i} },
\end{equation}
$$
where $s_{n,i}=s_{i}(t_{n})$.

The RL method provides an explicit formula for the gating variables $s_{n+1,i}$, making it easy to implement and computationally cheap. The RL method uses \eqref{eq:RL} for the gating variables and the simpler FE for all non-gating variables. For reference, the cell model we consider in \autoref{sec:cell models} contains 19 variables, where 12 of those are gating variables.

The \emph{generalized Rush-Larsen} (GRL) method is similar to the RL method. The GRL method decouples and linearizes the ODE system \eqref{eq:model ode} around a point $\mathbf{s}=\mathbf{s}_{n}$ and time $t=t_{n}$ \cite{marsh2012} to get the expression$$
\begin{equation}
%\label{eq:GRL}
	\frac{\text{d}s_{i}}{\text{d}t} =f_{i}(\mathbf{s}_{n})+\frac{ \partial  }{ \partial s_{i} } f_{i}(\mathbf{s}_{n})(s_{i}-s_{n,i}), \qquad \text{for }i=0,\dots,d-1.
\end{equation}
$$
where $f_{i}$ is the $i$-th component $\mathbf{f}$. The exact solution of \eqref{eq:GRL} can be found as \cite{marsh2012}$$
\begin{equation}
%\label{eq:GRL np1}
	s_{n+1,i}=s_{n,i}+ \frac{a}{b}(e^{ b(\Delta t) }-1),
\end{equation}
$$
where $a=f_{i}(\mathbf{s}_{n})$ and $b=\frac{ \partial f_{i}(\mathbf{s}_{n}) }{ \partial s_{i} }$. The GRL method uses \eqref{eq:GRL np1} on every component on $\mathbf{s}$, in contrast to the RL method, which uses FE for non-gating variables and \eqref{eq:RL} for the gating variables. Notice that \eqref{eq:GRL} reduces to \eqref{eq:RL} for the gating variables, due to their quasi-linearity.\todo{show?}



