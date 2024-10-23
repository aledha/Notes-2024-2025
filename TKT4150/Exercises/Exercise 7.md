![[Pasted image 20241023132545.png|800]]
Navier Stokes
$$\frac{\partial \mathbf v}{\partial t}+(\mathbf v \cdot \nabla )\mathbf v=-\frac{\nabla p}{\rho }+\frac{\mu }{\rho }\nabla ^{2}\mathbf v$$
Steady flow, so $\frac{\partial \mathbf v}{\partial t}=0$. Constant pressure gradient, independant of $y$.
$$\begin{aligned}
\mathbf {\dot v}=0&= -\frac{\nabla p}{\rho }+\frac{\mu }{\rho }\nabla ^{2}\mathbf v
\end{aligned}$$
Flow $\mathbf v=\begin{bmatrix}u(y) \\ 0  \\  0\end{bmatrix}$. Then we have only one equation:
$$\begin{aligned}
\frac{\partial p}{\partial x}&= \mu \frac{\partial ^{2}u}{\partial y^{2}},
\end{aligned}$$
since $u$ is independant of $x$. we can integrate
$$\begin{aligned}
\frac{\partial ^{2}u}{\partial y^{2}}&= \frac{1}{\mu }\frac{\partial p}{\partial x}\\
\frac{\partial u}{\partial y}&= \frac{1}{\mu }\frac{\partial p}{\partial x}y+C_{1}\\
u&= \frac{1}{2\mu }\frac{\partial p}{\partial x}y^{2}+C_{1}y+C_{2}\\
u(0)&= C_{2}=0\\
u(h)&= \frac{1}{2\mu }\frac{\partial p}{\partial x}h^{2}+C_{1}h=u_{0}\\
C_{1}&= \frac{u_{0}-\frac{h^{2}}{2\mu }\frac{\partial p}{\partial x}}{h}\\
u(y)&=  \frac{y^{2}}{2\mu }\frac{\partial p}{\partial x}+\frac{u_{0}-\frac{h^{2}}{2\mu }\frac{\partial p}{\partial x}}{h}y
\end{aligned}$$

![[Pasted image 20241023133603.png|800]]
![[Pasted image 20241023133634.png|400]]
![[Pasted image 20241023133618.png|800]]
Stationary, laminar. Straight rigid cube.
Navier Stokes in cylindrical coordinates with $(\mathbf v\nabla) \mathbf v=0$
$$\rho \left(\frac{\partial v_{z}}{\partial t}+v_{r}\frac{\partial v_{z}}{\partial r}+\frac{v_\theta }{r}\frac{\partial v_{z}}{\partial \theta }+v_{z}\frac{\partial v_{z}}{\partial z} \right)=0$$
Setting $\frac{\partial }{\partial \theta },\frac{\partial }{\partial z}\to0$, and $\frac{\partial \mathbf v}{\partial t}=0$, $v_{r}=v_{\theta }=0$. 


$$-\frac{\partial p}{\partial z}+\frac{1}{r}\frac{\partial }{\partial r}(r \tau _{rz})+\frac{1}{r}\frac{\partial \tau _{\theta z}}{\partial \theta }+\frac{\partial \tau _{zz}}{\partial z}+\rho b_{z}$$
$$\frac{\partial p}{\partial z}=\frac{1}{r}\frac{\partial }{\partial r}(r \tau  _{rz})$$
We have 
$$\begin{aligned}
\tau &= 2\mu \mathbf D\\
\tau _{rz}&= 2\mu \left(\frac{\partial v_{z}}{\partial r}+\frac{\partial v_{r}}{\partial z} \right)\frac{1}{2}\\
&= \mu \frac{\partial v_{z}}{\partial r}
\end{aligned}$$
$$\begin{aligned}
r \frac{\partial p}{\partial z}&= \frac{\partial }{\partial r}\left(\mu \frac{\partial v_{z}}{\partial r} \right)\\
\frac{r^{2}}{2}\frac{\partial p}{\partial z}&= \mu \frac{\partial v_{z}}{\partial r}+C_{1}
\end{aligned}$$
