\chapter{Theory}
\label{chap:monodomain}

\section{Anatomy}
\label{sec:anatomy}

The heart's main function is to pump deoxygenated blood into the lungs and pump oxygenated blood to the rest of the body. 

It is divided into four chambers. The two upper chambers are the left and right atria, while the two lower chambers are called the left and right ventricles. The right atrium receives deoxygenated blood from the body, which flows into the right ventricle to be pumped and distributed to the lungs to oxygenate the blood. The left atrium receives oxygenated blood from the lungs and passes it to the left ventricle, which contracts to pump the blood to the rest of the body.

The contraction of the various chambers needs to be intricately choreographed by an estimated 2-3 billion cardiac muscle cells. This is achieved by electrical signals initiated in the sinoatrial node, located above the right atrium. 

The muscle cells are connected by gap junctions that allow a flux of ions between cells, leading to an electrical current that affects the transmembrane potential. If the potential reaches a threshold value, the cell undergoes depolarization, which will be described in \ref{sec:ionic currents}. Stimulation of the cells neighboring the sinoatrial node will therefore cause a wave of depolarization to propagate throughout both atria, which in turn signals the muscle cells to contract. The wavefront reaches the ventricles through the atrioventricular node, which delays the propagation of the wavefront slightly. In this way, the atria contract first to pump blood into the relaxed ventricles which contract after a slight delay. 

The depolarization is an extremely fast process that is followed by a much slower process known as repolarization, which restores the transmembrane potential to its resting value. The cycle of depolarization and repolarization is called an action potential. We will see that the speed of the depolarization demands that we have very small time steps.

\section{Volume conductor}
\label{sec:volume conductor}
Sections \ref{sec:volume conductor}, \ref{sec:bidomain}, and \ref{sec:monodomain} are paraphrased from \cite{computing}. We start by modeling the body as a volume conductor, where we can express the relation between the electric and magnetic field from one of Maxwell's equations
$$
\nabla \times E +\frac{\partial B}{\partial t}=0.
$$
The temporal variations of the fields are fairly slow compared in the context of volume conductor theory. We can therefore assume that the system is in electromagnetic equilibrium in each instant of time. This assumption is called the *quasi-static assumption*, resulting in the simplification
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

We denote the ionic current is denoted by $I_\text{ion}$, and the positive direction is defined to by from the intracellular to the extracellular domain. Since $I_\text{ion}$ is measured per unit area of the membrane and the current $J$ is measured per unit volume, we must introduce the cell area to volume ratio as $\chi$. Then, $\chi I_\text{ion}$ is the ionic current per unit volume.

The cell membrane separating the intracellular and extracellular domains acts as an insulator, which allows accumulation of charge in each domain. Denoting the charge in the intracellular and extracellular domain as $q_i$ and $q_e$, respectively, the net current in a point must equal the rate of charge plus the ionic current exiting the domain:

\begin{subequations}
	\label{eq: bidelcurrents}
	\begin{align}
		-\nabla \cdot  J_{i} & = \frac{\partial q_{i}}{\partial t}+\chi I_\text{ion}, \\
		-\nabla \cdot J_{e}  & = \frac{\partial q_{e}}{\partial t}-\chi I_\text{ion}. 
	\end{align} 
\end{subequations}


Since the cell membrane is thin, an accumulation of charge in one domain causes an accumulation of the opposite charge in the other domain. Thus, the rate of total charge accumulation must be zero:
\begin{equation}
	\frac{\partial }{\partial t}(q_{i}+q_{e} )=0. \label{eq: chargeeq}
\end{equation}

The cell membrane can be viewed as a capacitor with capacitance per unit area $C_{m}$ and capacitance per unit volume as $\chi C_{m}$. The transmembrane voltage $v=u_{i}-u_{e}$ and the amount of separated charge $q=\frac{1}{2}(q_{i}-q_{e})$\todo{Why 1/2?} are related by
\begin{equation}
	q=\chi C_{m}v,
\end{equation}
which we can differentiate with respect to time to get

\begin{equation}
	\frac{1}{2}\left(\frac{\partial q_{i}}{\partial t}-\frac{\partial q_{e}}{\partial t} \right)= \chi C_{m}\frac{\partial v}{\partial t}.
	\label{eq: capacitancedt}
\end{equation}

Combining \ref{eq: chargeeq} and \ref{eq: capacitancedt} gives
\begin{equation*}
	\frac{\partial q_{i}}{\partial t}=-\frac{\partial q_{e}}{\partial t}=\chi C_{m}\frac{\partial v}{\partial t},
\end{equation*}

which we can substitute in \ref{eq: bidelcurrents} 
\begin{align*}
    -\nabla \cdot  J_{i} & = \chi C_{m}\frac{\partial v}{\partial t}+\chi I_\text{ion},  \\
    -\nabla \cdot J_{e}  & = -\chi C_{m}\frac{\partial v}{\partial t}-\chi I_\text{ion}. 
\end{align*}

Using \ref{eq: currents}
\begin{align}
	\nabla \cdot (M_{i}\nabla u_{i}) & = \chi C_{m}\frac{\partial v}{\partial t} + \chi I_\text{ion}, \label{eq: intracell}  \\ 
	\nabla \cdot (M_{e}\nabla u_{e}) & = -\chi C_{m}\frac{\partial v}{\partial t} - \chi I_\text{ion}. \label{eq: extracell} 
\end{align}


We use the relation $u_{i}=v+u_{e}$ on \ref{eq: intracell}
\begin{equation}
	\nabla \cdot (M_{i}\nabla v)+\nabla \cdot (M_{i}\nabla u_{e})= \chi C_{m}\frac{\partial v}{\partial t}+\chi I_\text{ion},
	\label{eq: bi1}
\end{equation}

where \ref{eq: extracell} can be applied to obtain the equation
\begin{equation}
	\nabla \cdot (M_{i}\nabla v)+\nabla\cdot((M_{i}+M_{e})\nabla u_{e})=0.
	\label{eq: bi2}
\end{equation}

\ref{eq: bi1} and \ref{eq: bi2} are the standard formulation of the bidomain model. Since the heart tissues are anisotropic, the conductivities $M_{i}$ and $M_{e}$ are tensors. 

To set boundary conditions, we assume that the heart is surrounded by an insulating medium such that we get Neumann conditions for both currents:
\begin{align*}
	n\cdot J_{i} & =0, \\ 
	n\cdot J_{e} & =0. 
\end{align*}

Substituting \ref{eq: currents} and the relation $u_{i}=v+u_{e}$ gives
\begin{align}
	n\cdot(M_{i}\nabla v+M_{i}\nabla u_{e} ) & =0,\label{eq: bibc1}  \\
	n\cdot(M_{e}\nabla u_{e})                & =0. \label{eq: bibc2} 
\end{align}

\ref{eq: bi1} and \ref{eq: bi2} with the boundary conditions \ref{eq: bibc1} and \ref{eq: bibc2} is a system of partial differential equations that are difficult to solve. We will therefore make some assumptions to simplify the model.

\section{Monodomain model}
\label{sec:monodomain}
The model can be derived from assuming equal anisotropy rates between the intracellular and extracellular conductivity tensors, meaning that the tensors are related by a constant $\lambda$. This is expressed as $M_{e}=\lambda M_{i}$. Now, we rewrite \ref{eq: bi2} as
\begin{align*}
	\nabla\cdot(M_{i}\nabla v)+\nabla\cdot ((1+\lambda)M_{i}\nabla u_{e}) & =0                                                \\
	\nabla \cdot(M_{i}\nabla u_{e})                                       & =-\frac{1}{1+\lambda}\nabla \cdot(M_{i}\nabla v), 
\end{align*}

which can be substituted into \ref{eq: bi1}:
\begin{align}
	\nabla \cdot(M_{i}\nabla v)-\frac{1}{1+\lambda}\nabla \cdot(M_{i}\nabla v) & =\chi C_{m} \frac{ \partial v }{ \partial t } +\chi I_\text{ion}  \nonumber\\
	\frac{{\lambda}}{1+\lambda}\nabla \cdot(M_{i}\nabla v)                     & =\chi C_{m} \frac{ \partial v }{ \partial t } +\chi I_\text{ion}. 
	\label{eq: mono}
\end{align}

We assume that some external stimulus $I_{\text{stim}}$ is applied to the tissue, such that \ref{eq: mono} becomes \todo{Explain why Istim appears on LHS}
\begin{equation}
    \frac{{\lambda}}{1+\lambda}\nabla \cdot(M_{i}\nabla v) +\chi I_\text{stim} =\chi C_{m} \frac{ \partial v }{ \partial t } +\chi I_\text{ion}. 
\end{equation}

The boundary condition \ref{eq: bibc2} becomes $n\cdot(\lambda M_{i}\nabla u_{e})=0 \implies n\cdot(M_{i}\nabla u_{e})=0$, which simplifies \ref{eq: bibc1} to
\begin{equation}
	n\cdot(M_{i}\nabla v)=0.
\end{equation}

\section{Ionic current models}
\label{sec:ionic currents}

\begin{align}
    \frac{\lambda }{1+\lambda }\nabla \cdot (M_{i}\nabla v)+\chi I_{\text{stim}} &= \chi C_{m}\frac{\partial v}{\partial t}+\chi I_{\text{ion}}(v,s), &x\in H, \label{eq:monomain}\\
    \frac{\partial s}{\partial t}&= f(s,v,t),&x\in H,\label{eq:monoode}\\
    n \cdot (M_{i}\nabla v)&= 0, &x\in \partial H\label{eq:monobc}.
\end{align}

\section{Operator splitting}
The operator splitting scheme can be used on problems of the form
$$
\frac{ \partial y }{ \partial t }=L_{1}(y)+L_{2}(y),
$$

where $L_{1}$ and $L_{2}$ are two operators on $y$. For a parameter $\theta \in [0,1]$, the operator splitting method is described as
\begin{enumerate}
    \item Given an initial condition $y(t_{n})=y^n$, solve $\frac{ \partial y }{ \partial t } =L_{1}(y)$ for $t_{n}\leq t\leq t_{n}+\theta\Delta t$, and call the solution $y_{\theta}^n$.
    \item With the initial condition $y(t_{n})=y^n_{\theta}$, solve $\frac{ \partial y }{ \partial t } =L_{2}(y)$ for $t_{n}\leq t\leq t_{n}+\Delta t$, and denote the solution as $y^{n+1}_{\theta}$.
    \item With the initial condition $y(t_{n}+\theta\Delta t)=y^{n+1}_{\theta}$, solve $\frac{ \partial y }{ \partial t } =L_{1}(y)$ for $t_{n}+\theta\Delta t \leq t\leq t_{n}+\Delta t$. Denote this solution as $y^{n+1}$.
\end{enumerate}

It can be shown that if $\theta=0.5$, operator splitting is second order accurate. Otherwise, it is first order accurate\cite{computing}.

We want to apply operator splitting on the system \ref{}. \ref{} can be written as

\begin{equation}
    \frac{ \partial v }{ \partial t } =- \frac{1}{C_{m}}I_\text{ion}(v,s)+ \frac{1}{\chi C_{m}} \frac{\lambda}{1+\lambda}\nabla \cdot(M_{i}\nabla v)+ \frac{1}{C_{m}}I_\text{stim}.
\end{equation}

We now choose the operators for $v$ as 
\begin{align}
    L_{1,v}(v,s) & =- \frac{1}{C_{m}}I_\text{ion}(v,s), \\
    L_{2,v}(v,s) & = \frac{1}{\chi C_{m}} \frac{\lambda}{1+\lambda}\nabla \cdot(M_{i}\nabla v)+ \frac{1}{C_{m}}I_\text{stim},
\end{align}

while the operators for $s$ are simply chosen as $L_{1,s}(v,s)=f(s,v,t)$ and $L_{2,s}(v,s)=0$. Now we apply the scheme described above.
\begin{enumerate}
    \item First, given $v(t_{n})=v^{n}$ and $s(t^{n})=s^{n}$, solve
    \begin{align}
    \frac{\partial v}{\partial t}&= -\frac{1}{C_{m}}I_{\text{ion}}(v,s),\\
    \frac{\partial s}{\partial t}&= f(v,s,t),
    \end{align}
    for $t_{n}<t \le t_{n}+\theta \Delta t$. Denote the solutions as $v_{\theta }^{n}$ and $s_{\theta }^{n}$.
\end{enumerate}
1. 

2. Then, with the initial condition $v(t_{n})=v_{\theta }^{n}$, solve
\begin{equation}
    \frac{\partial v}{\partial t}=\frac{1}{\chi C_{m}}\frac{\lambda }{1+\lambda }\nabla \cdot(M_{i}\nabla v)+\frac{1}{C_{m}}I_\text{stim},
\end{equation}
for $t_{n}<t \le t_{n}+\Delta t$. The solution is denoted as $v_{\theta }^{n+1}$.
3. Finally, with the initial conditions $v(t_{n}+\theta \Delta t)=v_{\theta }^{n+1}$ and $s(t_{n}+\theta \Delta t)=s^{n}_{\theta }$, solve the system

\begin{align}
\frac{\partial v}{\partial t}&= -\frac{1}{C_{m}}I_{\text{ion}}(v,s),\\
\frac{\partial s}{\partial t}&= f(v,s),
\end{align}

	for $t_{n}+\theta \Delta t <t \le t_{n}+\Delta t$. The solutions are $v^{n+1}$ and $s ^{n+1}$. 

Notice that since $L_{2,s}(v,s)=0$, we omit it in step 2, and we use the solution $s_{\theta}^n$ from step 1 as the initial condition for step 3.
