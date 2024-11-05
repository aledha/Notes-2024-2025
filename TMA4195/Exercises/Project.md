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
-D \frac{\partial }{\partial x}\left(\left(1-x^{2} \right)\frac{\partial }{\partial x} \left(\sum_{n=0}^{\infty}T_{n}P_{n}(x) \right) \right)&= -I(x)+QS(x)a(x,x_{s})\\
-D\sum_{n=0}^{\infty}T_{n} \frac{\partial }{\partial x}\left(\left(1-x^{2} \right)\frac{\partial P_{n}(x) }{\partial x}  \right)&= -I(x)+QS(x)a(x,x_{s})\\
-D\sum_{n=0}^{\infty}T_{n} ((1-x^{2})P_{n}'(x))' &= -I(x)+QS(x)a(x,x_{s})\\
-D\sum_{n=0}^{\infty}T_{n} (-n(n+1))P_{n}(x) &= -I(x)+QS(x)a(x,x_{s})\\
D\sum_{n=0}^{\infty}T_{n} n(n+1)P_{n}(x) &= -I(x)+QS(x)a(x,x_{s})\\
D\sum_{n=0}^{\infty}T_{n} n(n+1)P_{n}(x) &= B_{\text{out}}T(x)+A_{\text{out}}+QS(x)a(x,x_{s})\\
D\sum_{n=0}^{\infty}\left[n(n+1)T_{n}P_{n}(x)-B_{\text{out}}T_{n}P_{n}(x) \right] &= A_{\text{out}}+QS(x)a(x,x_{s})
\end{aligned}$$
The general Lagrange equation with $\mu =0$ is 
$$\begin{aligned}
(1-x^{2})P''(x)-2xP'(x)+\left[\lambda (\lambda +1)-\frac{\mu ^{2}}{1-x^{2}} \right]P(x)&= 0\\
(1-x^{2})P_{n}''(x)-2xP_{n}'(x)&= -n (n +1)P_{n}(x)
\end{aligned}$$
Then,
$$\begin{aligned}
D\sum_{n=0}^{\infty}\left[-(1-x^{2})T_{n}P_{n}''(x)+2xT_{n}P_{n}'(x)-B_{\text{out}}T_{n}P_{n}(x) \right] &= A_{\text{out}}+QS(x)a(x,x_{s})\\
-D \left[(1-x^{2})T''(x)-2xT'(x)+B_{\text{out}}T(x) \right]&= A_{\text{out}}+QS(x)a(x,x_{s})
\end{aligned}$$




$$\begin{aligned}
-D(1-x^{2})T''(x)+2DxT'(x)+I(x)-QS(x)a(x,x_{s})&= 0\\
D \left((1-x^{2})T''(x)-2xT'(x)) \right)+I(x)-QS(x)a(x,x_{s} &= 0\\
D\left((1-x^{2})T''(x)-2xT'(x) \right)+B_{\text{out}}T(x)&= QS(x)a(x,x_{s})-A_{\text{out}}
\end{aligned}$$
Substituting into our equation,
$$\begin{aligned}
-D\lambda (\lambda +1)T(x)+B_{\text{out}}T(x)&= QS(x)a(x,x_{s})-A_{\text{out}}\\
(-D \lambda (\lambda +1)+B_{\text{out}})T(x)&= QS(x)a(x,x_{s})-A_{\text{out}}
\end{aligned}$$
Let $T(x)=\sum_{n=0}^{\infty}T_{n}P_{n}(x)$, then
$$\begin{aligned}
\sum_{n=0}^{\infty}(-D n (n +1)+B_{\text{out}})T_{n}P_{n}(x)&= QS(x)a(x,x_{s})-A_{\text{out}}
\end{aligned}$$

$$\frac{1}{D}(I(x)-QS(x)a(x,x_{s}))=\left[\lambda (\lambda +1)-\frac{\mu ^{2}}{1-x^{2}} \right]T(x)$$
Since $I(x)=B_{\text{out}}T(x)+A_{\text{out}}$ and $\mu =0$,
$$
\frac{B_{\text{out}}}{D}T(x)+\frac{A_{\text{out}}}{D}= \lambda (\lambda +1) T(x) + \frac{QS(x)a(x,x_{s})}{D},
$$
and then (?)
$$\begin{aligned}
\frac{B_{\text{out}}}{D}&= \lambda (\lambda +1)\\
A_{\text{out}}&= 
\end{aligned}$$

![[Pasted image 20241105142315.png]]
