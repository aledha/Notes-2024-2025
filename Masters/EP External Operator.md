We let $M=\mathbf{I}$, $C_{m}=1$, and $\chi=1$ such that
$$
\begin{align}
\nabla \cdot(M\nabla v)  & =\chi C_{m}\frac{ \partial v }{ \partial t } +\chi I_\text{ion}-\chi I_\text{stim}, \\
\frac{ \partial v }{ \partial t } & =\nabla^2 v -I_\text{ion}+I_\text{stim}
\end{align}
$$
$\theta$-method to discretize in time:
$$
\begin{align}
\frac{v^{n+1}-v^n }{\Delta t} & =\theta \nabla ^2v^{n+1}+(1-\theta)\nabla^2v^n-I_\text{ion}+I_{\text{stim}} \\
v^{n+1}-\theta \Delta t \nabla^2v^{n+1} & =v^n +(1-\theta)\Delta t\nabla^2v^n-\Delta tI_\text{ion}+\Delta tI_\text{stim}
\end{align}
$$
Find $\phi \in V$ such that
$$
\begin{align}
\int_{\Omega }\phi (v^{n+1}-\theta \Delta t \nabla^2v^{n+1})\,\text{d} \mathbf{x} & =\int_{\Omega }\phi(v^n +(1-\theta)\Delta t\nabla^2v^n-\Delta tI_\text{ion}+\Delta tI_\text{stim})\,\text{d} \mathbf{x} \\
\int_{\Omega}(\phi v^{n+1}+\theta \Delta t(\nabla \phi \cdot \nabla v^{n+1}))\,\text{d} \mathbf{x} & =\int_{\Omega }(\phi v^n -(1-\theta)\Delta t(\nabla \phi \cdot\nabla v^n)-\Delta tI_\text{ion}\phi+\Delta tI_\text{stim}\phi)\,\text{d} \mathbf{x}
\end{align}
$$
