## Constitutive equations
Blood is a two-phase medium consisting of plasma and cells. Blood can be assumed as a Newtonian fluid with viscosity $\mu =1.2\cdot 10^{-3} \mathrm{ Pa\cdot s}=1.2 \mathrm{cP}$. (cp=centaipaise$=1\cdot 10^{-3}$ Pas), while water has $\mu =1.0\cdot 10^{-3}$.

Plasma: $90\%$ water, $7\%$ proteins and other stuff.
Normally, around $50$ vol% of blood is red blood cells. 
	In human blood, red cells at rest are small disc-shaped cells.  
	$3(8)\,\mathrm{\mu m}$ in length (height).
White blood cells represent less than $0.15$ vol.% of blood.
The volume% of cells is called *Hematocrit* ($H$).
	$H=0$: only plasma.
	$H=37\%-53\%$ for healthy adult.

Blood is a visco-plastic non-Newtonian fluid.
In a viscometer, if $\lvert \tau  \rvert<\tau _{y},\dot \gamma =0$.
If $\dot \gamma ≠0$, then $\tau =\eta (\dot \gamma )\dot \gamma$.
![[IMG_0328.jpg|700]]
Viscosity increases for increasing hematocrit.
For flow in capillaries (microvessels with diameter $4-10 \mathrm{\mu m}$) we must use two-phased flow methods (since it is the same size as red blood cells.)

For low shear strain rates ($\lvert \dot \gamma  \rvert<10 \mathrm{s^{-1}}$ and $H<40\%$) we may use *Casson's model for blood*:
$$\sqrt{\tau }=\sqrt{\tau _{y}}+\sqrt{\mu \dot \gamma },\quad \quad\text{for }\dot \gamma >0,$$
where $\tau _{y}$ is the yield shear stress and $\mu =\mu (\theta , H)$, $\theta$ is temperature and $H$ is the hematocrit.

Viscosity function is defined as
$$\eta (\dot \gamma )=\begin{cases}
\mu +\frac{\tau _{y}}{\lvert \dot \gamma  \rvert}+2\sqrt{\mu \frac{\tau _{y}}{\dot \gamma }}, & \quad\text{for }\tau >\tau _{y} \\
\infty, & \quad\text{for }\tau \le \tau _{y}.
\end{cases}$$
For high strain rates, $\lvert \dot \gamma  \rvert>400\,\mathrm{s^{-1}}$, then the blood can be assumed to be a Newtonian fluid. Then,
$$\eta \sim \mu .$$
The constitutive equations for blood as a Casson's fluid,
$$T_{ij}=-p \delta _{ij}+2\eta D_{ij},$$
where we have assumed incompressibility. In matrix notation:
$$\mathbf T=-p \mathbf I+\underbrace{2\eta \mathbf D}_\text{Viscous stresses}$$
Scalar measure of shear for a general 3D strain state:
$$\eta =\eta (\dot \gamma ),\qquad \dot \gamma =\sqrt{2D_{ij}D_{ij}}=\sqrt{2\mathbf D:\mathbf D}$$

### Example, Laminar flow in a blood vessel
We assume a flow driven by a constant pressure gradient $c=-\frac{\partial p}{\partial z}$, where $z$ is the longitudal axis of the vessel. Vessel has diameter $d$.
Furthermore, assume steady flow with a velocity field $v_{z}=v(R)$, where $R$ is the radial coordinate  and the flow at the wall is zero: $v \left(\frac{d}{2} \right)=0$.
$v_{R}=v_{\theta }=0$.
![[IMG_0329.jpg|700]]

We will show that $v(R)$ is a plug flow. i.e., for $R \le r_{P}$ then $\tau <\tau _{y},\quad \dot \gamma =0$. 
$r_{P}$ is the radius of the plug.

Casson's model and viscosity function:
$$\sqrt{\tau }=\sqrt{\tau _{y}}+\sqrt{\mu \dot \gamma },\quad\text{for }\dot \gamma >0 \tag{1}$$
$$\eta (\dot \gamma )=
\mu +\frac{\tau _{y}}{\lvert \dot \gamma  \rvert}+2\sqrt{\mu \frac{\tau _{y}}{\dot \gamma }},  \quad\text{for }\tau >\tau _{y}\tag{2}$$
$$\eta (\dot \gamma )=\infty,  \quad\text{for }\tau \le \tau _{y}\tag{3}.$$
The size of the plug is obtained from equilibrium.

$$\begin{aligned}
\tau 2\pi R \cdot \text{ d}z-\frac{\partial p}{\partial z}\text{ d}z \cdot \pi R^{2}&= 0\\
\left(c=\frac{\partial p}{\partial z} \right)\qquad \implies\qquad  \tau &= -\frac{cR}{2}
\end{aligned}\tag{*}$$
$\tau =\tau _{y}\quad\implies\quad r_{P}=2\frac{\tau _{y}}{c}$.
Flow field only gives one strain rate contribution:
$$2D_{RZ}=\dot \gamma _{Rz}=\frac{\partial V_{z}}{\partial R}+\frac{\partial V_{R}}{\partial z}=\frac{\partial V_{z}}{\partial R}$$
$\tau = \eta \left\lvert \frac{\partial V}{\partial R} \right\rvert$, then
$$\tau =\tau _{Rz}$$
all other components are zero.
![[IMG_0330.jpg|700]]

We have $\tau =-\eta \frac{\partial V}{\partial R}=\eta \dot \gamma$, so
$$\begin{aligned}
\left\lvert \tau  \right\rvert&= \left(\sqrt{\tau _{y}} +\sqrt{\mu \dot \gamma }\right)^{2}\\
\eta &= \frac{\left(\sqrt{\tau _{y}}+\sqrt{\mu \dot \gamma } \right)^{2}}{\left\lvert \frac{\partial V}{\partial R} \right\rvert}
\end{aligned}\tag{1}$$

$$\begin{aligned}
\tau &= -\frac{cR}{2}\\
&= -\left(\sqrt{\tau _{y}}+\sqrt{\mu \dot \gamma } \right)^{2}\\
\sqrt{\tau _{y}}+\sqrt{\mu \dot \gamma }&= \sqrt{\frac{cR}{2}}\\
\dot \gamma &= \frac{1}{\mu }\left(\sqrt{\frac{cR}{2}}-\sqrt{\tau _{y}} \right)^{2}\\
&= -\frac{\text{d}V}{\text{d}R}
\end{aligned}\tag{*}$$

For $r_{p}\le R \le \frac{d}{2}$ (after plug):
$$\frac{\text{d}V}{\text{d}R}=-\frac{1}{\mu }\left(\sqrt{\frac{cR}{2}}-\sqrt{\tau _{y}} \right)^{2}$$
Integrating and using $v(r=d/2)=0$:
$$\begin{aligned}
\frac{\text{d}V}{\text{d}R}&= -\frac{1}{\mu }\left(\frac{cR}{2}-2\sqrt{\frac{cR \tau _{y}}{2}}+\tau _{y} \right)\\
\left(\tau _{y}=\frac{cr_{p}}{2}\right)\qquad\implies\qquad &= -\frac{1}{\mu }\left(\frac{cR}{2}-2\sqrt{\frac{cR \tau _{y}}{2}}+\frac{cr_{p}}{2} \right)\\
V(R)&= -\frac{1}{\mu }\left(\frac{cR^{2}}{4}-\frac{2}{3}\sqrt{r_{p}}R^{\frac{3}{2}}+\frac{cr_{p}}{2}R \right)+k,
\end{aligned}$$
where $k$ is integration constant. Denote $a=\frac{d}{2}$, then $V(a)=0$, then
$$\begin{aligned}
V(a)&= 0\\
	k&= \frac{c}{4\mu }\left(a^{2}-\frac{8}{3}\sqrt{r_{p}}a^{\frac{3}{2}}+2r_{p}a \right)\\
v(R)&= -\frac{1}{4\mu }\left(a^{2}-R^{2}-\frac{8}{3}\sqrt{r_{p}}\left(a^{\frac{3}{2}}-R^\frac{3}{2} \right)+2r_{p}(a-R) \right)
\end{aligned}$$
so this describes velocity outside the plug.
Inside the plug:
$$V_{P}(R=r_{p})$$

Volumetric flow
$$\begin{aligned}
Q&= \int _{r_{p} }^{a}V(R) 2\pi R \text{ d}R+V_{p}\cdot \pi r_{p}^{2}\\
&= \frac{\pi ^{2}a^{4}c}{8\mu }F(\phi )\\
\phi &= \frac{2\tau _{y}}{ac}\\
	F(\phi )&= 1-\frac{16}{7}\phi ^{\frac{1}{3}}+\frac{4}{3}\phi -\frac{1}{21}\phi ^{4}
\end{aligned}$$
if $r_{p}=0$, $F=1,V_{p}=V_{0}=\frac{ca^{2}}{4\mu }$.