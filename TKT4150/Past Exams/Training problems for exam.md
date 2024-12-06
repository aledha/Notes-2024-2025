## Solid mechanics
```ad-question
title: Question 1
Briefly explain the continuum hypothesis on which continuum mechanics is based on

```
A material can be described by a continuum. Mechanical properties such as density, force, etc. can be evaluated at any point in the continuum. All material properties are perceived as an average over a small volume.

```ad-question
title: Q2
Define 
a) Particle
b) Position
c) Lagrangian coordinates
d) Eulerian coordinates
e) Material derivative of an intensive field function

```
a) A particular position in the reference system.
b) $\mathbf{r}_{0}=(X_{1},\dots,X_{n})$  , $\mathbf{r}=(x_{1},\dots,x_{n})$.
c) Lagrange: particle coordinates. Used to label material points, which are followed on their journey.
d) Euler: Space coordinates. Fixed point
![[Pasted image 20241204102406.png|500]]
e) 
* **Extensive property**: A property that is proportional to the amount of material that is in the system, i.e. it is a function of the volume or mass of the body. Example: **mass**
* **Intensive property**: A property that is independent of the amount of material that is in the system, i.e. it is independent of body volume or mass. Example: **Density** 
A material derivatives is the derivative of an intensive field function $f(x(X,t),t)$:
$$
\begin{align}
\dot{f} & = \frac{\text{d}f}{\text{d}t}  \\
 & =\frac{ \partial f }{ \partial t } +\frac{ \partial f }{ \partial x_{1} }\frac{ \partial x_{1} }{ \partial t }  +\frac{ \partial f }{ \partial x_{2} }\frac{ \partial x_{2} }{ \partial t }  +\frac{ \partial f }{ \partial x_{3} }\frac{ \partial x_{3} }{ \partial t }   \\
 & =\frac{ \partial f }{ \partial t } +\left( v_{i} \frac{ \partial  }{ \partial x_{i} } \right)f \\
 & =\frac{ \partial f }{ \partial t }+ (\mathbf{v}\cdot \nabla)f
\end{align}
$$
An extensive property would be $F(t)=\int_{V}f \rho\text{ d}V$.

![[Pasted image 20241204103629.png]]
$$
\mathbf{v}(\mathbf{x},t)=\frac{ \partial \mathbf{r}(\mathbf{r}_{0},t) }{ \partial t } 
$$
$$
\mathbf{a}(\mathbf{X},t)=\frac{ \partial \mathbf{v}(\mathbf{X},t) }{ \partial t } =\frac{ \partial ^2\mathbf{r}(\mathbf{X},t) }{ \partial t^{2} } 
$$
As acceleration and velocity is an intensive property, we may use the previous question with $\mathbf{f}=\mathbf{v}$:
$$
\begin{align}
\dot{\mathbf{v}} & =\frac{ \partial \mathbf{v} }{ \partial t }+ (\mathbf{v}\cdot \nabla)\mathbf{v} \\
\dot{\mathbf{a}} & =\frac{ \partial \mathbf{v} }{ \partial t } +(\mathbf{v}\cdot \nabla)\mathbf{v}
\end{align}
$$


![[Pasted image 20241204104200.png]]
$$
\mathbf{t}_{k}=T_{ik}\mathbf{e}_{i}
$$

![[Pasted image 20241204113255.png]]

First: **The rate of change of the linear momentum for a continuum volume equals the resultant force.** 
The linear momentum $\mathbf{P}$ (normally $mv$) is an **extensive** property, meaning that
$$
\mathbf{P}=\int_{V}\mathbf{v}\rho \text{ d} V,
$$
so
$$
\begin{align}
\dot{\mathbf{P}}=\frac{\text{d}}{\text{d}t} \int_{V}\mathbf{v}\rho \text{ d} V & =  \mathbf{f} \\
\int_{V}\dot{\mathbf{v}}\rho \text{ d} V & =\mathbf{f}\tag{Eulers 1st}
\end{align}
$$

Second: **The rate of change of the angular momentum for a continuum volume equals the resultant moment.**
$$
\dot{\mathbf{I}}=\mathbf{m}_{0} 
$$
Moment:
$$
\mathbf{m}_{0}=\int_{A}\mathbf{r}\times \mathbf{t}\text{ d} A+\int_{V}\mathbf{r}\times \mathbf{b}\text{ d} V
$$
Angular momentum:
$$
\dot{\mathbf{I}}_{0}=\int_{V}\mathbf{r}\times \mathbf{v}\rho \text{ d} V.
$$
![[Pasted image 20241204114611.png]]
The coordinate stresses are defined in the stress matrix
$$
\mathbf{T}=\begin{bmatrix}
T_{11} & T_{12} & T_{13} \\
T_{21} & T_{22} & T_{23} \\
T_{31} & T_{32} & T_{33}
\end{bmatrix}
$$
Where the first index is which surface the stress is being applied and the second index is the direction of the force

![[Pasted image 20241204115213.png]]
For a plane with normal vector $\mathbf{n}$, the stress vector is given by
$$
\mathbf{t}=\mathbf{T}\cdot \mathbf{n}
$$

![[Pasted image 20241204115603.png]]
The normal stress can be obtained by dot multiplying the stress vector with the normal vector:
$$
\sigma=\mathbf{n}\cdot \mathbf{t}=\mathbf{n}\cdot \mathbf{T}\cdot \mathbf{n}
$$
And such the shear vector $\tau$ must be the resulting
$$
\boldsymbol{\tau}=\mathbf{t}-\sigma \mathbf{n}
$$
and magnitude is
$$
\tau=\sqrt{ \boldsymbol{\tau}\cdot\boldsymbol{\tau} } 
$$

![[Pasted image 20241204115611.png]]
$$
\begin{align}
\int_{V}\dot{\mathbf{v}}\rho \text{ d} V & =\mathbf{f}\tag{Eulers 1st} \\
\int_{V}\dot{\mathbf{v}}\rho \text{ d} V & =\int_{A}\mathbf{t}_{i}\text{ d} A+\int_{V}\rho \mathbf{g}\text{ d} V \\
\int_{V}\dot{\mathbf{v}}\rho \text{ d} V & =\int_{A}\mathbf{T_{ik}}\mathbf{n}_{k}\text{ d} A+\int_{V}\rho \mathbf{g}\text{ d} V \\
\int_{V}\dot{\mathbf{v}}\rho \text{ d} V & =\int_{V}T_{ik,k}\text{ d} V+\int_{V}\rho \mathbf{g}\text{ d} V \\
\dot{v}_{i}\rho & =T_{ik,k}+\rho g_{i} \\
a_{i}\rho & =T_{ik,k}+\rho g_{i} \\
\mathbf{a}\rho & =\nabla \cdot \mathbf{T}+\rho \mathbf{g}
\end{align}
$$
![[Pasted image 20241204115619.png]]
For any state of stress in a particle there are three orthogonal planes free of shear stress, known as **principle planes**.

![[Pasted image 20241204115626.png]]
**Normal stress** is the stress acting in the normal direction of a surface. 
**Principle stress** is the stress acting in the normal direction of a plane free of shear stress.

![[Pasted image 20241204115642.png]]
By computing the eigenvalue problem
$$
\mathbf{T}\cdot \mathbf{n}=\sigma \mathbf{n}
$$
where $\sigma$ is the principal stress and $\mathbf{n}$ is the principle plane.

![[Pasted image 20241204115648.png]]
The **maximal and minimal normal stress** are intuitively the maximal and minimal principle stress. Therefore, the max normal is $40\,\mathrm{MPa}$
The **maximal shear stress** is given by
$$
\begin{align}
\tau _\text{max} & =\frac{1}{2}(\sigma _\text{max}-\sigma _\text{min}) \\
 & =\frac{1}{2}20=10
\end{align}
$$
The maximum shear stress acts on planes that are inclined 45∘ with respect to the principal directions of the maximum and minimum principal stresses.

![[Pasted image 20241204115655.png]]
**Longitudinal strain**
Given a particle and direction. How much a direction has stretched compared to the reference configuration
$$
\epsilon=\lim_{ s_{0} \to 0 } \frac{s-s_{0}}{s_{0}}= \frac{\text{d}s}{\text{d}s_{0}}-1 
$$
**Shear strain**
The angular deviation between vectors(given) that were orthogonal in reference configuration

**Volumetric strain**
$$
\epsilon_{V}=\lim_{ \Delta V_{0} \to 0 } \frac{\Delta V-\Delta V_{0}}{\Delta V_{0}}
$$
given particle

![[Pasted image 20241204115705.png]]
$x_{i}(X,t)=X_{i}+u_{i}(X,t)$.
$$
\begin{align}
F_{ij} & =\frac{ \partial x_{i} }{ \partial X_{j} }  \\
H_{ij} & =\frac{ \partial u_{i} }{ \partial X_{j} } \\
\mathbf{H} & =\mathbf{F}-\mathbf{I}  \\
\mathbf{C} & =\mathbf{F}^T\mathbf{F} \\
\mathbf{E} & =\frac{1}{2}(\mathbf{C}-\mathbf{I}) \\
\mathbf{L} & =\dot{\mathbf{H}} \\
L_{ij}  & =\frac{ \partial v_{i} }{ \partial x_{j} } =v_{i,j} \\
\mathbf{D} & =\frac{1}{2}(\mathbf{L}+\mathbf{L}^T)=\dot{\mathbf{E}} \\
D_{ij} & =\frac{1}{2}(v_{i,j}+v_{j,i})
\end{align}
$$
![[Pasted image 20241204115811.png]]
a)
$$
\lambda= \frac{ds}{ds_{0}}
$$
Let's say $e$ is in direction 1.
$F_{11}=\lambda\implies C_{11}=\lambda^2$. So $\lambda=\sqrt{ \mathbf{e}\cdot\lambda^2\cdot \mathbf{e} }=\lambda$.

b)
We have that $E_{11}=\frac{1}{2}(C_{11}-1)=\frac{1}{2}(\lambda^2-1)$, so
$$
\begin{align}
\mathbf{e}\cdot \mathbf{C}\cdot \mathbf{e} & =\frac{1}{2}(\lambda^2-1) \\
 & =\frac{1}{2}\left( \frac{ds^2}{ds_{0}^2}-1 \right) \\
 & =\frac{1}{2} \frac{ds^2-ds^{2}_{0}}{ds^{2}_{0}}
\end{align}
$$


![[Pasted image 20241204115819.png]]
**Small strains:** when longitudinal strain $\epsilon<1\%$. 
**Small deformations**: when all entries in $\mathbf{H}$ are << 1.

![[Pasted image 20241204115827.png]]
**Linear elastic material**: When the stresses are functions solely of the deformations: $\mathbf{T}=\mathbf{T}(\mathbf{E})$, where $\mathbf{T}(\mathbf{E})$ is a linear relation. Or $\epsilon_{i}=\frac{\sigma_{1}}{\eta}$.
**Hyperelastic material**: If the strain power per unit volume $\omega$ may be derived from a scalar valued potential $\phi(\mathbf{E})$ such that
$$
\omega=\dot{\phi}=\frac{ \partial \phi }{ \partial E_{ij} } \dot{E_{ij}}
$$
**Isotropic material**: when all directions in the material have the same material properties
**Elasticity modulus**: For a Hookean solid, the elasticity (Youngs) modulus $\eta$ is the relation between the stress and strains: $$\epsilon_{i}=\frac{\sigma_{i}}{\eta}$$
**Poisson ratio**: For a Hookean solid undergoing uniaxial stress in one direction, there are negative strains in the other direction with ratio $\nu$:
$$
\epsilon_{2}=-\nu \epsilon_{1}=-\nu\frac{ (\sigma_{1})}{\eta}
$$
**Shear modulus**: 
$$
\mu=\frac{\eta}{2(1+\nu)}
$$

![[Pasted image 20241204115834.png]]
First:
$$
\mathbf{T}_{0}=J\mathbf{T}\mathbf{F}^{-T} 
$$
Second:
$$
\mathbf{S}=J\mathbf{F}^{-1}\mathbf{T}\mathbf{F}^{-T}
$$
and for hyperelastic material,
$$
\mathbf{S}=2\frac{ \partial \phi }{ \partial \mathbf{C} } 
$$

## Fluid mechanics
![[Pasted image 20241204115911.png]]
**Fluid.** A fluid is a material that deforms continuously when subjected to anisotropic stress.

![[Pasted image 20241204115919.png]]
a)
$B$ is an extensive property, $b$ is the density of the extensive property, $V(t)$ is the control volume at time $t$, $A$ is the area of the control volume, $\mathbf{v}$ is the speed at a given point, $\mathbf{n}$ is the unit normal vector. So
$$
\int_{V(t)}\frac{ \partial b }{ \partial t } \text{ d} V
$$
is the change of the density of $B$ in a volume $V$, and
$$
\int_{A(t)}b(\mathbf{v}\cdot \mathbf{n})\text{ d}  A
$$
is the speed of the moving body relative to the normal vector multiplied by the density of $B$. This term is how much the material moves out of the control volume.

b) 
For a volume with mass $m$, we can set up Reynolds transport theorem as
$$
\dot{m}=\int_{V(t)}\frac{ \partial \rho }{ \partial t } \text{ d} V+\int_{A(t)}\rho(\mathbf{v}\cdot \mathbf{n})\text{ d} A
$$
here we assume conservation of mass, $i$.$e$. that $\dot{m}=0$ and use the divergence theorem on the last term:
$$
\begin{align}
0 & =\int_{V(t)}\frac{ \partial \rho }{ \partial t } \text{ d} V+\int_{V(t)}\rho \nabla \mathbf{v} \text{ d} V+\int_{V(t)}\rho \mathbf{v}\cdot(\nabla 1)\text{ d}  V \\
0 & =\frac{ \partial \rho }{ \partial t } +\rho \nabla \mathbf{v} \\
0 & =\frac{ \partial \rho }{ \partial t } +\rho(v_{i})_{,i}
\end{align}
$$

![[Pasted image 20241204115928.png]]
For incompressible flow, we have $\frac{ \partial \rho }{ \partial t }=0$ so the equation above:
$$
0=\rho \nabla \mathbf{v}
$$


![[Pasted image 20241204115937.png]]
Inner wall is stationary, while outer wall is moving. Torque on the inner wall is measured
![[IMG_0265.jpg|600]]

Relation between shear stress $\tau$ and shear strain rate $\dot{\gamma}$. Newtonian have a linear relation:
$$
\tau=\mu \dot{\gamma}
$$
Shear thinning: weaker relation
Shear thickening: Stronger relation
Viscoplastic: Undergoes plastic deformations, unrecoverable when a load is reached.

![[Pasted image 20241204115951.png]]
$\dot{\gamma}=\frac{\text{d}v}{\text{d}y}$
a) Newtonian, $\tau=\mu \dot{\gamma}$.

b) viscosity: $[\tau]=\mathrm{Pa}$, $[v]=\mathrm{ms^{-1}}$, $\left[ \frac{\text{d}v}{\text{d}y} \right]=s^{-1}$ so
$$
[\mu]=\mathrm{Pa\cdot s}
$$


![[Pasted image 20241204120002.png]]
$c=-\frac{\text{d}p}{\text{d}z}$

$$\begin{aligned}
\tau 2\pi R \cdot \text{ d}z-\frac{\partial p}{\partial z}\text{ d}z \cdot \pi R^{2}&= 0\\
\left(c=\frac{\partial p}{\partial z} \right)\qquad \implies\qquad  \tau &= -\frac{cR}{2}
\end{aligned}\tag{*}$$
$\tau =\tau _{y}\quad\implies\quad r_{P}=2\frac{\tau _{y}}{c}$.

![[Pasted image 20241204120009.png]]



![[Pasted image 20241204120015.png]]

![[Pasted image 20241204120021.png]]

![[Pasted image 20241204120026.png]]

## Muscles

![[Pasted image 20241204120038.png]]
![[Pasted image 20241204120044.png]]

![[Pasted image 20241204120051.png]]

![[Pasted image 20241204120057.png]]

## Vessel wall mechanics
![[Pasted image 20241204120111.png]]

![[Pasted image 20241204120122.png]]

![[Pasted image 20241204120132.png]]