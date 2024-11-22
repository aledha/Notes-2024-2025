![[Pasted image 20241115121724.png|800]]
![[Pasted image 20241115121804.png|800]]
![[Pasted image 20241115121817.png|800]]


We have now computed an equilibrium solution $T$, and are interested in analyzing the stability. Consider a small perturbation $\delta T$ around the equilibrium solution. Substituting $T+\delta T$ in (REF) yields
$$
\begin{aligned}
C_{a}\frac{\partial }{\partial t}(T+\delta T)&= D\frac{\partial }{\partial x}\left((1-x^{2})\frac{\partial }{\partial x}(T+\delta T)\right)-B_{\text{out}}(T+\delta T) -A_{\text{out}}+QS(x)a(x,x_{s})\\
C_{a}\frac{\partial T}{\partial t} + C_{a}\frac{\partial \delta T}{\partial t}&= D\frac{\partial }{\partial x}\left((1-x^{2})\frac{\partial T}{\partial x}\right)-B_{\text{out}}T -A_{\text{out}}+QS(x)a(x,x_{s})+ D \frac{\partial }{\partial x}\left((1-x^{2})\frac{\partial \delta T}{\partial x}\right)-B_{\text{out}} \delta T.
\end{aligned}
$$
Since $T$ is the equilibrium solution, this simplifies to
$$
\begin{aligned}
C_{a}\frac{\partial \delta T}{\partial t}&= D \frac{\partial }{\partial x}\left((1-x^{2})\frac{\partial \delta T}{\partial x} \right)-B_{\text{out}}\delta T\\
&= D(1-x^{2})\frac{\partial ^{2}\delta T}{\partial x^{2}}-2Dx \frac{\partial \delta T}{\partial x}-B_{\text{out}}\delta T.
\end{aligned}
$$
Let's use the ansatz $\delta T=e^{\lambda t}u(x)$. We want to investigate the value of $\lambda$ for a $u\neq0$, where a negative value of $\lambda$ means that the perturbation sinks as a function of time, and that the equilibrium solution is stable. Using this ansatz leads to the equation
$$\begin{aligned}
C_{a}\frac{\partial }{\partial t}(e^{\lambda t}u(x))&=  D(1-x^{2})\frac{\partial ^{2}}{\partial x^{2}}(e^{\lambda t}u(x))-2Dx \frac{\partial }{\partial x}(e^{\lambda t}u(x))-B_{\text{out}}(e^{\lambda t}u(x))\\
\lambda C_{a}e^{\lambda t}u(x)&= D(1-x^{2})e^{\lambda t}u''(x)-2Dxe^{\lambda t}u'(x)-B_{\text{out}}e^{\lambda t}u(x)\\
\lambda u(x)&= \frac{D}{C_a}\left[(1-x^{2})u''(x)-2x u'(x)-\frac{B_{\text{out}}}{D}u(x) \right].
\end{aligned}$$
Take the spatial discretization $x_i=ih$ for $i=0,\dots, n$, and denote $u_i=u(x_i)$. We will utilize the second order central difference approximations
$$\begin{aligned}
\frac{\partial u_i}{\partial x}&= \frac{u_{i+1}-u_{i-1}}{2h}+ \mathcal{O}(h^2 ),\\
\frac{\partial ^2 u_i}{\partial x^2}&= \frac{u_{i+1}-2u_i+u_{i-1}}{h^2}+\mathcal{O}(h^2).
\end{aligned}$$
The discretized equation for the interior nodes becomes
$$
\begin{aligned}
\lambda u_i&= \frac{D}{C_a}\left[(1-x_i^{2})\frac{u_{i+1}-2u_i+u_{i-1}}{h^2}-2x_i \frac{u_{i+1}-u_{i-1}}{2h}-\frac{B_{\text{out}}}{D}u_i \right]\\
\lambda C_au_i&= \frac{D}{C_a}\left[\left(\frac{1-(ih)^2}{h^2}-\frac{ih}{h} \right)u_{i+1}+\left(-\frac{2(1-(ih)^2)}{h^2}-\frac{B_\text{out}}{D} \right)u_i+\left(\frac{1-(ih)^2}{h^2}+\frac{ih}{h} \right)u_{i+1} \right]\\\
\lambda C_au_i&= \frac{D}{C_a}\left[\left(\frac{1}{h^2}-i^2-i \right)u_{i+1}+\left(-\frac{2}{h^2}+2i^2-\frac{B_\text{out}}{D} \right)u_i+\left(\frac{1}{h^2}-i^2+i \right)u_{i+1} \right].
\end{aligned}
$$
For $i=0$, we use forward differences to get 
$$
\begin{aligned}
\lambda  u_0 &= \frac{D}{C_a}\left[\frac{\partial ^2 u_0}{\partial x^2}-\frac{B_\text{out}}{D}u_0 \right]\\
\lambda u_0 &= \frac{D}{C_a} \left[\frac{u_{2}-2u_{1}+u_0}{h^2}-\frac{B_\text{out}}{D}u_0 \right]\\
\lambda u_0 &= \frac{D}{C_a} \left[\frac{1}{h^2}u_2-\frac{2}{h^2}u_1+\left(\frac{1}{h^2}-\frac{B_\text{out}}{D} \right)u_0 \right].
\end{aligned}
$$
For $i=n$, we use first order backward differences
$$
\begin{aligned}
\lambda  u_n&=\frac{D}{C_a} \left[-2 x_n \frac{\partial u_n}{\partial x}-\frac{B_\text{out}}{D}u_n \right]\\
\lambda C_a u_n&= \frac{D}{C_a} \left[-2 \frac{u_n-u_{n-1}}{h}-\frac{B_\text{out}}{D}u_n \right]\\
\lambda u_n&= \frac{D}{C_a} \left[\left(-\frac{2}{h}-\frac{B_\text{out}}{D} \right)u_n+\frac{2}{h}u_{n-1} \right].
\end{aligned}
$$
Then we have an eigenvalue problem of the form $\lambda \mathbf u=\mathbf M \mathbf u$, which we will compute numerically for different choices of the number of spatial nodes $n$. 


![[Pasted image 20241118082240.png|800]]
### no ansatz
Take the spatial discretization $x_i=ih$ for $i=0,\dots, n$, and denote $\delta T_i=\delta T(x_i)$. We will utilize the second order central difference approximations
$$\begin{aligned}
\frac{\partial \delta T_i}{\partial x}&= \frac{\delta T_{i+1}-\delta T_{i-1}}{2h}+ \mathcal{O}(h^2 ),\\
\frac{\partial ^2 \delta T_i}{\partial x^2}&= \frac{\delta T_{i+1}-2\delta T_i+\delta T_{i-1}}{h^2}+\mathcal{O}(h^2).
\end{aligned}$$
The discretized equation becomes
$$\begin{aligned}
C_a \frac{\partial \delta T_i}{\partial t}&= D(1-x_i^2)\frac{\delta T_{i+1}-2\delta T_i+\delta T_{i-1}}{h^2}-2Dx_i \frac{\delta T_{i+1}-\delta T_{i-1}}{2h}-B_\text{out}\delta T_i+\mathcal{O}(h^2)\\
C_a \frac{\partial \delta T_i}{\partial t}&= \left(\frac{1}{h^2}D(1-(ih)^2)-\frac{1}{h}Dih\right)\delta T_{i+1} + \left(-\frac{2}{h^2}D(1-(ih)^2) -B_\text{out}\right)\delta T_i+\left(\frac{1}{h^2}D(1-(ih)^2)+\frac{1}{h}Dih\right)\delta T_{i-1}+\mathcal{O}(h^2)\\
\frac{\partial \delta T_i}{\partial t}&= \frac{D}{C_a}\left[ \left(\frac{1}{h^2}-i^2-i\right)\delta T_{i+1} + \left(-\frac{2}{h^2}+2i^2-\frac{B_\text{out}}{D} \right)\delta T_i + \left(\frac{1}{h^2}-i^2+i \right)\delta T_{i-1} \right]+\mathcal{O}(h^2)
\end{aligned}$$
for $i=1,\dots,n-1$. With $\mathbf {\tilde T}(t)=\begin{bmatrix}\delta T_0(t)  &  \delta T_2(t)  & \dots   &  \delta T_n(t)\end{bmatrix}^T$, we can write this as a matrix equation
$$\mathbf {\tilde T}'(t)=\mathbf M \mathbf {\tilde T}(t)+\mathcal{O}(h^2).$$
This is stable if and only if the eigenvalues of $\mathbf M$ are less than $1$.
$$\mathbf M_{ij}=\frac{D}{C_a}\begin{cases}
\frac{1}{h^2}-i^2-i &\quad\text{for } i=j-1 \\
-\frac{2}{h^2}+2i^2-\frac{B_\text{out}}{D} & \quad\text{for } i=j \\
\frac{1}{h^2}-i^2+i & \quad\text{for }i= j+1\\
0 & \quad\text{otherwise}
\end{cases}$$

### Ansatz $\delta T=e^{\lambda t}u(x)$ 
$$\begin{aligned}
C_{a}\frac{\partial }{\partial t}(e^{\lambda t}u(x))&=  D(1-x^{2})\frac{\partial ^{2}}{\partial x^{2}}(e^{\lambda t}u(x))-2Dx \frac{\partial }{\partial x}(e^{\lambda t}u(x))-B_{\text{out}}(e^{\lambda t}u(x))\\
\lambda C_{a}e^{\lambda t}u(x)&= D(1-x^{2})e^{\lambda t}u''(x)-2Dxe^{\lambda t}u'(x)-B_{\text{out}}e^{\lambda t}u(x)\\
0&= D(1-x^{2})u''(x)-2Dx u'(x)-(B_{\text{out}}+\lambda C_{a})u(x)\\
0&= D(1-x_i ^2 )\frac{u_{i+1}-2u_i+u_{i-1}}{h^2}-2Dx_i \frac{u_{i+1}-u_{i-1}}{2h}-(B_\text{out}+\lambda C_a)u_i\\
0&= \left[\frac{D(1-x_i^2)}{h^2}-\frac{Dx_i}{h} \right] u_{i+1}+\left[-\frac{2D(1-x_i^2)}{h^2}-(B_\text{out}+\lambda C_a) \right]u_i+\left[\frac{D(1-x_i^2)}{h^2}+\frac{Dx_i}{h} \right]u_{i-1}\\
0&= \left[\frac{D}{h^2}-Di^2-Di \right] u_{i+1}+\left[-\frac{2D}{h^2}+2Di^2-(B_\text{out}+\lambda C_a) \right]u_i+\left[\frac{D}{h^2}-Di^2+Di \right]u_{i-1}\\
0&= \mathbf M \mathbf u,
\end{aligned}$$
where 
$$M_{ij}=D \begin{cases}
\frac{1}{h^2}-i^2-i & \quad\text{for }i=j-1 \\
-\frac{2}{h^2}+2i^2-\frac{B_\text{out}+\lambda C_a}{D} & \quad\text{for }i=j \\
\frac{1}{h^2}-i^2+i & \quad\text{for }i=j+1 
\end{cases}$$
---
OR
