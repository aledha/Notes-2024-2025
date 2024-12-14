\chapter{Theory}
\label{chap:monodomain}

\section{Anatomy}
\label{sec:anatomy}

The heart's main function is to pump deoxygenated blood into the lungs and pump oxygenated blood to the rest of the body. 

It is divided into four chambers. The two upper chambers are the left and right atria, while the two lower chambers are called the left and right ventricles. The right atrium receives deoxygenated blood from the body, which flows into the right ventricle to be pumped and distributed to the lungs to oxygenate the blood. The left atrium receives oxygenated blood from the lungs and passes it to the left ventricle, which contracts to pump the blood to the rest of the body.

The contraction of the various chambers needs to be intricately choreographed by an estimated 2-3 billion cardiac muscle cells. This is achieved by electrical signals initiated in the sinoatrial node, located above the right atrium. 

The muscle cells are connected by gap junctions that allow a flux of ions between cells, leading to an electrical current that affects the transmembrane potential. If the potential reaches a threshold value, the cell undergoes depolarization, which will be described in \ref{sec:ionic currents}. Stimulation of the cells neighboring the sinoatrial node will therefore cause a wave of depolarization to propagate throughout both atria, which in turn signals the muscle cells to contract. The wavefront reaches the ventricles through the atrioventricular node, which slightly delays the wavefront's propagation. In this way, the atria contract first to pump blood into the relaxed ventricles which contract after a slight delay. 

The depolarization is an extremely fast process that is followed by a much slower process known as repolarization, which restores the transmembrane potential to its resting value. The cycle of depolarization and repolarization is called an action potential. We will see that the speed of the depolarization demands that we have very small time steps.

\section{Volume conductor}
\label{sec:volume conductor}
Sections \ref{sec:volume conductor}, \ref{sec:bidomain}, and \ref{sec:monodomain} are paraphrased from \cite{computing}. We start by modeling the body as a volume conductor, where we can express the relation between the electric and magnetic field from one of Maxwell's equations:
$$
\nabla \times E +\frac{\partial B}{\partial t}=0.
$$
The temporal variations of the fields are fairly slow compared to the context of volume conductor theory. We can therefore assume that the system is in electromagnetic equilibrium in each instant of time. This assumption is called the *quasi-static assumption*, resulting in the simplification
$$
\nabla \times E=0.
$$
This implies that the electric field may be represented as the gradient of a scalar valued potential $u$:
$$
E=-\nabla u.
$$
The current $J$ in a conductor with an electric field $E$ and with conductivity $M$ is given by the relation
$$
J=ME=-M \nabla u.
$$

\section{Bidomain model}
\label{sec:bidomain}
To avoid modeling the complex geometry of the intra- and extra-cellular domains, we assume that both domains overlap. Therefore, each point in the domain has an intracellular potential $u_i$ and an extracellular potential $u_e$. The currents for the intracellular and extracellular domains are respectively
\begin{equation}
	\begin{aligned}
		J_{i} & = -M _{i}\nabla u_{i}, \\
		J_{e} & = -M_{e}\nabla u_{e}.  
	\end{aligned} \label{eq: currents}
\end{equation}
where $M_{i}$ and $M_{e}$ are the conductivity tensors for the intracellular domain and extracellular domain, respectively. 

The ionic current is denoted by $I_\text{ion}$, and the positive direction is defined to by from the intracellular to the extracellular domain. Since $I_\text{ion}$ is measured per unit area of the membrane and the currents $J_{i}$ and $J_{e}$ are measured per unit volume, we must introduce the cells area to volume ratio as $\chi$. Then, $\chi I_\text{ion}$ is the ionic current per unit volume.

The cell membrane can be viewed as a capacitor with capacitance per unit area $C_{m}$ and capacitance per unit volume as $\chi C_{m}$. Then, the transmembrane voltage $v=u_{i}-u_{e}$ and current are related by
\begin{equation}
I_{c}=\chi C_{m}\frac{ \partial v }{ \partial t } .
\end{equation}

If we assume that there also is a stimulating current $I_\text{stim}$, the total transmembrane current $I_{t}$ must be the sum of the ionic current, the capacitive current, and the stimulating current \cite{mathphys, p.567}:
\begin{equation}
I_{t}=\chi C_{m}\frac{ \partial v }{ \partial t } +\chi I_{\text{ion}}-\chi I_\text{stim},\label{eq:totalcurrent1}
\end{equation}

where the stimulating current is negative because it travels from the extracellular to the intracellular domain. The total current must also equal the current exiting the intracellular domain and the current entering the extracellular domain:
\begin{align}
I_{t} & =-\nabla \cdot J_{i}=\nabla \cdot J_{e},\nonumber \\
 I_{t}& =\nabla \cdot(M_{i}\nabla u_{i})=-\nabla \cdot(M_{e}\nabla u_{e}). \label{eq:totalcurrent2}
\end{align}

We use the relation $u_{i}=v+u_{e}$
\begin{equation}
\nabla \cdot(M_{i}\nabla(v+u_{e}))=-\nabla \cdot(M_{e}\nabla u_{e})=I_{t},
\end{equation}

which gives us the standard formulation of the bidomain model
\begin{align}
\label{eq:bi1} 
\nabla \cdot(M_{i}\nabla v)+\nabla \cdot(M_{i}\nabla u_{e}) & =\chi C_{m}\frac{ \partial v }{ \partial t } +\chi I_\text{ion}-\chi I_\text{stim}, \\ 
\label{eq:bi2} 
\nabla \cdot(M_{i}\nabla v)+\nabla \cdot((M_{i}+M_{e})\nabla u_{e}) & =0 .
\end{align}

To set boundary conditions, we assume that the heart is surrounded by an insulating medium such that we get Neumann conditions for both currents:
\begin{align}
n\cdot J_{i} & =0, \\ %label{eq: bibc1}
n\cdot J_{e} & =0. %label{eq: bibc2}
\end{align}


Substituting \ref{eq: currents} and the relation $u_{i}=v+u_{e}$ gives
\begin{align}
    \label{eq:bibc1}
    n\cdot(M_{i}\nabla v+M_{i}\nabla u_{e} ) & =0, \\
    \label{eq:bibc2}
    n\cdot(M_{e}\nabla u_{e}) & =0.
\end{align}

\ref{eq:bi1} and \ref{eq:bi2} with the boundary conditions \ref{eq:bibc1} and \ref{eq:bibc2} is a system of partial differential equations that is difficult to solve. We will therefore make some assumptions to simplify the model. 

\section{Monodomain model}
\label{sec:monodomain}
To arrive at the monodomain model, we make the assumption that the intracellular and extracellular conductivity tensors are related by a diagonal tensor $\Lambda$ such that $M_{e}=\Lambda M_{i}$. Then, \ref{eq:bi2} becomes
\begin{align*}
\nabla \cdot(M_{i} \nabla v)+\nabla \cdot((M_{i}+\Lambda M_{i})\nabla u_{e}) & =0 \\
(I+\Lambda)\nabla \cdot(M_{i}\nabla u_{e})& =-\nabla \cdot(M_{i} \nabla v)  \\
\nabla \cdot(M_{i}\nabla u_{e}) & =-(I+\Lambda)^{-1}\nabla \cdot(M_{i}\nabla v)
\end{align*}

which we can substitute in \ref{eq:bi1}:
\begin{align}
\nabla \cdot(M_{i}\nabla v)-(I+D)^{-1}\nabla \cdot(M_{i}\nabla v) & =\chi C_{m} \frac{ \partial v }{ \partial t } +\chi I_\text{ion}  -\chi I_\text{stim}\nonumber\\
(I-(I+D)^{-1})\nabla \cdot(M_{i}\nabla v) & =\chi C_{m}\frac{ \partial v }{ \partial t } +\chi I_\text{ion} -\chi I_\text{stim}\nonumber\\
%\label{eq:mono} 
\nabla \cdot(M \nabla v) & =\chi C_{m}\frac{ \partial v }{ \partial t } +\chi I_\text{ion}-\chi I_\text{stim},
\end{align}

where
\begin{align*}
M & =(I-(I+\Lambda)^{-1})M_{i} \\
 & =M_{i}-(I+\Lambda)^{-1}M_{i}, \\
(I+\Lambda)M & =(I+\Lambda)M_{i}-M_{i}=\Lambda M_{i} \\
M & =(I+\Lambda)^{-1}M_{e}.
\end{align*}

If $M_{i}$ and $M_{e}$ happen to be diagonal\todo{describe local conductivity tensors?} with $\sigma_{i,j}$ and $\sigma_{e,j}$ as entries number $j$, then entry $j$ in $\Lambda$ will simply be the proportion $\lambda_{j}=\frac{\sigma_{e,j}}{\sigma_{i,j}}$. Then, entry $j$ in $M$ can be found as 
\begin{align}
\sigma_{j}  & =\frac{1}{1+\frac{\sigma_{e,j}}{\sigma_{i,j}}}\sigma_{e,j} \nonumber \\
\label{eq:harmoniccond}
 \sigma_{j}& =\frac{\sigma_{i,j}\sigma_{e,j}}{\sigma_{i,j}+\sigma_{e,j}}.
\end{align}

The boundary condition \ref{eq:bibc2} becomes $n\cdot(\Lambda M_{i}\nabla u_{e})=0 \implies n\cdot(M_{i}\nabla u_{e})=0$, which simplifies \ref{eq:bibc1} to\todo{This seems dubious}
\begin{equation}
	n\cdot(M_{i}\nabla v)=0.
\end{equation}
\begin{align} 
    n\cdot(M_{i}\nabla v+M_{i}\nabla u_{e} ) & =0, \\
    n\cdot(M_{e}\nabla u_{e}) & =0.  \\
    n\cdot(\Lambda^{-1}(1+\Lambda)M\nabla v+\Lambda^{-1}(1+\Lambda)M\nabla u_{e} ) & =0, \\
    n\cdot((I+\Lambda)M\nabla u_{e}) & =0.
\end{align}

\section{Ionic current models}
\label{sec:ionic currents}
\todo{Describe Tentusccher model}

\begin{align}
    \nabla \cdot (M\nabla v)+\chi I_{\text{stim}} &= \chi C_{m}\frac{\partial v}{\partial t}+\chi I_{\text{ion}}(v,s), &x\in H, \label{eq:monomain}\\
    \frac{\partial s}{\partial t}&= f(s,v,t),&x\in H,\label{eq:monoode}\\
    n \cdot (M\nabla v)&= 0, &x\in \partial H\label{eq:monobc}.
\end{align}

\section{Operator splitting}
\label{sec:opsplit}
The operator splitting scheme can be used on problems of the form
$$
\frac{ \partial y }{ \partial t }=L_{1}(y)+L_{2}(y),
$$

where $L_{1}$ and $L_{2}$ are two operators on $y$. For a parameter $\theta \in [0,1]$, the operator splitting method is described as
\begin{enumerate}
    \item Given an initial condition $y(t_{n})=y^n$, solve $\frac{ \partial y }{ \partial t } =L_{1}(y)$ for $t\in [t_n, t_n+\theta\Delta t]$, and call the solution $y_{\theta}^n$.
    \item With the initial condition $y(t_{n})=y^n_{\theta}$, solve $\frac{ \partial y }{ \partial t } =L_{2}(y)$ for $t\in [t_n, t_n+\Delta t]$, and denote the solution as $y^{n+1}_{\theta}$.
    \item With the initial condition $y(t_{n}+\theta\Delta t)=y^{n+1}_{\theta}$, solve $\frac{ \partial y }{ \partial t } =L_{1}(y)$ for $t\in [t_n+\theta\Delta t, t_n+\Delta t]$. Denote this solution as $y^{n+1}$.
\end{enumerate}

It can be shown that if $\theta=0.5$, operator splitting is second-order accurate. Otherwise, it is first order accurate\cite{computing}.

We want to apply operator splitting on the system \ref{eq:monomain}-\ref{eq:monobc}. \ref{eq:monomain} can be written as

\begin{equation}
    \frac{ \partial v }{ \partial t } =- \frac{1}{C_{m}}I_\text{ion}(v,s)+ \frac{1}{\chi C_{m}} \frac{\lambda}{1+\lambda}\nabla \cdot(M_{i}\nabla v)+ \frac{1}{C_{m}}I_\text{stim}.
\end{equation}

We now choose the operators for $v$ as 
\begin{align*}
    L_{1,v}(v,s) & =- \frac{1}{C_{m}}I_\text{ion}(v,s), \\
    L_{2,v}(v,s) & = \frac{1}{\chi C_{m}} \frac{\lambda}{1+\lambda}\nabla \cdot(M_{i}\nabla v)+ \frac{1}{C_{m}}I_\text{stim},
\end{align*}

while the operators for $s$ are simply chosen as $L_{1,s}(v,s)=f(s,v,t)$ and $L_{2,s}(v,s)=0$. Now we apply the scheme described above.
\begin{enumerate}
    \item First, given $v(t_{n})=v^{n}$ and $s(t^{n})=s^{n}$, solve the system
    \begin{align}
        \label{eq:odesplitv}
        \frac{\partial v}{\partial t}&= -\frac{1}{C_{m}}I_{\text{ion}}(v,s),\\
        \label{eq:odesplits}
        \frac{\partial s}{\partial t}&= f(v,s,t),
    \end{align}
    
    for $t\in [t_n, t_n+\theta\Delta t]$. Denote the solutions as $v_{\theta }^{n}$ and $s_{\theta }^{n}$.

    \item Then, with the initial condition $v(t_{n})=v_{\theta }^{n}$, solve
    \begin{equation}
        \label{eq:pdesplit}
        \frac{\partial v}{\partial t}=\frac{1}{\chi C_{m}}\frac{\lambda }{1+\lambda }\nabla \cdot(M_{i}\nabla v)+\frac{1}{C_{m}}I_\text{stim},
    \end{equation}
    
    for $t\in [t_n, t_n+\Delta t]$. The solution is denoted as $v_{\theta }^{n+1}$.

    \item Finally, with the initial conditions $v(t_{n}+\theta \Delta t)=v_{\theta }^{n+1}$ and $s(t_{n}+\theta \Delta t)=s^{n}_{\theta }$, solve the system \ref{eq:odesplitv}-\ref{eq:odesplits} again for $t\in [t_n+\theta\Delta t, t_n+\Delta t]$. The solutions are denoted $v^{n+1}$ and $s ^{n+1}$. 
\end{enumerate}

Notice that since $L_{2,s}(v,s)=0$, we omit it in step 2, and we use the solution $s_{\theta}^n$ from step 1 as the initial condition for step 3.

\section{Galerkin formulation}
To to solve the PDE \ref{eq:pdesplit}, we will utilize a $\theta$-method to discretize in time:
\begin{equation}
\label{eq:thetarule}
    \frac{v^{n+1}-v^{n}}{\Delta t}= \frac{1}{\chi C_{m}}\frac{\lambda }{1+\lambda }\left(\theta \nabla \cdot(M_{i}\nabla v^{n+1})+(1-\theta )\nabla \cdot(M_{i}\nabla v^{n}) \right)+\frac{1}{C_{m}}I_\text{stim}. 
\end{equation}

Notice that this $\theta$ differs from the parameter $\theta$ used in section \ref{sec:opsplit}. However, a parameter choice of $\theta =\frac{1}{2}$ gives the second-order Crank-Nicholson scheme, and the same choice for $\theta$ gives second-order accuracy for the operator splitting. Similarly, $\theta\neq \frac{1}{2}$ gives a first order scheme for both the $\theta$-method and the operator splitting. Hence, we treat the parameter as the same. 

Let $\alpha= \frac{\Delta t}{\chi C_{m}} \frac{\lambda}{1+\lambda}$ and $\beta= \frac{\Delta t}{C_{m}}$, then \ref{eq:thetarule} becomes
\begin{equation}
    \label{eq:timediscrete}
    v^{n+1}-v^n =\alpha\theta \nabla \cdot(M_{i}\nabla v^{n+1})+\alpha(1-\theta)\nabla \cdot(M_{i}\nabla v^n)+\beta I_\text{stim}. 
\end{equation}

Now, we can reformulate \ref{eq:timediscrete} into a Galerkin formulation: 
For some suitable function space $V$, find $v^{n+1}\in V$, given $v^n\in V$, such that for every $\phi \in V$,
\begin{equation*}
    \int_{H}(v^{n+1}-v^n)\phi \text{ d} \mathbf{x} =\int_{H}(\alpha\theta \nabla \cdot(M_{i}\nabla v^{n+1})+\alpha(1-\theta)\nabla \cdot(M_{i}\nabla v^n)+\beta I_\text{stim})\phi \text{ d} \mathbf{x}
\end{equation*}

\begin{equation*}
    \int_{H}v^{n+1}\phi -\alpha\theta\nabla \cdot(M_{i}\nabla v^{n+1})\phi \text{ d} \mathbf{x} =\int_{H}(\beta I_\text{stim}+v^n)\phi + \alpha(1-\theta)\nabla \cdot(M_{i}\nabla v^n)\phi \text{ d} \mathbf{x} 
\end{equation*}

Using the divergence theorem, we can rewrite the last term of both sides as
\begin{align*}
    \int_{H}\nabla \cdot(M_{i}\nabla v^{n+1})\phi \text{ d} \mathbf{x} & =  \int_{\partial H}\mathbf{n}\cdot(M_{i}\nabla v^{n+1})\phi \text{ d} \mathbf{x}-\int_{H}(M_{i}\nabla v^{n+1})\cdot \nabla \phi \text{ d} \mathbf{x}, \\
    \int_{H}\nabla \cdot(M_{i}\nabla v^{n})\phi \text{ d} \mathbf{x} & =  \int_{\partial H}\mathbf{n}\cdot(M_{i}\nabla v^{n})\phi \text{ d} \mathbf{x}-\int_{H}(M_{i}\nabla v^{n+1})\cdot \nabla \phi \text{ d} \mathbf{x},
\end{align*}

where the boundary integrals vanish due to the boundary condition \ref{eq:monobc}. Substituting the terms back gives
\begin{equation}
    \label{eq:galerkin}
    \int_{H}v^{n+1}\phi  +\alpha\theta(M_{i}\nabla v^{n+1})\cdot\nabla\phi \text{ d} \mathbf{x}  =\int_{H}(\beta I_\text{stim}+v^n)\phi - \alpha(1-\theta)(M_{i}\nabla v^n)\cdot \nabla\phi \text{ d} \mathbf{x} .
\end{equation}

The bilinear and linear forms are
\begin{align}
    \label{eq:bilinearform}
    a(v^{n+1},\phi )&= \int_{H}v^{n+1}\phi  +\alpha\theta(M_{i}\nabla v^{n+1})\cdot\nabla\phi\text{ d}\mathbf x,\\ 
    \label{eq:linearform}
    L(\phi )&= \int_{H} (\beta I_\text{stim}+v^n)\phi - \alpha(1-\theta)(M_{i}\nabla v^n)\cdot \nabla\phi \text{ d} \mathbf{x}.
\end{align}


