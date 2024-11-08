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



### inserting sum into hom. eq.
Let $y(x)=\sum_{n=0}^{\infty}\alpha _{n}x^{n}$. Then, the homogenous equations becomes
$$\begin{aligned}
-D\frac{\partial }{\partial x}\left((1-x^{2})\frac{\partial }{\partial x} \left(\sum_{n=0}^{\infty}\alpha _{n}x^{n} \right)\right)+B_{\text{out}}\sum_{n=0}^{\infty}\alpha _{n}x^{n}&= 0\\
\sum_{n=0}^{\infty}\alpha _{n}\left[-D \frac{\partial }{\partial x} \left((1-x^{2})\frac{1}{n}x^{n-1} \right)+B_{\text{out}}x^{n} \right]&= 0\\
\sum_{n=0}^{\infty}\alpha _{n}\left[-\frac{D}{n} \frac{\partial }{\partial x} \left(x^{n-1}-x^{n+1}\right)+B_{\text{out}}x^{n} \right]&= 0\\
\sum_{n=0}^{\infty}\alpha _{n}\left[-\frac{D}{n} \left(\frac{1}{n-1}x^{n-2}-\frac{1}{n+1}x^{n} \right)+B_{\text{out}}x^{n} \right]&= 0\\
\sum_{n=0}^{\infty}\alpha _{n}\left[-\frac{D}{n} \left(\frac{(n+1)x^{n-2}}{(n-1)(n+1)}-\frac{(n-1)x^{n}}{(n-1)(n+1)} \right)+\frac{n(n-1)(n+1)}{n(n-1)(n+1)}B_{\text{out}}x^{n} \right]&= 0\\
\sum_{n=0}^{\infty}\alpha _{n} \left[\frac{-D(n+1)x^{n-2}+(D(n-1)+B_{\text{out}}n(n^{2}-1))x^{n}}{n(n^{2}-1)} \right]&= 0
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
