As will be discussed in section \ref{sec:}, $T_{a}$ and $\eta$ will be used as the coupling from the electrophysiology to the mechanics. For now, let's denote that
$$
\begin{equation}
T_{a}=T_{a}\left( \mathbf{s},\lambda ,\frac{ \partial \lambda }{ \partial t }  \right),
\end{equation}
$$
where $\mathbf{s}$ are state variables defined in each cell (and in each point in the intracellular domain) and $\lambda$ is the stretch. Notice that $\mathbf{s}$ here differs from the deformed sheet axis $\mathbf{s}$.

The Land model details the active tension as
$$
\begin{equation}
T_{a}=h(\lambda)\frac{T_{ref}}{rs}((1+\zeta_{s})S+\zeta_{w}W),
\end{equation}
$$
where $T_\text{ref}$ and $rs$ are constants and
$$
\begin{align}
h(\lambda) & =\max(0,h'(\min(\lambda,1.2))), \\
h'(\lambda) & =1+\beta_{0}(\lambda+\min(\lambda,0.87)-1.87),
\end{align}
$$
where $\beta_{0}$ is also a constant. $W$ and $S$ represent the fraction of myosin binding sites pre- and post-powerstroke, respectively.
