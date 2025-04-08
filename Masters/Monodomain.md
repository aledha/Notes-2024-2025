In this subsection, we will reduce the bidomain equations to a single partial differential equation with one unknown. This can be achieved by assuming that the intracellular and extracellular conduction tensors are related to a scalar: $\mathbf{M}_{e}=\gamma \mathbf{M}_{i}$. This is called the $\textit{equal anisotropy rates assumption}$ \cite{}. \todo{discuss accuracy}

$$
\begin{align}
\nabla \cdot(\mathbf{M}_{i}(\nabla v+\nabla v_{e})) & =\chi\left( C_{m}\frac{ \partial v }{ \partial t } +I_\text{ion} \right), &  \quad \mathbf{X}\in \Omega,\\
\nabla \cdot(\mathbf{M}_{e}+\mathbf{M}_{i})\nabla v_{e}+\nabla \cdot(\mathbf{M}_{i}\nabla v) & =0, & \mathbf{X}\in \Omega.
\end{align}
$$

Then, \eqref{eq:bi2} becomes
$$
\begin{equation}
\nabla \cdot(\mathbf{M}_{i}\nabla v_{e}) =-\frac{1}{1+\gamma}\nabla \cdot(\mathbf{M}_{i}\nabla v),
\end{equation}
$$
which we can substitute into \eqref{eq:bi1} to eliminate $v_{e}$:
$$
\begin{align}
\nabla \cdot(\mathbf{M}_{i}\nabla v)-\frac{1}{1+\gamma}\nabla \cdot(\mathbf{M}_{i}\nabla v) & =\chi\left( C_{m}\frac{ \partial v }{ \partial t } +I_\text{ion} \right) \\
\frac{\gamma}{1+\gamma}\nabla \cdot(\mathbf{M}_{i}\nabla v) & =\chi\left( C_{m}\frac{ \partial v }{ \partial t } +I_\text{ion} \right) .
\end{align}
$$
Denoting $\mathbf{M}=\frac{\gamma}{1+\gamma}\mathbf{M}_{i}$, we get the $\textit{monodomain equation}$:
$$
\begin{equation}
\nabla \cdot(\mathbf{M}\nabla v) =\chi\left( C_{m}\frac{ \partial v }{ \partial t } +I_\text{ion} \right) ,\quad \mathbf{X}\in \Omega,
\end{equation}
$$
with the boundary condition
$$
\begin{equation}
\mathbf{n}\cdot(\mathbf{M}\nabla v)=0,\quad\mathbf{X}\in \partial \Omega.
\end{equation}
$$
