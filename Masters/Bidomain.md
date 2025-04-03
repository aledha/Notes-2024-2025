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


