As will be discussed in section \ref{sec:}, $T_{a}$ and $\eta$ will be used as the coupling from the electrophysiology to the mechanics. For now, let's denote that
$$
\begin{equation}
T_{a}=T_{a}\left( \mathbf{s},\lambda ,\frac{ \partial \lambda }{ \partial t }  \right),
\end{equation}
$$
where $\mathbf{s}$ are state variables defined in each cell (and in each point in the intracellular domain) and $\lambda$ is the stretch. Notice that $\mathbf{s}$ here differs from the deformed sheet axis $\mathbf{s}$.

## Land model
After the intracellular calcium is released


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
where $\beta_{0}$ is also a constant.  $W$ and $S$ represent the fraction of myosin binding sites pre- and post-powerstroke, respectively. $\zeta_{s}$ and $\zeta_{w}$ represent the distortion of crossbridges in the $S$ and $W$ states, respectively.

The distortions are modeled as
$$
\begin{align}
\frac{\text{d}\zeta_{s}}{\text{d}t}  & =A_{s}\frac{\text{d}\lambda}{\text{d}t} -c_{s}\zeta_{s}, \\
\frac{\text{d}\zeta_{w}}{\text{d}t}  & =A_{w}\frac{\text{d}\lambda}{\text{d}t} -c_{w}\zeta_{w},
\end{align}
$$
where $A_{s}$, $c_{s}$, $A_{w}$, and $c_{w}$ are constants.

For myosin to bind to actin, the binding site must be in an unblocked state. 
The transition between the fraction of myosin binding sites pre- and post-powerstroke are modeled by
$$
\begin{align}
\frac{\text{d}W}{\text{d}t}  & =k_\text{uw}U-k_\text{wu}W-k_\text{ws}W-\gamma _\text{wu}W, \\
\frac{\text{d}S}{\text{d}t}  & =k_\text{ws}W-k_\text{su}S-\gamma _\text{su}S,
\end{align}
$$
where 