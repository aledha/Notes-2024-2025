$$
\begin{align}
J=\mathbf{M}E=-\mathbf{M}\nabla u
\end{align}
$$
$$
\begin{align}
J_{i} & =-\mathbf{M}_{i}\nabla u_{i} \\
J_{e} & =-\mathbf{M}_{e}\nabla u_{e}
\end{align}
$$

$\mathbf{M}_{e}=\gamma \mathbf{M}_{i}$ 

$\mathbf{M}=\frac{\gamma}{1+\gamma}\mathbf{M}_{i}$
$$
\begin{equation}
\nabla \cdot(\mathbf{M}\nabla v)=\chi C_{m}\frac{ \partial v }{ \partial t } +\chi I_\text{ion}-\chi I_\text{stim}
\end{equation}
$$

$$
\begin{equation}
\mathbf{n}\cdot(\mathbf{M}\nabla v)=0
\end{equation}
$$
opsplit:
$$
\begin{align}
\frac{ \partial y }{ \partial t }  & =L_{1}(y) \\
\frac{ \partial y }{ \partial t }  & =L_{2}(y)
\end{align}
$$

$$
\begin{align}
\frac{ \partial v }{ \partial t }  & = \frac{1}{\chi C_{m}}\nabla \cdot(\mathbf{M}\nabla v)-\frac{1}{C_{m}}I_\text{ion}(v,\mathbf{s})+\frac{1}{C_{m}}I_\text{stim} \\
\frac{ \partial \mathbf{s} }{ \partial t }  & =f(\mathbf{s},v,t)
\end{align}
$$
$$
\begin{equation}
\implies \qquad \begin{aligned}
(1)\quad&\begin{cases}
\frac{ \partial v }{ \partial t } =-\frac{1}{C_{m}}I_\text{ion}(v,\mathbf{s}) \\
\frac{ \partial \mathbf{s} }{ \partial t } =\mathbf{f}(\mathbf{s},v,t)
\end{cases}\\
\\
(2)\quad&\begin{cases}
\frac{ \partial v }{ \partial t }  =\frac{1}{\chi C_{m}}\nabla \cdot(\mathbf{M}\nabla v)+\frac{1}{C_{m}}I_\text{stim} \\
\frac{ \partial \mathbf{s} }{ \partial t }  =\boldsymbol{0}
\end{cases}
\end{aligned}
\end{equation}
$$






$$
\begin{align}
\frac{ \partial \mathbf{s} }{ \partial t }  & =\mathbf{f}(\mathbf{s},v,t) \\
I_\text{ion} & =I_\text{ion}(v,\mathbf{s})
\end{align}
$$






$$
\begin{align}
\nabla \cdot(\mathbf{M}_{i}\nabla v)+\nabla \cdot(\mathbf{M}_{i}\nabla u_{e}) & =\chi C_{m}\frac{ \partial v }{ \partial t } +\chi I_\text{ion}-\chi I_\text{stim} \\
\nabla \cdot(\mathbf{M}_{i}\nabla v)+\nabla \cdot((\mathbf{M}_{i}+\mathbf{M}_{e})\nabla u_{e}) & =0
\end{align}
$$

$$
\begin{align}
\mathbf{n}\cdot(\mathbf{M}_{i}\nabla v+\mathbf{M}_{i}\nabla u_{e}) & =0 \\
\mathbf{n}\cdot(\mathbf{M}_{e}\nabla u_{e}) & =0
\end{align}
$$
0d:
$$
\begin{align}
    \nabla \cdot(\mathbf{M}\nabla v) & =\chi C_{m}\frac{ \partial v }{ \partial t } +\chi I_\text{ion}(v,\mathbf{s})-\chi I_\text{stim}, & \mathbf{x}\in \Omega , \\
    \frac{ \partial \mathbf{s} }{ \partial t } & =f(\mathbf{s},v,\lambda,\dot{\lambda},t), & \mathbf{x}\in \Omega, \\
    \mathbf{n}\cdot(\mathbf{M}\nabla v) & =0, &\mathbf{x}\in \partial\Omega , \\
\nabla \cdot \mathbf{P} & =0, & \mathbf{x}\in \Omega, \\
\mathbf{u} & =\mathbf{u}_{D}, & \mathbf{x}\in \partial \Omega_{D}, \\
\mathbf{P}\mathbf{N} & =\mathbf{T}, & \mathbf{x}\in \partial \Omega_{N}.
\end{align}
$$
$\implies\nabla v=\boldsymbol{0}\quad\forall t$

$$
\begin{equation}
\implies \qquad \frac{ \partial v }{ \partial t } =\frac{1}{C_{m}}I_\text{stim}-\frac{1}{C_{m}}I_\text{ion}(v,\mathbf{s})
\end{equation}
$$

$$
\begin{equation}
\implies \qquad \frac{ \partial \mathbf{s} }{ \partial t } =f(\mathbf{s},t, \lambda, \dot{\lambda})
\end{equation}
$$

$$
\begin{align}
  F_{1}(\lambda,p;T_{a}) & =T_{a}+a(\lambda^2-\lambda^{-1})e^{ b(\lambda^2+2\lambda^{-1}-3) }+2\lambda^2 a_{f}(\lambda^2-1)_{+}e^{ b_{f}(\lambda^2-1)_{+}^2 }+p, \\
    F_{2}(\lambda,p) & =2a(\lambda^2-\lambda^{-1})e^{ b(\lambda^2+2\lambda^{-1}-3) }+4\lambda^2 a_{f}(\lambda^2-1)_{+}e^{ b_{f}(\lambda^2-1)_{+}^2 }-p.
\end{align}
$$

