The hyperelastic, incompressible model can be summarized as
$$
\begin{align}
\nabla \cdot \mathbf{P} & =0,\qquad & \mathbf{X}\in\Omega, \\
\mathbf{u} & =\mathbf{u}_{D}, & \mathbf{X}\in \partial\Omega_{D}, \\
\mathbf{P}\mathbf{N} & =\mathbf{T}, & \mathbf{X}\in \partial\Omega_{N}, \\
\mathbf{P} & =\mathbf{P}_{p}+\mathbf{P}_{a} \\
\mathbf{P}_{p} & =\frac{ \partial \Psi_{p}(\mathbf{F}) }{ \partial \mathbf{F} }+Jp\mathbf{F}^{-T}, \\
\mathbf{P}_{a} & =\frac{ \partial \Psi_{a}(\mathbf{F}) }{ \partial \mathbf{F} },
\end{align}
$$
where the active and passive strain-energy functions are defined as
$$
\begin{align}
\Psi_{a}(I_{4\mathbf{f}_{0}}) & =\frac{JT_{a}}{2} (I_{4\mathbf{f}_{0}}-1), \\
\Psi_{p}(I_{1},I_{4\mathbf{f}_{0}}) & = \frac{a}{2b}\bigg(e^{ b(I_{1}-3) }-1\bigg)  + \frac{a_{f}}{2b_{f}}\bigg(e^{ b_{f}(I_{4\mathbf{f}_{0}}-1)^2_{+}}-1\bigg),
\end{align}
$$
and the
$$
\begin{align}
I_{1} & =  \mathrm{Tr}\mathbf{C} \\
I_{4\mathbf{f}_{0}} & =\mathbf{f}_{0}\cdot(\mathbf{C}\mathbf{f}_{0}), \\
I_{4\mathbf{P}_{0}} & =\mathbf{P}_{0}\cdot(\mathbf{C}\mathbf{P}_{0}), \\
I_{4\mathbf{n}_{0}} & =\mathbf{n}_{0}\cdot(\mathbf{C}\mathbf{n}_{0}), \\ 
I_{8\mathbf{f}_{0}\mathbf{P}_{0}} & =\mathbf{P}_{0}\cdot(\mathbf{C}\mathbf{f}_{0}).
\end{align}
$$

---

We assume that the fibre direction is $\mathbf{f}_{0}=\begin{bmatrix}1&0&0\end{bmatrix}^T$ in the slab, and that there is a uniform electrical activation across the slab. We further assume that the slab is transversely isotropic and incompressible, which leads to a diagonal deformation matrix of the form
$$
\begin{equation}
\mathbf{F}=\begin{bmatrix}
\lambda & 0 & 0 \\
0 & \frac{1}{\sqrt{ \lambda }} & 0 \\
0 & 0 & \frac{1}{\sqrt{ \lambda }} 
\end{bmatrix},
\end{equation}
$$
and $J=\det \mathbf{F}=1$. The right Cauchy-Green deformation tensor becomes
$$
\begin{equation}
\mathbf{C}=\begin{bmatrix}
\lambda^2 & 0 & 0 \\
0 & \frac{1}{\lambda} & 0 \\
0 & 0 & \frac{1}{\lambda} 
\end{bmatrix}.
\end{equation}
$$
Then, the invariants simplify to
$$
\begin{align}
I_{1} & =\mathrm{Tr}\mathbf{C}=\lambda^2+2\lambda^{-1}, \\
I_{4\mathbf{f}_{0}} & =\mathbf{f}_{0}\cdot(\mathbf{C}\mathbf{f}_{0})=\lambda^2.
\end{align}
$$

Substitution into the passive and active strain-energy functions gives
$$
\begin{equation}
\Psi_{p}(I_{1},I_{4\mathbf{f}_{0}})  = \frac{a}{2b}\bigg(e^{ b(\lambda^2 +2\lambda^{-1}-3) }-1\bigg)  + \frac{a_{f}}{2b_{f}}\bigg(e^{ b_{f}(\lambda^2-1)^2_{+}}-1\bigg).
\end{equation}
$$
The passive stress components are
$$
\begin{align}
(\mathbf{P}_{p})_{11} & =\frac{ \partial \Psi_{p} }{ \partial \lambda } +Jp(\mathbf{F}^{-T})_{11} \\
 & = \frac{a}{2}(2\lambda -2\lambda^{-2})e^{ b\left( \lambda^2 +2\lambda^{-1}-3 \right) }+ a_{f}(\lambda^2-1)_{+}2\lambda e^{ b_{f}(\lambda^2-1)^2_{+} }+\frac{Jp}{\lambda} \\
  & =a(\lambda-\lambda^{-2})e^{ b(\lambda^2+2\lambda^{-1}-3) }+2\lambda a_{f}(\lambda^2-1)_{+}e^{ b_{f}(\lambda^2-1)_{+}^2 }+p\lambda^{-1},\\
(\mathbf{P}_{p})_{22}=(\mathbf{P}_{p})_{33} & =\frac{ \partial \Psi_{p} }{ \partial \left( \frac{1}{\sqrt{ \lambda }} \right) }  + Jp(\mathbf{F}^{-T})_{22}\\
 & =\frac{ \partial \lambda }{ \partial \left( \frac{1}{\sqrt{ \lambda }} \right) } \frac{ \partial \Psi_{p} }{ \partial \lambda } +Jp(\mathbf{F}^{-T})_{22} \\
 & = (-\lambda^{3/2})\left[ a(\lambda-\lambda^{-2})e^{ b(\lambda^2+2\lambda^{-1}-3) }+2\lambda a_{f}(\lambda^2-1)_{+}e^{ b_{f}(\lambda^2-1)_{+}^2 } \right] +p\sqrt{ \lambda }
\end{align}
$$

$$
\begin{equation}
\frac{ \partial \lambda }{ \partial\left(  \frac{1}{\sqrt{ \lambda }} \right) } =\frac{ \partial \gamma^{-2} }{ \partial \gamma } =-2\gamma^{-3}=-\lambda^{3/2}.
\end{equation}
$$

We have that the active Cauchy stress tensor is given by
$$
\begin{equation}
\boldsymbol{\sigma}_{a}=\text{diag}\{T_{a}, \eta T_{a},\eta T_{a}\},
\end{equation}
$$
and is also related to the first Piola-Kirchoff stress by
$$
\begin{equation}
\mathbf{P}_{a}=J\boldsymbol{\sigma}_{a}\mathbf{F}^{-T}\implies \boldsymbol{\sigma}_{a}=\mathbf{P}_{a}\mathbf{F}^T.
\end{equation}
$$

We assume that the slab is unloaded, and we ignore body and inertia forces, such that the active and passive stresses must balance at all points:
$$
\begin{equation}
\mathbf{P}=\mathbf{P}_{p}+\mathbf{P}_{a}=0.
\end{equation}
$$
Combination of \eqref{} gives
$$
\begin{equation}
\text{diag}\{T_{a},\eta T_{a},\eta T_{a}\}=-\frac{1}{J}\mathbf{P}_{p}\mathbf{F}^T
\end{equation}
$$
Taking the above equation for the first component gives 
$$
\begin{align}
T_{a} & =-\left[ a(\lambda-\lambda^{-2})e^{ b(\lambda^2+2\lambda^{-1}-3) }+2\lambda a_{f}(\lambda^2-1)_{+}e^{ b_{f}(\lambda^2-1)_{+}^2 }+p\lambda^{-1} \right] \lambda \\
 & =-a(\lambda^2-\lambda^{-1})e^{ b(\lambda^2+2\lambda^{-1}-3) }-2\lambda^2 a_{f}(\lambda^2-1)_{+}e^{ b_{f}(\lambda^2-1)_{+}^2 }-p,
\end{align}
$$
and the second (and third) component is
$$
\begin{align}
\eta T_{a} & = - \left[ (-\lambda^{3/2})\left[ a(\lambda-\lambda^{-2})e^{ b(\lambda^2+2\lambda^{-1}-3) }+2\lambda a_{f}(\lambda^2-1)_{+}e^{ b_{f}(\lambda^2-1)_{+}^2 } \right] +p\sqrt{ \lambda } \right] \frac{1}{\sqrt{ \lambda }} \\
 & =a(\lambda^2-\lambda^{-1})e^{ b(\lambda^2+2\lambda^{-1}-3) }+2\lambda^2 a_{f}(\lambda^2-1)_{+}e^{ b_{f}(\lambda^2-1)_{+}^2 }-p
\end{align}
$$
