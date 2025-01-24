## Kinematics
* *Reference configuration*: 
	* $\Omega\equiv\chi_{0}(\mathcal{B})$
	* Coordinate $\mathbf{X}\in\Omega$
* *Current configuration*: 
	* $\omega\equiv\chi(\mathcal{B})$
	* Coordinate $\mathbf{x}\in\omega$
* A common convention is to denote a quantity in the reference configuration with a capitalized symbol, while denoting a quantity in the current configuration with a non-capitalized symbol. This convention will be used in this paper.
* Deformation mapping from reference to current:
	* $\mathbf{x}=\phi(\mathbf{X})$
	* $\phi:\Omega\to\omega$
	* smooth enough, injective (except boundary), and orientation preserving
* Deformation gradient $\mathbf{F}=\nabla_{\mathbf{X}}\phi=\text{Grad}\mathbf{x}$
	* $\mathbf{F}=\frac{ \partial \mathbf{x} }{ \partial \mathbf{X} }$.
	* Grad: derivative with respect to reference coordinates $\mathbf{X}$.
	* $\mathbf{F}\in \text{Lin}^+$, 
		* where $\text{Lin}^+$ is the space of linear transformations with strictly positive determinant.
		* Deformation does not create voids: $J=\det \mathbf{F}≠0$.
	* (Inverse function theorem) Implies that there exists an inverse deformation mapping $\phi^{-1}:\omega\to\Omega$.
		* $\mathbf{X}=\phi^{-1}(\mathbf{x})$
* Local deformation first order approximation
	* $\mathbf{x}+\,\text{d}\mathbf{x}=\phi(\mathbf{X}+\,\text{d}\mathbf{X})\approx\phi(\mathbf{X})+\frac{ \partial \phi(X) }{ \partial \mathbf{X} }\,\text{d}\mathbf{X}=\mathbf{x}+\mathbf{F}\,\text{d}\mathbf{X}$
* Displacement field
	* $\mathbf{u}=\mathbf{x}-\mathbf{X}$
	* $\mathbf{F}=\text{Grad}\mathbf{x}=\text{Grad}\mathbf{u}+\text{Grad}\mathbf{X}=\text{Grad}\mathbf{u}+\mathbf{I}$
* Right Cauchy-Green deformation tensor $\mathbf{C}=\mathbf{F}^T\mathbf{F}$
* Left Cauchy-Green deformation tensor $\mathbf{B}=\mathbf{F}\mathbf{F}^T$
* Green-Lagrange strain tensor $\mathbf{E}=\frac{1}{2}(\mathbf{C}-\mathbf{I})$
* Determinant of deformation gradient $J=\det \mathbf{F}$.
![[Pasted image 20250109130411.png]]

A vector $d\mathbf{X}$ in the reference configuration will be deformed to the vector $d\mathbf{x}$ in the current configuration such that $\text{ d}\mathbf{x}=\mathbf{F}\text{ d}\mathbf{X}$. Thus, an infinitesimal volume $\,\text{d}v$ in the current configuration deformed from the reference volume $\,\text{d}V$ has the relation 
$$
\begin{equation}
\text{ d} v=\det (\mathbf{F})\text{ d} V.
\end{equation}
$$
This can be rewritten using the infinitesimal surface elements $\,\text{d}s$ and $\,\text{d}S$, with the outer normal vectors $\mathbf{n}$ and $\mathbf{N}$.
$$
\begin{align}
\,\text{d} s\mathbf{n}\,\text{d} \mathbf{x} & =\,\text{d} v=\det(\mathbf{F})\,\text{d}  V=\det(\mathbf{F})\,\text{d}  S\mathbf{N}\,\text{d} \mathbf{X} \\
 \,\text{d} s\mathbf{n}\mathbf{F}\,\text{d} \mathbf{X} & =\det(\mathbf{F})\,\text{d} S\mathbf{N}\,\text{d} \mathbf{X}  \\
\,\text{d} s\mathbf{F}^T\mathbf{n} & =\det(\mathbf{F})\,\text{d} S\mathbf{N} \\
\,\text{d} s\mathbf{n} & =\det(\mathbf{F})\,\text{d} S \mathbf{F}^{-T}\mathbf{N},
\end{align}
$$
which is *Nanson's formula*.

**Cauchy's momentum equation:**
$$
\begin{equation}
\nabla \cdot\sigma+\mathbf{b}=\rho \mathbf{\dot{v}}.
\end{equation}
$$Often the contribution from $\mathbf{b}$ and $\rho \mathbf{\dot{v}}$ are considered negligible compared to $\nabla \cdot\sigma$ such that the force balance equations can be stated as
$$
\begin{equation}
\nabla \cdot\sigma=0.
\end{equation}
$$

## Hyperelastic material
There exists a strain-energy density function $\Psi:\text{Lin}^+\to \mathbb{R}^+$ and the first Piola-Kirchoff stress tensor is 
$$
\begin{equation}
\mathbf{P}=\frac{ \partial \Psi(\mathbf{F}) }{ \partial \mathbf{F} },
\end{equation}
$$


The strain-energy density function relates the deformation $\mathbf{F}$ to the stored energy in the material. An important distinction for hyperelastic materials is that the stored energy is only related to the deformation and not the path of deformation.

We impose the following conditions for $\Psi$:
* The energy stored in the reference configuration must be zero: $\Psi(\mathbf{I})=0$
* The material cannot store negative energy: $\Psi(\mathbf{F})\geq0$.
* Compression the material to zero volume, or expansion to infinite volume demands infinite energy: $\Psi(\mathbf{F})\to \infty$ as $\det \mathbf{F}\to0$ or $\det \mathbf{F}\to \infty$.

One wishes to express the strain-energy function in terms of *principle invariants*, meaning that they do not depend on the choice of coordinate system. For example, an isotropic hyperelastic material can be expressed in terms of the principle invariants $I_{1},I_{2},I_{3}$ of $\mathbf{C}$ such that
$$
\begin{equation}
\Psi(\mathbf{C})=\Psi(I_{1},I_{2},I_{3}).
\end{equation}
$$

### Extensive property 
(Rossi $p$.13)
For an extensive property $B$ in a domain $\omega$, the conservation law reads
$$
\begin{equation}
\frac{\text{d}}{\text{d}t} \int_{\omega}B(\mathbf{x},t)\,\text{d} v=\int_{\omega}S(\mathbf{x},t)\,\text{d} v+\int_{\partial\omega}\mathbf{q}\cdot \mathbf{n} \,\text{d} s,
\end{equation}
$$
where $S(\mathbf{x},t)$ is the source term, $\mathbf{q}$ is the flux density, and $\mathbf{n}$ is the outward surface normal of $\omega$.
$\vdots$
*Balance equation*
$$
\begin{equation}
\int_{\Omega}J\left[ \frac{\text{d}B}{\text{d}t} +B\nabla \cdot \mathbf{v} \right]\,\text{d} V=\int_{\omega}\left[ \frac{\text{d}B}{\text{d}t} +B\nabla \cdot \mathbf{v} \right]\,\text{d} v,
\end{equation}
$$
where $\mathbf{v}$ is the spatial velocity vector

Applying the *balance equation* to the mass density $\rho$ gives

### Dissipation inequality
(Rossi p.19)
Denoting $\eta$ as the entropy per mass, the entropy $\mathcal{S}$ is an extensive property:
$$
\begin{equation}
\mathcal{S}=\int_{\Omega}\rho\eta \,\text{d} v.
\end{equation}
$$
Conservation of entropy states that 
$$
\begin{equation}
\frac{\text{d}\mathcal{S}}{\text{d}t} =\mathcal{H}+\mathcal{J},
\end{equation}
$$
where $\mathcal{H}$ is the entropy production in $\Omega$ and $\mathcal{J}$ is the entropy flux. The second law of thermodynamics states that the entropy production $\mathcal{H}$ must be nonnegative. This gives us the *dissipation inequality*
$$
\begin{equation}
\mathcal{H}=\frac{\text{d}\mathcal{S}}{\text{d}t} -\mathcal{J}\geq0
\end{equation}
$$
