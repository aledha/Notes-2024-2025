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




The active strain-energy density function is 
$$
\begin{align}
    L_{1}(\lambda,p;T_{a}) & =T_{a}+a(\lambda^2-\lambda^{-1})e^{ b(\lambda^2+2\lambda^{-1}-3) }+2\lambda^2 a_{f}(\lambda^2-1)_{+}e^{ b_{f}(\lambda^2-1)_{+}^2 }+p, \\
    L_{2}(\lambda,p) & =2a(\lambda^2-\lambda^{-1})e^{ b(\lambda^2+2\lambda^{-1}-3) }+4\lambda^2 a_{f}(\lambda^2-1)_{+}e^{ b_{f}(\lambda^2-1)_{+}^2 }-p.
\end{align}
$$

$$
\begin{align}
%\label{eq:activepsi}
\Psi_{a}(I_{4\mathbf{f}_{0}}) & =\frac{JT_{a}}{2} (I_{4\mathbf{f}_{0}}-1), \\
%\label{eq:passivepsi}
\Psi_{p}(I_{1},I_{4\mathbf{f}_{0}}) & = \frac{a}{2b}\bigg(e^{ b(I_{1}-3) }-1\bigg)  + \frac{a_{f}}{2b_{f}}\bigg(e^{ b_{f}(I_{4\mathbf{f}_{0}}-1)^2_{+}}-1\bigg).
\end{align}
$$

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