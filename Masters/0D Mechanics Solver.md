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
\Psi_{p}(I_{1},I_{4\mathbf{f}_{0}}) & = \frac{a}{2b}\bigg(e^{ b(I_{1}-3) }-1\bigg)  + \frac{a_{f}}{2b_{f}}\bigg(e^{ b_{f}(I_{4\mathbf{f}_{0}}-1)^2_{+}}-1\bigg).
\end{align}
$$
$$
\begin{align}
I_{1} & =  \mathrm{Tr}\mathbf{C} \\
I_{4\mathbf{f}_{0}} & =\mathbf{f}_{0}\cdot(\mathbf{C}\mathbf{f}_{0}), \\
I_{4\mathbf{s}_{0}} & =\mathbf{s}_{0}\cdot(\mathbf{C}\mathbf{s}_{0}), \\
I_{4\mathbf{n}_{0}} & =\mathbf{n}_{0}\cdot(\mathbf{C}\mathbf{n}_{0}), \\ 
I_{8\mathbf{f}_{0}\mathbf{s}_{0}} & =\mathbf{s}_{0}\cdot(\mathbf{C}\mathbf{f}_{0}).
\end{align}
$$

---
We assume that the fibre direction is $\mathbf{f}_{0}=\begin{bmatrix}1&0&0\end{bmatrix}^T$ in the slab, and that there is a uniform electrical activation across the slab. Since the slab is transversely isotropic and incompressible, this leads to a diagonal deformation matrix of the form
$$
\begin{equation}
\mathbf{F}=\begin{bmatrix}
\lambda & 0 & 0 \\
0 & \frac{1}{\lambda} & 0 \\
0 & 0 & \frac{1}{\lambda} 
\end{bmatrix},
\end{equation}
$$
and the right Cauchy-Green deformation tensor becomes
$$
\begin{equation}
\mathbf{C}=\begin{bmatrix}
\lambda^2 & 0 & 0 \\
0 & \frac{1}{\lambda^2} & 0 \\
0 & 0 & \frac{1}{\lambda^2} 
\end{bmatrix}.
\end{equation}
$$
Then, the invariants simplify to
$$
\begin{align}
I_{1} & =\mathrm{Tr}\mathbf{C}=\lambda^2+\frac{2}{\lambda ^2}, \\
I_{4\mathbf{f}_{0}} & =\mathbf{f}_{0}\cdot(\mathbf{C}\mathbf{f}_{0})=\lambda^2.
\end{align}
$$

