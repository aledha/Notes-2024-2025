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
\mathbf{H} & =\mathbf{F}-\mathbf{I} 
\end{align}
$$
![[Pasted image 20241204115811.png]]

![[Pasted image 20241204115819.png]]

![[Pasted image 20241204115827.png]]

![[Pasted image 20241204115834.png]]

## Fluid mechanics
![[Pasted image 20241204115911.png]]

![[Pasted image 20241204115919.png]]

![[Pasted image 20241204115928.png]]

![[Pasted image 20241204115937.png]]

![[Pasted image 20241204115951.png]]

![[Pasted image 20241204120002.png]]

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