* **Contraction mechanism:** Calcium ions are released into cells as a result from the triggering of the action potential. This allows the thin filament, actin, and the thick filament, myosin, to bind, which forms what is called a *cross-bridge*. 
* **PV-Loop**: During one cardiac cycle, one can measure the volume of the left ventricle on one axis, and the pressure on the other to illustrate the pressure-volume relationship during a cycle.

 
* **Isovolumoic contraction**: During end-diastole (ED), the mitral valve closes such that the ventricle is fully closed. Then, the ventricle contracts, which increases the pressure. When the pressure exceeds the *aortic pressure*, the aortic valve opens, allowing the high-pressurized blood to flow to the rest of the body.
* **Isovolumic relaxation**: When the pressure drops below the *aortic pressure* after the sufficient blood has flowed out of the ventricle, the aortic valve closes again. The ventricle is fully closed and relaxes, decreasing the pressure. When the pressure drops below the *atrial pressure*, the mitral valve opens and allows oxygenated blood to flow into the ventricle.

The process from the start of the isovolumic contraction until the closing of the aortic valve is called *systole*.
The process from the start of isovolumic relaxation until the closing of the mitral valve is called *diastole*.

![[Pasted image 20250108140802.png|800]]
* **End-diastolic pressure volume relationship (EDPVR)** is the relationship between the pressure and volume during the inactive state (no contraction in the myocardium)
*  **End-systolic pressure volume relationship (ESPVR)** is the relationship between the pressure and volume during the active state (full contraction in the myocardium)

![[Pasted image 20250108141045.png|600]]

If the blood coming into the heart (i.e., preload) increases, then the end-diastolic (after refilling) volume increases, and the ventricle contracts more. This is called the *Frank-Sterling law*.
* **Frank-Sterling law**: the difference in EDPVR and ESPVR increases for increased preload.
* **Elastance**: the slope of the pressure-volume relationship.
* *Time varying elastance model*:
$$
\begin{equation}
P(t)=E(t)(V(t)-V_{0}),
\end{equation}
$$
where $P$ is the endocardial pressure, $V$ is the cavity volume, $E$ is the time-varying elastance, and $V_{0}$ is the volume axis intercept (?).

## Kinematics
* *Reference configuration*: 
	* $\Omega\equiv\chi_{0}(\mathcal{B})$
	* Coordinate $\mathbf{X}\in\Omega$
* *Current configuration*: 
	* $\omega\equiv\chi(\mathcal{B})$
	* Coordinate $\mathbf{x}\in\omega$
* Mapping from reference to current:
	* $\mathbf{x}=\phi(\mathbf{X})$
* Deformation gradient $\mathbf{F}=\nabla_{\mathbf{X}}\phi=\text{Grad}\mathbf{x}$
	* Grad: derivative with respect to reference coordinates $\mathbf{X}$.
	* $\mathbf{F}\in \text{Lin}^+$, 
		* where $\text{Lin}^+$ is the space of linear transformations with strictly positive determinant.
* Displacement field
	* $\mathbf{u}=\mathbf{x}-\mathbf{X}$
	* $\mathbf{F}=\text{Grad}\mathbf{x}=\text{Grad}\mathbf{u}+\text{Grad}\mathbf{X}=\text{Grad}\mathbf{u}+\mathbf{I}$
* Right Cauchy-Green deformation tensor $\mathbf{C}=\mathbf{F}^T\mathbf{F}$
* Left Cauchy-Green deformation tensor $\mathbf{B}=\mathbf{F}\mathbf{F}^T$
* Green-Lagrange strain tensor $\mathbf{E}=\frac{1}{2}(\mathbf{C}-\mathbf{I})$
* Determinant of deformation gradient $J=\det \mathbf{F}$.
![[Pasted image 20250109130411.png]]

A vector $d\mathbf{X}$ in the reference configuration will be deformed to the vector $d\mathbf{x}$ in the current configuration such that $\text{ d}\mathbf{x}=\mathbf{F}\text{ d}\mathbf{X}$. Thus, an infinitesimal volume $v$ in the current configuration deformed from the reference volume $V$ has the relation 
$$
\begin{equation}
\text{ d} v=\det (\mathbf{F})\text{ d} V.
\end{equation}
$$
This can be rewritten using surface elements
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
\mathbf{P}=\frac{ \partial \Psi(\mathbf{F}) }{ \partial \mathbf{F} } .
\end{equation}
$$
The strain-energy density function relates the deformation $\mathbf{F}$ to the stored energy in the material. An important distinction for hyperelastic materials is that the stored energy is only related to the deformation and not the path of deformation.

Some conditions for $\Psi$ are
* The energy stored in the reference configuration must be zero: $\Psi(\mathbf{I})=0$
* The material cannot store negative energy: $\Psi(\mathbf{F})\geq0$.
* Compression the material to zero volume, or expansion to infinite volume demands infinite energy: $\Psi(\mathbf{F})\to \infty$ as $\det \mathbf{F}\to0$ or $\det \mathbf{F}\to \infty$.

One wishes to express the strain-energy function in terms of *principle invariants*, meaning that they do not depend on the choice of coordinate system. For example, an isotropic hyperelastic material can be expressed in terms of the principle invariants $I_{1},I_{2},I_{3}$ of $\mathbf{C}$ such that
$$
\begin{equation}
\Psi(\mathbf{C})=\Psi(I_{1},I_{2},I_{3}).
\end{equation}
$$
### Incompressibility
During the contraction of the myocardium, blood is squeezed out, resulting in a volume loss of 2-4%. Hence, the myocardium is a compressible material. 
A common simplification for numerical ease is to assume that the myocardium is incompressible, such that
$$
\begin{equation}
J=\det \mathbf{F}=1.
\end{equation}
$$

## Constitutive equations for living tissue

### Passive myocardium
With a local orthonormal coordinate system with fiber axis $\mathbf{f}_{0}$, sheet axis $\mathbf{s}_{0}$, and sheet-normal axis $\mathbf{n}_{0}$. The invariants are defined as
$$
\begin{align}
I_{1} & =  \mathrm{Tr}\mathbf{C} \\
I_{4\mathbf{f}_{0}} & =\mathbf{f}_{0}\cdot(\mathbf{C}\mathbf{f}_{0}), \\
I_{4\mathbf{s}_{0}} & =\mathbf{s}_{0}\cdot(\mathbf{C}s_{0}), \\
I_{8\mathbf{f}_{0}\mathbf{s}_{0}} & =\mathbf{s}_{0}\cdot(\mathbf{C}\mathbf{f}_{0}).
\end{align}
$$
$I_{4\mathbf{f}_{0}}$ can be interpreted as the stretch along the fibers, $I_{4\mathbf{s}_{0}}$ can be interpreted as the stretch along the sheet. \eqref{} can be rewritten as
$$
\begin{equation}
I_{8\mathbf{f}_{0}\mathbf{s}_{0}}=\mathbf{s}_{0}\cdot(\mathbf{C}\mathbf{f}_{0})=\mathbf{s}_{0}\cdot(\mathbf{F}^T\mathbf{F}\mathbf{f}_{0})=(\mathbf{F}\mathbf{s}_{0})\cdot(\mathbf{F}\mathbf{f}_{0}),
\end{equation}
$$
which indicates that $I_{8\mathbf{f}_{0}\mathbf{s}_{0}}$ can be interpreted as a measure on the angle between the deformed sheet axis and the deformed fiber axis. The sheet axis and the fiber axis were orthonormal in the reference configuration.

![[Pasted image 20250109153550.png]]
#ask why $(x)_{+}$?