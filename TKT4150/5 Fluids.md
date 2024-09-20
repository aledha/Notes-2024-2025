Ref. Viscometer experiments give material response. 
![[IMG_0265.jpg|600]]

For a fluid at rest, the stress state is isotropic:
$$T_{ij}=-p \delta _{ij}=-p(\theta , \rho )$$
where $\theta$ is temperature.

Cauchy's equations of motion
$$\begin{aligned}
\text{div}\mathbf T+\rho \mathbf b&= \rho \mathbf a\\
\frac{\partial v_{i}}{\partial t}+v_{k}v_{i,k}&= \frac{1}{\rho } T_{ik,k}+b_{i}\\
a&= \partial _{t}v_{i}+v_{k}v_{i,k}
\end{aligned}$$

*Stream lines*: vector fields for velocity, they change with time for nonsteady flow, 
$$\mathbf v=\mathbf v(\mathbf r,t)$$
Stream lines coincide with particle trajectories (path lines) for steady flow $\implies\quad \mathbf v=\mathbf v(\mathbf r)$.
![[IMG_0266.jpg|600]]
$\text{ d}\mathbf r$ and $\mathbf v$ are parallel
$$\implies\quad \text{ d}\mathbf r \times \mathbf v=0=\det\begin{bmatrix}\text{ d}x_{1} & \text{ d}x_2 \\ v_{1} & v_2\end{bmatrix}$$
$$\text{ d}x_{1}v_{2}-v_{1}\text{ d}x_{2}=0 \quad\implies\quad \frac{\text{ d}x_{1}}{v_{1}}=\frac{\text{ d}x_{2}}{v_{2}}$$
We define the following:
- *Vorticity field*: $\mathbf c=\nabla \times \mathbf  v$
- *Potential flow -> irrotational flow*:
  $$\mathbf v=\nabla \phi ,\qquad \phi =\phi (\mathbf r,t), \qquad \mathbf c=\nabla \times \mathbf v=0.$$
![[IMG_0267.jpg|400]]
$Q$: volumetric flow rate, $V_{m}:$ mean velocity, $d:$ diameter of tube
$$Q=v_{m}\pi \frac{d^{2}}{4},$$
Reynolds number is
$$R_{e}=\frac{\rho v_{m}d}{\mu }$$
We have laminar flow for $R_{e}<1000$, turbulent flow for $R_{e}>2000$.

## Strain rates
In fluids, the velocity $\mathbf v(\mathbf x,t)$ is the primary kinematic quantity.
During a short time interval, a fluid "particle" is displaced $\text{ d}\mathbf u=\mathbf v \text{ d}t$.
We find a strain from $\text{ d}\mathbf u$
$$\begin{aligned}
E_{ik}&= \frac{1}{2}(v_{i,k}+v_{k,i})\text{ d}t\\
&= D_{ik}\text{ d}t
\end{aligned}$$
Longitudinal strain rate $\epsilon$ in a direction $\mathbf e$,
$$\dot \epsilon =\mathbf e \cdot \mathbf D \cdot \mathbf e$$
Shear strain rate (change of a 90 degree angle) with respect to $\mathbf e$ and $\overline{\mathbf e}$, $\mathbf e \cdot \overline{\mathbf  e}=0$
$$\dot \gamma =2 \overline{\mathbf e}\cdot \mathbf D \cdot \mathbf e$$
Volumetric strain rate $\dot \epsilon _{V}=D_{kk}=V_{k,k}$.

From conservation of mass, we get the **continuity equation**
$$\dot m=0=\int_{V}\frac{\partial \rho }{\partial t}\text{ d}V+\int_{A}\rho (\mathbf v \cdot \mathbf n)\text{ d}A$$
By divergence theorem:
$$\begin{aligned}
0&= \int_{V}\left(\frac{\partial \rho }{\partial t}+\nabla \left(\rho \mathbf v \right) \right)\text{ d}V
\end{aligned}$$
$$\boxed{\frac{\partial \rho }{\partial t}+\nabla \left(\rho \mathbf v \right)=0}$$

For an incompressible fluid, we get
$$\boxed{v_{k,k}=0}$$

### Perfect fluids
If we neglect viscosity ($\mu \approx0$), we have a **perfect fluid** (Euler fluid). 
**Euler equations**
$$\mathbf T=-\rho \mathbf I, \quad T_{ij}=-p \delta _{ij}$$
$$\implies\quad \partial _{t}v_{i}+v_{k}v_{i,k}=-\frac{1}{\rho }p_{,i}+b_{i}$$
Here 
$$T_{ik,k}=(-p \delta _{ik})_{k}=-p_{,k}\delta _{ik}=-p_{,i}$$
$$\implies\quad \text{div}\mathbf T=-\nabla p$$

**Bernoulli equations** = Euler equations + stationary flow ($\partial _{t}\mathbf v=0$)
$$\rho (\mathbf v \cdot \nabla )\mathbf v=-\nabla p+\rho \mathbf g,\qquad \mathbf g=-g \mathbf e_{3}$$

It is possible to rewrite 
$$(\mathbf v \cdot \nabla )\mathbf v=\frac{1}{2}\nabla (\mathbf v \cdot \mathbf v)-\mathbf v \times(\nabla  \times \mathbf v)$$
Substituting:
$$-\nabla p-\frac{1}{2}\nabla (\mathbf v \cdot \mathbf v)-\rho g \mathbf e_{3}=\rho \mathbf v \times(\nabla \times \mathbf v)$$
![[IMG_0268.jpg|600]]
Take dot product of this with $\text{d}\mathbf s$:
$$\begin{aligned}
-\nabla p \cdot  \text{ d}\mathbf s-\frac{1}{2}\rho \nabla (\mathbf v \cdot \mathbf v)\cdot \text{ d}\mathbf s-\rho g \mathbf e_{3}\cdot \text{ d}\mathbf s&= -\rho \mathbf v \times(\nabla \times \mathbf v)\cdot \text{ d}\mathbf s
\end{aligned}$$
note that 
- $\nabla p \cdot \text{ d}\mathbf s=\frac{\partial p}{\partial x_{1}}\text{ d}x_{1}+\frac{\partial p}{\partial x_{2}}\text{ d}x_{2}+\frac{\partial p}{\partial x_{3}}\text{ d}x_{3}=\text{ d}p$.
- $(\mathbf v \cdot \mathbf v)\cdot \text{ d}\mathbf s=(v^{2})\cdot \text{ d}\mathbf s=\frac{\partial (v^{2})}{\partial x_{i}}\text{ d}x_{i}=\text{ d}v^{2}$.
- $-\rho \mathbf v \times(\nabla \times \mathbf v)\cdot \text{ d}\mathbf s=0$ since these are orthogonal.
- $\mathbf e_{3}\cdot \text{ d}s=\text{ d}x_{3}$
The equation simplifies to
$$\begin{aligned}
-\text{ d}p-\frac{1}{2}\rho \text{ d}(v^{2})-\rho g \text{ d}x_{3}&= 0\\
\frac{\text{ d}p}{\rho }+\frac{1}{2}\text{ d}v^{2}+g \text{ d}x_{3}&= 0
\end{aligned}\tag{*}$$

We have that
$$\int_\text{stream line} (*)=\text{constant}$$
this means that at points (1) and (2) the same value results
$$\frac{p_{1}}{\rho g}+\frac{v_{1}^{2}}{2g}+x_{3}|_{1}= \frac{p_{2}}{\rho g}+\frac{v_{2}}{2g}+x_{3}|_{2}$$

### Linearly viscous fluids
Relation between shear stress and shear strain rate
$$\tau =\mu \dot \gamma, $$
where $\mu$ is constant.
Constitute equations (material models)
Look at Hooke's law in elasticity. It can be written
$$T_{ij}=2 \mu E_{ij}'+\varkappa E_{kk}\delta _{ij},$$
where
- $E'_{ij}=E_{ij}-\frac{1}{3}E_{kk}\delta _{ij}$ are deviatoric strains
- $\varkappa$ is the bulk modulus, relates to the resistance of volume change

$$\begin{aligned}
\implies\quad T_{ij}&= 2\mu \left(E_{ij}-\frac{1}{3}E_{kk}\delta _{ij}\right)+\varkappa E_{kk}\delta _{ij}\\
&= 2\mu E_{ij}+ \left(\varkappa -\frac{2}{3} \right)E_{kk}\delta _{ij}
\end{aligned}$$
For a linearly viscous fluid we have a similar expression (use strain rate instead of strains):
$$T_{ij}=2\mu D_{ij}+\left(\varkappa-\frac{2}{3}\mu \right)D_{kk}\delta _{ij}$$
where $D$ is rate of deformation.

Usually, we also have an initial pressure. Then we get the **Constitute equation**
$$\begin{aligned}
\implies\quad T_{ij}&= -p \delta _{ij}+2\mu D_{ij}+\left(\varkappa -\frac{2}{3}\mu \right) D_{kk}\delta _{ij}\\
\mathbf T&= -\rho \mathbf I+2\mu \mathbf D+\left(\varkappa -\frac{2}{3}\mu \right)\text{trace}(\mathbf D)\mathbf I.
\end{aligned}\tag{CE}$$

- Pure shear $T_{12}=\tau =\mu (v_{1,2}+v_{2,1})=\mu \dot \gamma$
- Isotropic stress state $T_{ij}=-\tilde p \delta _{ij}$
  $D_{ij}= \frac{1}{3}D_{kk}\delta _{ij}= \frac{1}{3}\dot \epsilon _{V}\delta _{ij}$
Then we get
$$\begin{aligned}
-\tilde p&= -p\frac{2}{3}\mu \dot \epsilon _{V}+ \left(\varkappa -\frac{2}{3}\mu \right)\dot \epsilon _{V}\\
&= -p +\varkappa \dot \epsilon _{V}\\
\implies\quad \varkappa &= \frac{p-\tilde p}{\dot \epsilon _{V}}, \qquad \text{bulk viscosity}
\end{aligned}$$
- Incompressible fluid $\quad\implies\quad \text{trace}(\mathbf D)=0$ 
$$T_{ij}=-p \delta _{ij}+2\mu D_{ij}$$
Next: plug (CE) into cauchys eq of motion, we get Navier-Stokes.