### Passive myocardium
With a local orthonormal coordinate system with fiber axis $\mathbf{f}_{0}$, sheet axis $\mathbf{s}_{0}$, and sheet-normal axis $\mathbf{n}_{0}$. The invariants are defined as
$$
\begin{align}
I_{1} & =  \mathrm{Tr}\mathbf{C}, \\
I_{4\mathbf{f}_{0}} & =\mathbf{f}_{0}\cdot(\mathbf{C}\mathbf{f}_{0}), \\
I_{4\mathbf{s}_{0}} & =\mathbf{s}_{0}\cdot(\mathbf{C}\mathbf{s}_{0}), \\
I_{4\mathbf{n}_{0}} & =\mathbf{n}_{0}\cdot(\mathbf{C}\mathbf{n}_{0}), \\ 
I_{8\mathbf{f}_{0}\mathbf{s}_{0}} & =\mathbf{s}_{0}\cdot(\mathbf{C}\mathbf{f}_{0}).
\end{align}
$$
$I_{4\mathbf{f}_{0}}$ can be interpreted as the stretch along the fibers, $I_{4\mathbf{s}_{0}}$ can be interpreted as the stretch along the sheet. \eqref{} can be rewritten as
$$
\begin{equation}
I_{8\mathbf{f}_{0}\mathbf{s}_{0}}=\mathbf{s}_{0}\cdot(\mathbf{C}\mathbf{f}_{0})=\mathbf{s}_{0}\cdot(\mathbf{F}^T\mathbf{F}\mathbf{f}_{0})=(\mathbf{F}\mathbf{s}_{0})\cdot(\mathbf{F}\mathbf{f}_{0}),
\end{equation}
$$
which indicates that $I_{8\mathbf{f}_{0}\mathbf{s}_{0}}$ can be interpreted as a measure on the angle between the deformed sheet axis and the deformed fiber axis. The sheet axis and the fiber axis are orthonormal in the reference configuration.
$$
\begin{align}
I_{4\mathbf{f}_{0}}+I_{4\mathbf{s}_{0}}+I_{4\mathbf{n}_{0}} & =\mathbf{f}_{0}\cdot(\mathbf{C}\mathbf{f}_{0})+\mathbf{s}_{0}\cdot(\mathbf{C}\mathbf{s}_{0})+\mathbf{n}_{0}\cdot(\mathbf{C}\mathbf{n}_{0}) \\
 & =(\mathbf{f}_{0}+\mathbf{s}_{0}+\mathbf{n}_{0})\cdot \mathbf{C}(\mathbf{f}_{0}+\mathbf{s}_{0}+\mathbf{n}_{0})
\end{align}
$$

The orthotropic Holzapfel-Ogden model is
$$
\begin{align}
\Psi_{p}(I_{1},I_{4\mathbf{f}_{0}},I_{4\mathbf{s}_{0}},I_{8\mathbf{f}_{0}\mathbf{s}_{0}}) = & \frac{a}{2b}\bigg(e^{ b(I_{1}-3) }-1\bigg) \\
 & + \frac{a_{f}}{2b_{f}}\bigg(e^{ b_{f}(I_{4\mathbf{f}_{0}}-1)^2_{+}}-1\bigg)  \\
 & + \frac{a_{s}}{2b_{s}}\bigg(e^{ b_{s}(I_{4\mathbf{s}_{0}}-1)_{+}^2}-1\bigg)  \\
 & + \frac{a_{fs}}{2b_{fs}}\bigg(e^{ b_{fs}I_{8\mathbf{f}_{0}\mathbf{s}_{0}}^2}-1\bigg).  \\
\end{align}
$$
If the material is transversely isotropic, we may set $a_{fs}=b_{fs}=a_{s}=b_{s}=0$ ( #todo: show this), simplifying \eqref{} to
$$
\begin{equation}
\Psi_{p}(I_{1},I_{4\mathbf{f}_{0}})= \frac{a}{2b}\bigg(e^{ b(I_{1}-3) }-1\bigg)  + \frac{a_{f}}{2b_{f}}\bigg(e^{ b_{f}(I_{4\mathbf{f}_{0}}-1)^2_{+}}-1\bigg)
\end{equation}
$$

### Active myocardium
#### Active stress formulation
The classical three element Hill muscle model will be used
![[Pasted image 20250110104738.png|400]]
Assume that the Cauchy stress can be written as a sum of a passive contribution and an active contribution:
$$
\begin{equation}
\boldsymbol{\sigma}=\boldsymbol{\sigma}_{p}+\boldsymbol{\sigma}_{a}.
\end{equation}
$$
The passive stress depends on the material model:
$$
\begin{equation}
\boldsymbol{\sigma}_{p}=\frac{1}{J}\frac{ \partial \Psi_{p}(\mathbf{F}) }{ \partial \mathbf{F} } \mathbf{F}^T,
\end{equation}
$$
while the active stress is
$$
\begin{equation}
\boldsymbol{\sigma}_{a}=\sigma_{ff}\mathbf{f}\otimes \mathbf{f}+\sigma_{ss}\mathbf{s}\otimes \mathbf{s}+\sigma_{nn}\mathbf{n}\otimes \mathbf{n},
\end{equation}
$$
where $\sigma_{ff},\sigma_{ss},$ and $\sigma_{nn}$ are the components of the active stress in the fiber, sheet, and normal direction, respectively. 

Although the sheet and normal active stresses are non-negligible, a common simplification is to collect these to one variable:
$$
\begin{equation}
\boldsymbol{\sigma}_{a}=T_{a}(\mathbf{f}\otimes \mathbf{f}+\eta(\mathbf{s}\otimes \mathbf{s}+\mathbf{n}\otimes \mathbf{n})),
\end{equation}
$$
where $T_{a}$ represent the total active stress and $\eta$ represents the active stress in the transverse direction. We will assume that $\eta=0$ ( #todo  reason) such that
$$
\begin{equation}
\boldsymbol{\sigma}_{a}=T_{a}\mathbf{f}\otimes \mathbf{f}.
\end{equation}
$$

Using
$$
\begin{equation}
\frac{ \partial I_{4\mathbf{f}_{0}} }{ \partial \mathbf{F} } =\frac{ \partial (\mathbf{f}_{0}\cdot \mathbf{C}\mathbf{f}_{0}) }{ \partial \mathbf{F} } =2\mathbf{f}\otimes \mathbf{f}_{0}\implies \mathbf{f}\otimes \mathbf{f}=\frac{1}{2}\frac{ \partial I_{4\mathbf{f}_{0}} }{ \partial \mathbf{F} } \mathbf{F}^T,
\end{equation}
$$
on \eqref{} gives
$$
\begin{equation}
\boldsymbol{\sigma}_{a}=\frac{T_{a}}{2}\frac{ \partial I_{4\mathbf{f}_{0}} }{ \partial \mathbf{F}}\mathbf{F}^T.
\end{equation}
$$
To find a strain-energy function that satisfies $\boldsymbol{\sigma}_{a}=\frac{1}{J}\frac{ \partial \Psi(\mathbf{F}) }{ \partial \mathbf{F} }\mathbf{F}^T$, we set
$$
\begin{equation}
\Psi_{a}(\mathbf{F})=\Psi_{a}(I_{4\mathbf{f}_{0}})=\frac{JT_{a}}{2} (I_{4\mathbf{f}_{0}}-1),
\end{equation}
$$
where the invariant $I_{4\mathbf{f}_{0}}$ is subtracted by 1 to fulfill the requirement that $\Psi_{a}(\mathbf{I})=0$.

(The active stress formulation is not sufficient to describe tissue deformations (Rossi, p.5).)

#### for eta≠0
The relation $I_{1}=I_{4\mathbf{f}_{0}}+I_{4\mathbf{s}_{0}}+I_{4\mathbf{n}_{0}}$ allows \eqref{} to be rewritten to
$$
\begin{equation}
\boldsymbol{\sigma}_{a}=\frac{T_{a}}{2}\left( \frac{ \partial I_{4\mathbf{f}_{0}} }{ \partial \mathbf{F} }+\eta \left( \frac{ \partial I_{1} }{ \partial \mathbf{F} } -\frac{ \partial I_{4\mathbf{f}_{0}} }{ \partial \mathbf{F} } \right)  \right) \mathbf{F}^T.
\end{equation}
$$

### Incompressibility
During the contraction of the myocardium, blood is squeezed out, resulting in a volume loss of 2-4%. Hence, the myocardium is a compressible material. However, it is common to assume that the myocardium is incompressible for numerical ease, such that
$$
\begin{equation}
J=\det \mathbf{F}=1.
\end{equation}
$$
In order to impose the incompressibility condition, we modify the strain-energy function to
$$
\begin{equation}
\Psi=\Psi_{p}+\Psi_{a}+p(J-1),
\end{equation}
$$
where $p$ is a Lagrange multiplier.

We can differentiate \eqref{} with respect to $\mathbf{F}$ to get an expression the first Piola-Kirchoff stress tensor:
$$
\begin{equation}
\mathbf{P}=\frac{ \partial \Psi_{p} (\mathbf{F})}{ \partial \mathbf{F} } +\frac{ \partial \Psi_{a}(\mathbf{F}) }{ \partial \mathbf{F} } + Jp\mathbf{F}^{-T}.
\end{equation}
$$
Let's denote
$$
\begin{equation}
\mathbf{P}=\mathbf{P}_{p}+\mathbf{P}_{a},
\end{equation}
$$
where $\mathbf{P}_{p}=\frac{ \partial \Psi_{p}(\mathbf{F}) }{ \partial \mathbf{F} }+Jp\mathbf{F}^{-T}$ and $\mathbf{P}_{a}=\frac{ \partial \Psi_{a}(\mathbf{F}) }{ \partial \mathbf{F} }$.

## Force-balance equation
#todo derive
$$
\begin{equation}
\nabla \cdot \mathbf{P}=\boldsymbol{0},\qquad \mathbf{X}\in\Omega.
\end{equation}
$$

### Boundary conditions
Let the surface of the domain be decomposed as $\partial\Omega=\partial\Omega_{D} \cup \partial\Omega_{N}$, where $\partial\Omega_{D}$ denotes the boundary where we will apply a Dirichlet condition to the displacement $\mathbf{u}$, and $\partial\Omega_{N}$ denotes the boundary where we will apply a Neumann condition on the flux of the first Piola-Kirchhoff stress tensor.

We will consider two types of Dirichlet conditions, the first being
$$
\begin{equation}
\mathbf{u}=\boldsymbol{0}, \qquad  \mathbf{X} \in \partial\Omega_{D},%\label{eq:type1dir}
\end{equation}
$$
where all coordinates of $\mathbf{u}$ are fixed. This will be referred to as a type 1 Dirichlet condition. Type 2 Dirichlet conditions are of the form
$$
\begin{equation}
u_{i}=0,\qquad \mathbf{X}\in \partial\Omega_{D},%\label{eq:type2dir}
\end{equation}
$$
where $u_{i}$ is one of the coordinates of $\mathbf{u}=(u_{1},u_{2},u_{3})$. Notice that three type 2 Dirichlet conditions must be enforced to fix the geometry.

Both types of Dirichlet conditions may be described by
$$
\begin{equation}
\mathbf{u}=\mathbf{u}_{D}, \qquad  \mathbf{X} \in \partial\Omega_{D}.%\label{eq:udir}
\end{equation}
$$
The Neumann conditions are
$$
\begin{equation}
\mathbf{P}\mathbf{N}=\mathbf{T},\qquad \mathbf{X}\in \partial\Omega_{N},%\label{eq:mechneumann}
\end{equation}
$$
where $\mathbf{N}$ is the outward normal vector in the reference domain, and $\mathbf{T}$ is the desired traction.

## Summary of Mechanical Model
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
%\label{eq:activepsi}
\Psi_{a}(I_{4\mathbf{f}_{0}}) & =\frac{JT_{a}}{2} (I_{4\mathbf{f}_{0}}-1), \\
%\label{eq:passivepsi}
\Psi_{p}(I_{1},I_{4\mathbf{f}_{0}}) & = \frac{a}{2b}\bigg(e^{ b(I_{1}-3) }-1\bigg)  + \frac{a_{f}}{2b_{f}}\bigg(e^{ b_{f}(I_{4\mathbf{f}_{0}}-1)^2_{+}}-1\bigg).
\end{align}
$$
