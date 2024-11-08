![[Pasted image 20241028134134.png|900]]
The total amount of heat energy in a domain $\Omega$ is
$$\iiint_{\Omega }c\rho T \text{ d}V.$$
By Fourier's law, the heat flux contribution per time is 
$$\iint_{\partial \Omega } -\mathbf n \cdot k \nabla T \text{ d}S,$$
where $\mathbf n$ is the normal vector pointing out of the domain.

We also have the energy per time contributed by the heat source
$$\iiint_{\Omega }q \text{ d}V.$$

The total amount of energy must be conserved:
$$\frac{\partial }{\partial t}\iiint_{\Omega }c\rho T \text{ d}V=\iint_{\partial \Omega } -\mathbf n \cdot k \nabla T \text{ d}S+\iiint_{\Omega }q \text{ d}V,$$
where we can apply the divergence theorem to get
$$\frac{\partial }{\partial t}\iiint_{\Omega }c\rho T \text{ d}V=\iiint_{\Omega } \nabla  \cdot (k \nabla T )\text{ d}V+\iiint_{\Omega }q \text{ d}V.$$
Since $\Omega$ is arbitrary, this can be written equivalently in differential form:
$$\frac{\partial }{\partial t}(c \rho T)= \nabla \cdot (k \nabla T)+q.$$

![[Pasted image 20241030122021.png]]
![[Pasted image 20241030122031.png]]
![[Pasted image 20241030122047.png]]
$$\begin{aligned}
-D\frac{\partial }{\partial x}\left((1-x^{2})\frac{\partial T(x)}{\partial x}\right)&= -I(x)+QS(x)a(x,x_{s})\\
-D\frac{\partial }{\partial x}\left((1-x^{2})\frac{\partial T(x)}{\partial x}\right)&= -B_{\text{out}}T(x)-A_{\text{out}}+QS(x)a(x,x_{s})\\
-D\frac{\partial }{\partial x}\left((1-x^{2})\frac{\partial T(x)}{\partial x}\right)+B_{\text{out}}T(x)&= -A_{\text{out}}+QS(x)a(x,x_{s})\\
\end{aligned}$$
We can express $T$ as a particular solution with two homogenous solutions:
$$T(x)=T_{p}(x)+C_{1}y_{1}(x)+C_{2}y_{2}(x),$$
such that
$$\begin{aligned}
-D\frac{\partial }{\partial x}\left((1-x^{2})\frac{\partial T_{p}(x)}{\partial x}\right)+B_{\text{out}}T_{p}(x)&= -A_{\text{out}}+QS(x)a(x,x_{s})\\
-D\frac{\partial }{\partial x}\left((1-x^{2})\frac{\partial y_{i}(x)}{\partial x}\right)+B_{\text{out}}y_{i}(x)&= 0\quad\text{for }i=1,2.
\end{aligned}$$

https://www.iitg.ac.in/shyamashree/Lecture16-2016.pdf

### inserting sum into hom. eq.

$$\begin{aligned}
-D(1-x^{2})y''(x)-2xy'(x)+B_{\text{out}}y(x)&= 0\\
-Dy''(x)-\frac{2x}{1-x^{2}}y'(x)+\frac{B_{\text{out}}}{1-x^{2}}y(x)&= 0
\end{aligned}$$
Let $y(x)=\sum_{n=0}^{\infty}\alpha _{n}x^{n}$. Then, the homogenous equations becomes
$$\begin{aligned}
-D(1-x^{2})y''(x)-2xy'(x)+B_{\text{out}}y(x)&= 0\\
-D(1-x^{2})\frac{\partial ^{2}}{\partial x^{2}}\left(\sum_{n=0}^{\infty}\alpha _{n}x^{n} \right)-2x \frac{\partial }{\partial x}\left(\sum_{n=0}^{\infty}\alpha _{n}x^{n} \right)+B_{\text{out}}\sum_{n=0}^{\infty}\alpha _{n}x^{n}&= 0\\
-D(1-x^{2})\sum_{n=2}^{\infty}\alpha _{n}\frac{1}{n(n-1)}x^{n-2}-2x \sum_{n=1}^{\infty}\alpha _{n}\frac{1}{n}x^{n-1}+B_{\text{out}}\sum_{n=0}^{\infty}\alpha _{n}x^{n}&= 0\\
-D(1-x^{2})\sum_{n=0}^{\infty}\alpha _{n+2}\frac{1}{(n+2)(n+1)}x^{n}-2x \sum_{n=0}^{\infty}\alpha _{n+1}\frac{1}{n+1}x^{n}+B_{\text{out}}\sum_{n=0}^{\infty}\alpha _{n}x^{n}&= 0\\
\sum_{n=0}^{\infty}\left[-D(1-x^{2})\frac{\alpha _{n+2}}{(n+2)(n+1)}-2x \frac{\alpha _{n+1}}{n+1}+B_{\text{out}}\alpha _{n} \right]x^{n}&= 0
\end{aligned}$$
Since $\frac{1}{1-x^{2}}=\sum_{n=0}^{\infty}x^{2n}$ for $\lvert x \rvert<1$, 
$$\begin{aligned}
\sum_{n=0}^{\infty}\left[-D\frac{\alpha _{n+2}}{(n+2)(n+1)}-\frac{2x}{1-x^{2}} \frac{\alpha _{n+1}}{n+1}+\frac{B_{\text{out}}}{1-x^{2}}\alpha _{n} \right]x^{n}&= 0
\end{aligned}$$

This equation must be valid for $x=0$, where only the summand $n=0$ contribute to the sum:
$$\begin{aligned}
\sum_{n=0}^{\infty}\left[-D(1-0)\frac{\alpha _{n+2}}{(n+2)(n+1)}-2 \cdot 0\cdot  \frac{\alpha _{n+1}}{n+1}+B_{\text{out}}\alpha _{n} \right]0^{n}&= 0\\
-D\frac{\alpha _{2}}{2}+B_{\text{out}}\alpha _{0}&= 0
\end{aligned}$$
Setting $x=1$:
$$\begin{aligned}
\sum_{n=0}^{\infty}\left[-D(1-1^{2})\frac{\alpha _{n+2}}{(n+2)(n+1)}-2 \frac{\alpha _{n+1}}{n+1}+B_{\text{out}}\alpha _{n} \right]1^{n}&= 0\\
\sum_{n=0}^{\infty}\left[-2 \frac{\alpha _{n+1}}{n+1}+B_{\text{out}}\alpha _{n} \right]&= 0 
\end{aligned}$$



$$\begin{aligned}
-D\frac{\partial }{\partial x}\left((1-x^{2})\frac{\partial }{\partial x} \left(\sum_{n=0}^{\infty}\alpha _{n}x^{n} \right)\right)+B_{\text{out}}\sum_{n=0}^{\infty}\alpha _{n}x^{n}&= 0\\
-D \frac{\partial }{\partial x} \left((1-x^{2})\sum_{n=1}^{\infty}\alpha _{n}\frac{1}{n}x^{n-1} \right)+B_{\text{out}}\sum_{n=0}^{\infty}\alpha _{n}x^{n} &= 0\\
\sum_{n=0}^{\infty}\alpha _{n}\left[-\frac{D}{n} \frac{\partial }{\partial x} \left(x^{n-1}-x^{n+1}\right)+B_{\text{out}}x^{n} \right]&= 0\\
\sum_{n=0}^{\infty}\alpha _{n}\left[\frac{D}{n(n-1)}x^{n-2}-\frac{D}{n(n+1)}x^{n} +B_{\text{out}}x^{n} \right]&= 0\\

\end{aligned}$$
### using wiki solution
The homogenous equation is of the form of the general Legendre equation,
$$(1-x)^{2}y''-2xy'+\left[\lambda (\lambda +1)-\frac{\mu ^{2}}{1-x^{2}} \right]y=0,$$
where in our problem $\lambda (\lambda +1)=-\frac{B_{\text{out}}}{D}$, and $\mu =0$. The two linearly independent solutions are
![[Pasted image 20241108130254.png|800]]
Where
![[Pasted image 20241108130943.png|300]]
and
![[Pasted image 20241108131008.png|400]]
Denoting $y_{1}(x)=P^{0}_{\lambda}$, we have
$$\begin{aligned}
y_{1}(x)&= \frac{1}{\Gamma (1)}\,\prescript{}{2}F_{1}\left(-\lambda , \lambda +1,1,\frac{1-x}{2}\right)\\
&= \sum_{n=0}^{\infty}\frac{(-\lambda )_{n}(\lambda +1)_{n}}{(1)_{n}}\cdot \frac{x^{n}}{n!}\\
&= \sum_{n=0}^{\infty}\prod_{k=0}^{n-1}\frac{(-\lambda-k)(\lambda +1-k) }{(1-k)}
\end{aligned}$$




![[Pasted image 20241105142315.png]]
