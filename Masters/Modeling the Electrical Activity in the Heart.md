## Anatomy
The main function of the heart is to pump deoxygenated blood into the lungs and pump oxygenated blood to the rest of the body. 

It is divided into four chambers, as depicted in figure (). The two upper chambers are the left and right atria, while the two lower chambers are called the left and right ventricle. The right atrium receives deoxygenated blood from the body, which flows into the right ventricle to then be pumped and distributed to the lungs in order to oxygenate the blood. The left atrium receives oxygenated blood from the lungs and passes it to the left ventricle, which contracts to pump the blood to the rest of the body.

The contraction of the various chambers needs to be intricately choreographed by an estimated 2-3 billion cardiac muscle cells. This is achieved by electrical signals initiated in the sinoatrial node, located above the right atrium. 

The muscle cells are connected by gap junctions that allow flux of ions between cells, leading to an electrical current which effects the transmembrane potential. If the potential reaches a threshold value, the cell undergoes a process called depolarization, which will be described in further detail in (#ref). Stimulation of the cells neighbouring the sinoatrial node will therefore cause a wave of depolarisation to propagate throughout both atria, which in turn signals the muscle cells to contract. The wavefront reaches the ventricles through the atrioventricular node, which delays the propagation of the wavefront slightly. In this way, the atria contract first to pump blood into the relaxed ventricles that then contract after a slight delay. 

The depolarization is an extremely fast process, and is followed by a much slower process known as repolarization, which restores the transmembrane potential to the its resting value. The cycle of depolarization and repolarization is called an action potential. We will see that the speed of the depolarization demands that we have a very small time steps.

## Volume conductor
We start by modeling the body as a volume conductor, where we can express the relation between the electric and magnetic field from one of Maxwell's equations
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
The current $I$ in a conductor with an electric field $E$ and with conductivity $M$ is given by the relation
$$
J=ME=-M \nabla u.
$$
## Bidomain model
TTo avoid modeling the complex geometry of the intra- and extra-cellular domains, we assume that both domains overlap. Therefore, each point in the domain has an intracellular potential $u_i$ and an extracellular potential $u_e$. The currents for the intracellular and extracellular domains are respectively
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
## Monodomain, old
The monodomain model can be derived from assuming equal anisotropy rates between the intracellular and extracellular conductivity tensors, meaning that the tensors are related by a constant $\lambda$. This is expressed as $M_{e}=\lambda M_{i}$. Now, we rewrite \ref{eq: bi2} as
$$
\begin{align}
\nabla\cdot(M_{i}\nabla v)+\nabla\cdot ((1+\lambda)M_{i}\nabla u_{e}) & =0 \\
\nabla \cdot(M_{i}\nabla u_{e}) & =-\frac{1}{1+\lambda}\nabla \cdot(M_{i}\nabla v),
\end{align}
$$

which can substitute in \ref{eq: bi1}:
$$
\begin{align}
\nabla \cdot(M_{i}\nabla v)-\frac{1}{1+\lambda}\nabla \cdot(M_{i}\nabla v) & =\chi C_{m} \frac{ \partial v }{ \partial t } +\chi I_\text{ion}-\chi I_\text{stim} \\
\frac{{\lambda}}{1+\lambda}\nabla \cdot(M_{i}\nabla v) & =\chi C_{m} \frac{ \partial v }{ \partial t } +\chi I_\text{ion}-\chi I_\text{stim} \\
%label{eq: mono} 
\nabla \cdot(M\nabla v) & =\chi C_{m}\frac{ \partial v }{ \partial t } +\chi I_\text{ion}-\chi I_\text{stim},
\end{align}
$$
where
$$
\begin{equation}
M=\frac{\lambda}{1+\lambda}M_{i}.%\label{eq:Mtensor}
\end{equation}
$$

\ref{eq: bibc2} becomes $n\cdot(\lambda M_{i}\nabla u_{e})=0 \implies n\cdot(M_{i}\nabla u_{e})=0$, which simplifies \ref{eq: bibc1} to
$$
\begin{equation}
n\cdot(M_{i}\nabla v)=0. %\label{eq: monobc}
\end{equation}
$$


## Monodomain
To arrive at the monodomain model, we make the assumption that the intracellular and extracellular conductivity tensors are related by a diagonal tensor $\Lambda$ such that $M_{e}=\Lambda M_{i}$. Then, \ref{eq:bi2} becomes
$$
\begin{align*}
\nabla \cdot(M_{i} \nabla v)+\nabla \cdot((M_{i}+\Lambda M_{i})\nabla u_{e}) & =0 \\
(I+\Lambda)\nabla \cdot(M_{i}\nabla u_{e})& =-\nabla \cdot(M_{i} \nabla v)  \\
\nabla \cdot(M_{i}\nabla u_{e}) & =-(I+\Lambda)^{-1}\nabla \cdot(M_{i}\nabla v)
\end{align*}
$$
which we can substitute in \ref{eq:bi1}:
$$
\begin{align}
\nabla \cdot(M_{i}\nabla v)-(I+D)^{-1}\nabla \cdot(M_{i}\nabla v) & =\chi C_{m} \frac{ \partial v }{ \partial t } +\chi I_\text{ion}  -\chi I_\text{stim}\nonumber\\
(I-(I+D)^{-1})\nabla \cdot(M_{i}\nabla v) & =\chi C_{m}\frac{ \partial v }{ \partial t } +\chi I_\text{ion} -\chi I_\text{stim}\nonumber\\
%\label{eq:mono} 
\nabla \cdot(M \nabla v) & =\chi C_{m}\frac{ \partial v }{ \partial t } +\chi I_\text{ion}-\chi I_\text{stim},
\end{align}
$$
where
$$
\begin{align*}
M & =(I-(I+\Lambda)^{-1})M_{i} \\
 & =M_{i}-(I+\Lambda)^{-1}M_{i}, \\
(I+\Lambda)M & =(I+\Lambda)M_{i}-M_{i}=\Lambda M_{i} \\
M & =(I+\Lambda)^{-1}M_{e}.
\end{align*}
$$
If $M_{i}$ and $M_{e}$ happen to be diagonal with $\sigma_{i,j}$ and $\sigma_{e,j}$ as entries number $j$, then entry $j$ in $\Lambda$ will simply be the proportion $\lambda_{j}=\frac{\sigma_{e,j}}{\sigma_{i,j}}$. Then, entry $j$ in $M$ can be found as 
$$
\begin{align}
\sigma_{j}  & =\frac{1}{1+\frac{\sigma_{e,j}}{\sigma_{i,j}}}\sigma_{e,j} \nonumber \\
%\label{eq:harmoniccond}
 \sigma_{j}& =\frac{\sigma_{i,j}\sigma_{e,j}}{\sigma_{i,j}+\sigma_{e,j}}.
\end{align}
$$
$$
\begin{align} 
    n\cdot(M_{i}\nabla v+M_{i}\nabla u_{e} ) & =0, \\
    n\cdot(M_{e}\nabla u_{e}) & =0.  \\
    n\cdot(\Lambda^{-1}(I+\Lambda)M\nabla v+\Lambda^{-1}(1+\Lambda)M\nabla u_{e} ) & =0, \\
    n\cdot((I+\Lambda)M\nabla u_{e}) & =0. \\
\end{align}
$$
