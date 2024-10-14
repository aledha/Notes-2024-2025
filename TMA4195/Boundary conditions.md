$$u_{t}+(1-2u)u_{x}=0,\qquad x \ge0,\quad u(x,0)=\frac{1}{8}$$
$$F(u(0,t))=\frac{3}{16}$$

$$f(u)=1-2u$$
for characteristics starting from the x-axis: $x=\frac{3}{4}t+x_{0}$.
for characteristics starting from the t-axis: 
$$x=f(u(0,t_{0}))(t-t_{0})\quad\text{for }t \ge t_{0}$$
since $f(u)=1-2u$, then $F(u)=u-u^{2}$. We solve $F(u)=\frac{3}{16}$ to get
$$\begin{aligned}
u-u^{2}&= \frac{3}{16}\\
u^{2}-u+\frac{3}{16}&= 0\\
\left(u-\frac{1}{4}\right)\left(u-\frac{3}{4} \right)&= 0
\end{aligned}$$
so we have two possible values for $u$. 
If $u=\frac{3}{4}$, then 
$$\begin{aligned}
x&= \left(1-2 \cdot \frac{3}{4} \right)(t-t_{0})\\
&= -\frac{1}{2}(t-t_{0}).
\end{aligned}$$
This gives characteristics going out of the model (from right to left.)
If $u=\frac{1}{4}$, then
$$\begin{aligned}
x&= \left(1-2 \cdot \frac{1}{4} \right)(t-t_{0})\\
&= \frac{1}{2}(t-t_{0}),
\end{aligned}$$
which goes from left to right, into the domain.

To find the rarefaction wave,
$$\begin{aligned}
1-2u&= y\\
u&= \frac{1-y}{2}.
\end{aligned}$$

$$u(x,t)=\begin{cases}
\frac{1}{4} &  \quad\text{for } 0<x<\frac{1}{2}t \\
\frac{1-\frac{x}{t}}{2} & \quad\text{for }\frac{1}{2}t<x<\frac{3}{4}t \\
\frac{1}{8} & \quad\text{for }x>\frac{3}{4}t
\end{cases}$$

![[IMG_0346.jpg|600]]

## Modelling  flow in porous medium
$\phi$ is the fraction of medium available for fluids.
### Single-phased flow
We want to set up a conservation law, so we need the flux. 
Darcy's law: Volumetric flux densitity $\vec{q}$ is
$$\vec{q}=-\frac{k}{\mu }\nabla p,$$
where $k$ is absolute permeability, $\mu$ is the viscosity, and $p$ is the pressure. Dimensions:
* $[p]=\mathrm{kgm^{-1}s^{-2}}$.
* $[k]=\mathrm{m^{2}}$.
* $[\mu ]=\mathrm{kgm^{-1}s^{-1}}$.
* $[q]=\mathrm{\frac{m^{3}}{m^{2}s}}=\mathrm{ms^{-1}}$.

We can find the mass flux density as
$$\rho \vec{q},$$
where $\rho$ is the mass density.

Let $\Omega \subset \mathbb{R}^{3}$. The mass of fluids in $\Omega$ is
$$\iiint_{\Omega }\rho \phi \text{ d}V$$
Then the conservation (over mass) law is
$$\frac{\text{d}}{\text{d}t}\iiint_{\Omega }\phi \rho \text{ d}V+\iint_{\partial \Omega}\rho \vec{q}\cdot n \text{ d}S=0$$
If $\vec{q}$ is smooth, we can apply the divergence theorem to get
$$(\phi \rho )_{t}+\nabla \cdot (\rho \vec{q})=0$$
If we have incompressible flow, then $\phi$ and $\rho$ are constant, and
$$\nabla \cdot \vec{q}=0$$
### Two-phased flow
![[IMG_0347.jpg|700]]
We are pumping in CO2, which is lighter than brine. We want to figure out when CO2 begins going up the brine well.

$u(\vec{x},t):=$ fraction of pure space with CO2 = CO2 saturation.

Mass of CO2 in $\Omega$ is 
$$\iiint_{\Omega }\phi \rho _{g}u\text{ d}V$$
where $\rho _{g}$ is the density of CO2.

Brine saturation $=1-u$.
Need to find flux for both brine and CO2.
Volumetric flux densities:
$$\begin{aligned}
\vec{q}_{g}&= -k_{rg}(u)\frac{k}{\mu _{g}}\nabla p\\
\vec{q}_{w}&= -k_{rw}(u)\frac{k}{\mu _{w}}\nabla p
\end{aligned}$$
$k_{rg}$ and $k_{rw}$ are the relative permeabilities of CO2 and water. $k_{rg}$ goes from 0 to 1 when $u$ goes from 0 to 1 (when $u=1$ we have only CO2 and single phased flow).
![[IMG_0348.jpg|600]]
Let's set
$$\begin{aligned}
k_{rg}&= u^{2}\\
k_{rw}&= (1-u)^{2}.
\end{aligned}$$
Now we can write down the conservation laws.
$$\begin{aligned}
\frac{\text{d}}{\text{d}t}\iiint_{\Omega }\phi \rho _{g}u \text{ d}V+ \iint_{\partial \Omega }\rho _{g}\vec{q}_{g}\cdot \vec{n}\text{ d}S&= 0,\\
\frac{\text{d}}{\text{d}t}\iiint_{\Omega }\phi \rho _{w}(1-u) \text{ d}V+ \iint_{\partial \Omega }\rho _{w}\vec{q}_{w}\cdot \vec{n}\text{ d}S&= 0.
\end{aligned}$$
Let's simplify to 1D. 
$L:$ distance between wells.
Assume that $\rho _{g},\rho _{w},k,\mu _{w},\mu _{g},\phi$ are constant.
For gas:
$$\begin{aligned}
\frac{\text{d}}{\text{d}t}\left(\int_{a }^{b}\phi \rho _{g}u(x,t) \text{ d}x \right)A+ \rho _{g}(\vec{q}_{g}(b,t)-\vec{q}_{g}(a,t))A&=  0\\
\phi u_{t}+(q_{g})_{x}&= 0
\end{aligned}$$
For brine:
$$\begin{aligned}
\frac{\text{d}}{\text{d}t}\left(\int_{a }^{b}\phi \rho _{w}(1-u(x,t)) \text{ d}x \right)A+ \rho _{w}(\vec{q}_{w}(b,t)-\vec{q}_{w}(a,t))A&=  0\\
-\phi u_{t}+(q_{w})_{x}&= 0
\end{aligned}$$
Adding the two equations together:
$$\begin{aligned}
(q_{g}+q_{w})_{x}&= 0\\
q_{g}(x,t)+q_{w}(x,t)&= q_{T}(t),
\end{aligned}$$
where $q_{T}$ is the total flux density, only depends on time.

Assume that $q_{T}$ is constant.
$$\begin{aligned}
q_{g}&= -k_{rg}(u)\frac{k}{\mu _{g}}\frac{\partial p}{\partial x}\\
q_{w}&= -k_{rw}(u)\frac{k}{\mu _{w}}\frac{\partial p}{\partial x}
\end{aligned}$$
Simplify notation by setting $\lambda  _{g}=\frac{k_{rg}}{\mu _{g}}$. Then
$$\begin{aligned}
q_{g}&= -\lambda _{g}(u)k\frac{\partial p}{\partial x}\\
q_{w}&= -\lambda _{w}(u)k\frac{\partial p}{\partial x}
\end{aligned}$$
Then adding them together,
$$\begin{aligned}
-kp_{x}(\lambda _{g}+\lambda _{w})&= q_{T}\\
-k p_{x}&= \frac{q_{T}}{\lambda _{g}+\lambda _{w}}
\end{aligned}$$
$$\begin{aligned}
q_{g}&= -\lambda _{g}kp_{x}\\
&= q_{T}\frac{\lambda _{g}(u)}{\lambda _{g}(u)+\lambda _{w}(u)}
\end{aligned}$$

$$\phi u_{t}+q \left(\frac{\lambda _{g}(u)}{\lambda _{g}(u)+\lambda _{w}(u)} \right)_{x}=0$$
This is hyperbolic with
$$\begin{aligned}
F(u)&= \frac{u^{2}/\mu _{g}}{u^{2} /\mu _{g}+(1-u)^{2}/\mu _{w}}\\
&= \frac{u^{2}}{u^{2}+M (1-u)^{2}},
\end{aligned}$$
where $M =\frac{\mu _{g}}{\mu _{w}}$.

$$\phi u_{t}+q_{T}\left(\frac{u^{2}}{u^{2}+M(1-u)^{2}} \right)_{x}$$
now we want to solve this with the boundary condition $u(0,t)=1$.
Have that $F(0)=0$ and $F(1)=1$. 
By elementary calculations,
$$f(u)=\frac{2Mu(1-u)}{(u^{2}+M(1-u)^{2})^{2}}=F'(u)$$
So $F'(0)=F'(1)=0$ and $F'(u)\ge0$. 

