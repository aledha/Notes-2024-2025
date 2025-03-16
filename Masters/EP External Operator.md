We let $M=\mathbf{I}$, $C_{m}=1$, and $\chi=1$ such that
$$
\begin{align}
\nabla \cdot(M\nabla v)  & =\chi C_{m}\frac{ \partial v }{ \partial t } +\chi I_\text{ion}-\chi I_\text{stim}, \\
\frac{ \partial v }{ \partial t } & =\nabla^2 v -I_\text{ion}+I_\text{stim}
\end{align}
$$
## Backward Euler
We have the system
$$
\begin{align}
\frac{\text{d}s}{\text{d}t}  & =v, \\
\frac{\text{d}v}{\text{d}t}  & =-s.
\end{align}
$$
The backwards Euler method on the system yields
$$
\begin{align}
s ^{n+1}-s^n  & =\Delta tv^{n+1}, \\
v^{n+1}-v^n & =\Delta ts ^{n+1}.
\end{align}
$$
