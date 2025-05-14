We need to verify that our solver converges to a solution, so we will set up a problem with a known analytical solution to compare with approximate solutions using the solver described in \autoref{}. Let $\Omega$ be a cuboidal slab, on which we perform a uniaxial test. That is, we define a stretch ratio $\lambda$ along the $x$-axis, and as a result of incompressibility, the $y$-axis and $z$-axis will compress with the stretch ratio $\lambda^{-1/2}$. The deformation gradient will take the form $$
\begin{equation}
\mathbf{F}=\begin{bmatrix}
\lambda  & 0 & 0 \\
0 & \lambda^{-1/2} & 0 \\
 0& 0 & \lambda^{-1/2}
\end{bmatrix}.
\end{equation}
$$
We will need to compute the following invariants:
$$
\begin{align}
I_{1} & =  \mathrm{Tr}\mathbf{C}=\lambda^2+\frac{2}{\lambda}, \\
I_{4\mathbf{f}_{0}} & =\mathbf{f}_{0}\cdot(\mathbf{C}\mathbf{f}_{0})=\lambda^2.
\end{align}
$$


Let \(\Omega\) be a cuboidal slab, with fiber direction \(\mathbf{f}_{0}=\begin{bmatrix}1&0&0\end{bmatrix}^T\). We assume that the slab is transversely isotropic and incompressible, which leads to a diagonal deformation matrix of the form 
$$\begin{equation}
    \mathbf{F}=
    \begin{bmatrix}
        \lambda & 0 & 0 \\
        0 & \frac{1}{\sqrt{ \lambda }} & 0 \\
        0 & 0 & \frac{1}{\sqrt{ \lambda }} 
    \end{bmatrix},
\end{equation}
$$
and \(J=\det \mathbf{F}=1\). The right Cauchy-Green deformation
tensor becomes 
$$\begin{equation}
    \mathbf{C}=
        \begin{bmatrix}
            \lambda^2 & 0 & 0 \\
            0 & \frac{1}{\lambda} & 0 \\
            0 & 0 & \frac{1}{\lambda} 
        \end{bmatrix}.
\end{equation}$$

Then, the invariants simplify to 
$$\begin{align}
    I_{1} & =\mathrm{Tr}\mathbf{C}=\lambda^2+2\lambda^{-1}, \\
    I_{4\mathbf{f}_{0}} & =\mathbf{f}_{0}\cdot(\mathbf{C}\mathbf{f}_{0})=\lambda^2.
\end{align}$$

Substitution into the passive and active strain-energy functions
gives 
$$\begin{equation}
    \Psi_{p}(I_{1},I_{4\mathbf{f}_{0}})  = \frac{a}{2b}\bigg(e^{ b(\lambda^2 +2\lambda^{-1}-3) }-1\bigg)  + \frac{a_{f}}{2b_{f}}\bigg(e^{ b_{f}(\lambda^2-1)^2_{+}}-1\bigg).
\end{equation}
$$
The passive first Piola-Kirchoff stress tensor components are 
$$\begin{align}
    (\mathbf{P}_{p})_{11} 
    & =\frac{ \partial \Psi_{p} }{ \partial \lambda } +Jp(\mathbf{F}^{-T})_{11} \\
    & = \frac{a}{2}(2\lambda -2\lambda^{-2})e^{ b\left( \lambda^2 +2\lambda^{-1}-3 \right) }+ a_{f}(\lambda^2-1)_{+}2\lambda e^{ b_{f}(\lambda^2-1)^2_{+} }+\frac{Jp}{\lambda} \\
    & =a(\lambda-\lambda^{-2})e^{ b(\lambda^2+2\lambda^{-1}-3) }+2\lambda a_{f}(\lambda^2-1)_{+}e^{ b_{f}(\lambda^2-1)_{+}^2 }+p\lambda^{-1},\\
    (\mathbf{P}_{p})_{33}=(\mathbf{P}_{p})_{22} 
    & =\frac{ \partial \Psi_{p} }{ \partial \left( \frac{1}{\sqrt{ \lambda }} \right) }  + Jp(\mathbf{F}^{-T})_{22}\\
    & =\frac{ \partial \lambda }{ \partial \left( \frac{1}{\sqrt{ \lambda }} \right) } \frac{ \partial \Psi_{p} }{ \partial \lambda } +Jp(\mathbf{F}^{-T})_{22} \\
    & = (-2\lambda^{3/2})\left[ a(\lambda-\lambda^{-2})e^{ b(\lambda^2+2\lambda^{-1}-3) }+2\lambda a_{f}(\lambda^2-1)_{+}e^{ b_{f}(\lambda^2-1)_{+}^2 } \right] +p\sqrt{ \lambda },
\end{align}$$

where we have used the chain rule and 
$$\begin{equation}
    \frac{ \partial \lambda }{ \partial\left(  \frac{1}{\sqrt{ \lambda }} \right) } =\frac{ \partial \gamma^{-2} }{ \partial \gamma } =-2\gamma^{-3}=-2\lambda^{3/2}.
\end{equation}$$

The active Cauchy stress tensor is given by 
$$\begin{equation}
    \label{eq:0d_active_cauchy}
    \boldsymbol{\sigma}_{a}=\text{diag}\{T_{a}, \eta T_{a},\eta T_{a}\},
\end{equation}$$

and is also related to the first Piola-Kirchoff stress by 
$$\begin{equation}
    \label{eq:0d_active_piola}
    \mathbf{P}_{a}=J\boldsymbol{\sigma}_{a}\mathbf{F}^{-T}\implies \boldsymbol{\sigma}_{a}=\mathbf{P}_{a}\mathbf{F}^T.
\end{equation}$$
