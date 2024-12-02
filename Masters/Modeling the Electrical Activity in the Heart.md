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
The current $J$ in a conductor with an electric field $E$ and with conductivity $M$ is given by the relation
$$
J=ME=-M \nabla u.
$$
## Bidomain model
To avoid modeling the complex geometry of the intracellular and extracellular domain, we assume that both domains are overlapping. Therefore, each point in the domain has an intracellular potential $u_i$ and an extracellular potential $u_e$. The currents are
$$
\begin{aligned}
J_{i}&= -M _{i}\nabla u_{i},\\
J_{e}&= -M_{e}\nabla u_{e}. 
\end{aligned} %label{eq: currents}
$$
We denote the ionic current is denoted by $I_\text{ion}$, and the positive direction is defined to by from the intracellular to the extracellular domain. Since $I_\text{ion}$ is measured per unit area of the membrane and the current $J$ is measured per unit volume, we must introduce the cells area to to volume ratio as $\chi$. Then, $\chi I_\text{ion}$ is the ionic current per unit volume.

The cell membrane separating the intracellular and extracellular domain acts as an insulator, which allows accumulation of charge in each domain. Denoting the charge in the intracellular and extracellular domain as $q_i$ and $q_e$, respectively, the net current in a point must equal the rate of charge plus the ionic current exiting the domain:
$$
\begin{aligned}
-\nabla \cdot  J_{i}&= \frac{\partial q_{i}}{\partial t}+\chi I_\text{ion},\\
-\nabla \cdot J_{e}&= \frac{\partial q_{e}}{\partial t}-\chi I_\text{ion}.
\end{aligned}%label{eq: bidelcurrents}
$$

Since the cell membrane is thin, accumulation of charge in one domain causes accumulation of the opposite charge in the other domain. Thus, the rate of total charge accumulation must be zero:
$$
\frac{\partial }{\partial t}(q_{i}+q_{e} )=0. %label{eq: chargeeq}
$$

The cell membrane can be viewed as a capacitor with capacitance per unit area $C_{m}$ and capacitance per unit volume as $\chi C_{m}$. The transmembrane voltage $v=u_{i}-u_{e}$ and the amount of separated charge $q=\frac{1}{2}(q_{i}-q_{e})$ are related by
$$
q=\chi C_{m}v,
$$
which we can differentiate with respect to time to get
$$
\frac{1}{2}\left(\frac{\partial q_{i}}{\partial t}-\frac{\partial q_{e}}{\partial t} \right)= \chi C_{m}\frac{\partial v}{\partial t}.%label{eq: capacitancedt}
$$

Combining \ref{eq: chargeeq} and \ref{eq: capacitancedt} gives
$$
\frac{\partial q_{i}}{\partial t}=-\frac{\partial q_{e}}{\partial t}=\chi C_{m}\frac{\partial v}{\partial t},
$$

which we can substitute in \ref{eq: bidelcurrents} 
$$
\begin{aligned}
-\nabla \cdot  J_{i}&= \chi C_{m}\frac{\partial v}{\partial t}+\chi I_\text{ion},\\
-\nabla \cdot J_{e}&= -\chi C_{m}\frac{\partial v}{\partial t}-\chi I_\text{ion}.
\end{aligned}
$$
Using \ref{eq: currents}
$$
\begin{aligned}
\nabla \cdot (M_{i}\nabla u_{i})&= \chi C_{m}\frac{\partial v}{\partial t} + \chi I_\text{ion},\\ %label{eq: intracell}
\nabla \cdot (M_{e}\nabla u_{e})&= -\chi C_{m}\frac{\partial v}{\partial t} - \chi I_\text{ion}. %label{eq: extracell}
\end{aligned}
$$

We use the relation $u_{i}=v+u_{e}$ on \ref{eq: intracell}
$$
\nabla \cdot (M_{i}\nabla v)+\nabla \cdot (M_{i}\nabla u_{e})= \chi C_{m}\frac{\partial v}{\partial t}+\chi I_\text{ion},%label{eq: bi1}
$$

where \ref{eq: extracell} can be applied to obtain the equation
$$
\nabla \cdot (M_{i}\nabla v)+\nabla\cdot((M_{i}+M_{e})\nabla u_{e})=0.%label{eq: bi2}
$$

\ref{eq: bi1} and \ref{eq: bi2} are the standard formulation of the bidomain model. Notice that since the heart tissues are anisotropic, the conductivities $M_{i}$ and $M_{e}$ are tensors. 

To set boundary conditions, we assume that the heart is surrounded by an insulating medium such that we get Neumann conditions for both currents:
$$
\begin{align}
n\cdot J_{i} & =0, \\ %label{eq: bibc1}
n\cdot J_{e} & =0. %label{eq: bibc2}
\end{align}
$$

Substituting \ref{eq: currents} and the relation $u_{i}=v+u_{e}$ gives
$$
\begin{align}
n\cdot(M_{i}\nabla v+M_{i}\nabla u_{e} ) & =0, \\
n\cdot(M_{e}\nabla u_{e}) & =0.
\end{align}
$$

\ref{eq: bi1} and \ref{eq: bi2} with the boundary conditions \ref{eq: bibc1} and \ref{eq: bibc2} is a system of partial differential equations that are difficult to solve. We will therefore make some assumptions to simplify the model.

## Monodomain model
The model can be derived from assuming equal anisotropy rates between the intracellular and extracellular conductivity tensors, meaning that the tensors are related by a constant $\lambda$. This is expressed as $M_{e}=\lambda M_{i}$. Now, we rewrite \ref{eq: bi2} as
$$
\begin{align}
\nabla\cdot(M_{i}\nabla v)+\nabla\cdot ((1+\lambda)M_{i}\nabla u_{e}) & =0 \\
\nabla \cdot(M_{i}\nabla u_{e}) & =-\frac{1}{1+\lambda}\nabla \cdot(M_{i}\nabla v),
\end{align}
$$

which can substitute in \ref{eq: bi1}:
$$
\begin{align}
\nabla \cdot(M_{i}\nabla v)-\frac{1}{1+\lambda}\nabla \cdot(M_{i}\nabla v) & =\chi C_{m} \frac{ \partial v }{ \partial t } +\chi I_\text{ion} \\
\frac{{\lambda}}{1+\lambda}\nabla \cdot(M_{i}\nabla v) & =\chi C_{m} \frac{ \partial v }{ \partial t } +\chi I_\text{ion}.%label{eq: mono}
\end{align}
$$

\ref{eq: bibc2} becomes $n\cdot(\lambda M_{i}\nabla u_{e})=0 \implies n\cdot(M_{i}\nabla u_{e})=0$, which simplifies \ref{eq: bibc1} to
$$
n\cdot(M_{i}\nabla v)=0. %label{eq: monobc}
$$
