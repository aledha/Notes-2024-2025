The bidomain model can be derived by considering one of Maxwell's equations:
$$
\begin{equation}
\nabla \times \mathbf{E}=-\frac{ \partial \mathbf{B} }{ \partial t }, 
\end{equation}
$$
where $\mathbf{E}$ ($\mathrm{Vm^{-1}}$) is the electric field and $\mathbf{B}$ is the magnetic field. We assume that $\frac{ \partial \mathbf{B} }{ \partial t }$ is negligible compared to $\nabla \times \mathbf{E}$, which is called the $\textit{quasi-static assumption}$. Then,
$$
\begin{equation}
\nabla \times \mathbf{E}=0,
\end{equation}
$$
which implies that the electrical field can be written as the divergence of a potential $v$ \cite:
$$
\begin{equation}
\mathbf{E}=-\nabla v.
\end{equation}
$$
The current densitiy $\mathbf{J}$ ($\mathrm{Am^{-2}}$) is given by
$$
\begin{equation}
\mathbf{J}=\mathbf{M}\mathbf{E},
\end{equation}
$$
where $\mathbf{M}$ ($\mathrm{Sm^{-1}}$) is the conductivity tensor. Combining \eqref{eq:} and \eqref{eq:}, and considering the intracellular and extracellular domains gives
$$
\begin{align}
\mathbf{J}_{i}=-\mathbf{M}_{i}\nabla v_{i}, \\
\mathbf{J}_{e}=-\mathbf{M}_{e}\nabla v_{e}.
\end{align}
$$
We assume that our domain is electrically isolated, leading t

Let $I_{t}$ $\mathrm{(Am^{-3})}$ be the total transmembrane current per unit volume, with positive direction from the extracellular domain to the intracellular domain. Then, since no current is lost and there are no other sources
$$
\begin{equation}
%\label{eq:transcurrent}
\nabla \cdot \mathbf{J}_{e}=I_{t}=-\nabla \cdot \mathbf{J}_{i}.
\end{equation}
$$
\eqref{eq:} can be rewritten as the system of equations
$$
\begin{align}
-\nabla \cdot \mathbf{J}_{i} & =I_{t}, \\
\nabla \cdot \mathbf{J}_{e}+\nabla \cdot \mathbf{J}_{i} & =0.
\end{align}
$$
Substitution with \eqref{eq:}-\eqref{eq:} gives
$$
\begin{align}
\nabla \cdot (\mathbf{M}_{i}\nabla v_{i}) & =I_{t}, \\
\nabla \cdot (\mathbf{M}_{e}\nabla v_{e})+\nabla \cdot (\mathbf{M}_{i}\nabla v_{i}) & =0.
\end{align}
$$

The transmembrane current $I_{t}$ is composed of a capacitive current $I_{c}$ and the ionic current $I_\text{ion}$ described in \autoref{}. The capacitive current can be found by viewing the considering the cell membrane as a capacitor with the general capacitor equation
$$
\begin{equation}
%\label{eq:capacitor}
Q=C_{m}v,
\end{equation}
$$
where $Q$ $(\mathrm{C})$ is the charge, $C_{m}$ $(\mathrm{F})$ is the membrane capacitance, and $v=v_{i}-v_{e}$ is the transmembrane potential. Differentiation of \eqref{eq:} with respect to time gives
$$
\begin{equation}
I_{c}=C_{m}\frac{ \partial v }{ \partial t } .
\end{equation}
$$
Since $I_{c}$ and $I_\text{ion}$ are measured per unit area, while $I_{t}$ is measured per unit volume, we must include the cells surface to volume ratio $\chi$ to relate the currents:
$$
\begin{align}
I_{t} & =\chi(I_{c}+I_\text{ion}) \\
I_{t} & =\chi\left( C_{m}\frac{ \partial v }{ \partial t } +I_\text{ion} \right).
\end{align}
$$

Substitution of \eqref{eq:} and $v_{i}=v+v_{e}$ in \eqref{eq:} gives
$$
\begin{align}
\nabla \cdot(\mathbf{M}_{i}(\nabla v+\nabla v_{e})) & =\chi\left( C_{m}\frac{ \partial v }{ \partial t } +I_\text{ion} \right), \\
\nabla \cdot(\mathbf{M}_{e}+\mathbf{M}_{i})v_{e}+\nabla \cdot(\mathbf{M}_{i}\nabla v) & =0
\end{align}
$$
