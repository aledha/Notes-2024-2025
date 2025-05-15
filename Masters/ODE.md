An ordinary differential equation (ODE) is a differential equation that is dependent on only one independent variable. Take, for example, the initial value problem (IVP) $$
\begin{equation}
%\label{eq:model ode}
\frac{\text{d}y}{\text{d}t} =f(y,t), \qquad y(t_{0})=y_{0}.
\end{equation}
$$
Here, $y_{0}\in \mathbb{R}^d$ is the given initial value, $y \in \mathbb{R}^d$ is the unknown function of $t$ that we wish to solve for, and $f:\mathbb{R}^d \times[t_{0},\infty)\to \mathbb{R}^d$ is a known function. The ODE \eqref{eq:model ode} is of \emph{first-order}. That is, it only depends on the first derivative with respect to $t$, and not on higher derivatives such as $\frac{\text{d}^2y}{\text{d}t^2}$. All ODEs discussed in this paper will be of first-order.

In a majority of cases, it is impossible to find an analytical solution of \eqref{eq:model ode}, so we turn to numerically approximating the solution. There are a wide range of schemes to numerically approximate ODEs, but we start by introducing the simpler schemes. Let $t_{n}=n \Delta t$ be a time discretization for some time step $\Delta t$, and assume that we know the solution at $y_{n}=y(t_{n})$. Then, to find the solution $y_{n+1}$, we can integrate both sides of \eqref{eq:model ode} over $t \in[t_{n},t_{n+1}]$: $$
\begin{equation}
%\label{eq:model ode int}
\int_{t_{n}}^{t_{n+1}}\frac{\text{d}y}{\text{d}t} \,\text{d} t=\int_{t_{n}}^{t_{n+1}}f(y,t)\,\text{d} t.
\end{equation}
$$
We use the fundamental theorem of calculus on the left-hand side of \eqref{eq:model ode int} to reduce it to $$
\begin{align}
\nonumber 
y_{n+1}-y_{n} & =\int_{t_{n}}^{t_{n+1}}f(y,t)\,\text{d} t \\
%\label{eq:ode approx}
y_{n+1} & =y_{n} +\int_{t_{n}}^{t_{n+1}}f(y,t)\,\text{d} t.
\end{align}
$$
Then, we numerically approximate the integral on the right-hand side of \eqref{eq:ode approx}. The simplest approach is a left endpoint approximation of the integral, leading to $$
\begin{equation}
%\label{eq:fwd euler}
y_{n+1}  \approx y_{n} +\Delta tf(y_{n},t_{n}),
\end{equation}
$$
which is called the \emph{forward Euler method}. This is an \emph{explicit scheme}, meaning that we have an explicit formula for $y_{n+1}$, which is very easy to implement and numerically cheap to compute. It can be shown \cite{computing} that the forward Euler method is first order accurate in time. That is, the error after $n$ time steps is proportional to $\Delta t$.

One relevant issue with the forward Euler method is its stability properties. The ODE systems we consider in this paper are what is known as \emph{stiff}. The stiffness of an ODE is an emergent property that is difficult to define. In the case of homogeneous linear equations, one can relate the stiffness to eigenvalues of the equation, see, e.g., \cite{computing}. Some ODE solvers are more susceptible to stiffness, in particular the forward Euler method. Attempting to solve a stiff ODE with one of these susceptible solvers leads to rapid oscillations in the solution if the step size $\Delta t$ is not small enough. 

A method that is more resilient to stiffness is the \emph{backwards Euler method}, which can be obtained by using a right endpoint approximation of the integral in \eqref{eq:ode approx}: $$
\begin{equation}
%\label{eq:bwd euler}
y_{n+1}  \approx y_{n} +\Delta tf(y_{n+1},t_{n+1}).
\end{equation}
$$
It can be shown \cite{computing}\todo{find source that proves} that the this method is also first order accurate in time. The backwards Euler method is an \emph{implicit scheme}, meaning that we cannot write an explicit formula for $y_{n+1}$, since it appears in the right-hand side function $f$. Consequentially, we must solve a system of equations. In \autoref{sec:cell models}, the dimension of the unknown function $y$ will be $d=18$ and the right-hand side function $f$ will be nonlinear. Using the backward Euler method on the system in \autoref{sec:cell models} requires us to solve a system of $18$ nonlinear equations at every time step. This is both hard to implement and computationally costly.

Both the forward Euler method and the backward Euler method are special cases of what is known as the \emph{$\theta$-method}: $$
\begin{equation}
y_{n+1}\approx y_{n}+\theta \Delta tf(y_{n},t_{n})+(1-\theta)\Delta tf(y_{n+1},t_{n+1}).
\end{equation}
$$
When $\theta=1$ we get the forward Euler method, when $\theta=0$ we get the backwards Euler method, and when $\theta=\frac{1}{2}$ we get the \emph{Crank-Nicolson scheme}. The Crank-Nicolson scheme is second order accurate in time \cite{}, in contrast to the Euler methods. It is also implicit, making it equally hard to implement and numerically costly as the backwards Euler method. 






$$
\begin{equation} 
    \frac{\text{d}m_i}{\text{d}t} =\alpha_{i}(v)(1-m_i)-\beta_{i}(v)m_i, \quad i=1,2,\dots,l,
\end{equation}
$$