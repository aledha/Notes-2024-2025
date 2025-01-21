### Passive myocardium
With a local orthonormal coordinate system with fiber axis $\mathbf{f}_{0}$, sheet axis $\mathbf{s}_{0}$, and sheet-normal axis $\mathbf{n}_{0}$. The invariants are defined as
$$
\begin{align}
I_{1} & =  \mathrm{Tr}\mathbf{C} \\
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
where $T_{a}$ represent the total active stress and $\eta$ represents the active stress in the transverse direction. As will be discussed in section \ref{sec:}, $T_{a}$ and $\eta$ will be used as the coupling from the electrophysiology to the mechanics.

Using
$$
\begin{equation}
\frac{ \partial I_{4\mathbf{s}_{0}} }{ \partial \mathbf{F} } =\frac{ \partial (\mathbf{s}_{0}\cdot \mathbf{C}\mathbf{s}_{0}) }{ \partial \mathbf{F} } =2\mathbf{s}\otimes \mathbf{s}_{0}\implies \mathbf{s}\otimes \mathbf{s}=\frac{1}{2}\frac{ \partial I_{4\mathbf{s}_{0}} }{ \partial \mathbf{F} } \mathbf{F}^T,
\end{equation}
$$
and the analogous expressions for $\mathbf{f}\otimes \mathbf{f}$ and $\mathbf{n}\otimes \mathbf{n}$ on \eqref{} gives
$$
\begin{equation}
\boldsymbol{\sigma}_{a}=\frac{T_{a}}{2}\left(\frac{ \partial I_{4\mathbf{f}_{0}} }{ \partial \mathbf{F} }  + \eta \left(\frac{ \partial I_{4\mathbf{s}_{0}} }{ \partial \mathbf{F} }  +\frac{ \partial I_{4\mathbf{n}_{0}} }{ \partial \mathbf{F} } \right) \right)\mathbf{F}^T.
\end{equation}
$$
The relation $I_{1}=I_{4\mathbf{f}_{0}}+I_{4\mathbf{s}_{0}}+I_{4\mathbf{n}_{0}}$ allows \eqref{} to be rewritten to
$$
\begin{equation}
\boldsymbol{\sigma}_{a}=\frac{T_{a}}{2}\left( \frac{ \partial I_{4\mathbf{f}_{0}} }{ \partial \mathbf{F} }+\eta \left( \frac{ \partial I_{1} }{ \partial \mathbf{F} } -\frac{ \partial I_{4\mathbf{f}_{0}} }{ \partial \mathbf{F} } \right)  \right) \mathbf{F}^T.
\end{equation}
$$
To find a strain-energy function that satisfies $\boldsymbol{\sigma}_{a}=\frac{1}{J}\frac{ \partial \Psi(\mathbf{F}) }{ \partial \mathbf{F} }\mathbf{F}^T$, 
$$
\begin{equation}
\Psi_{a}(\mathbf{F})=\frac{JT_{a}}{2}[ (I_{4\mathbf{f}_{0}}-1)+\eta((I_{1}-3)-(I_{4\mathbf{f}_{0}}-1)) ],
\end{equation}
$$
where the invariants are subtracted to fulfill the requirement that $\Psi_{a}(\mathbf{I})=0$.
(The active stress formulation is not sufficient to describe tissue deformations (Rossi, p.5).)
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


## Force-balance equation




$$
\begin{align}
\nabla \cdot \mathbf{P} & =0 \\
J-1 & =0
\end{align}
$$

