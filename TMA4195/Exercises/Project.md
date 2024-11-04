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
-D \frac{\partial }{\partial x}\left(\left(1-x^{2} \right)\frac{\partial }{\partial x} \left(\sum_{n=1}^{\infty}T_{n}P_{n}(x) \right) \right)&= -I(x)+QS(x)a(x,x_{s})\\
-D\sum_{n=1}^{\infty}T_{n} \frac{\partial }{\partial x}\left(\left(1-x^{2} \right)\frac{\partial P_{n}(x) }{\partial x}  \right)&= -I(x)+QS(x)a(x,x_{s})\\
-D\sum_{n=1}^{\infty}T_{n} ((1-x^{2})P_{n}')' &= -I(x)+QS(x)a(x,x_{s})\\
-D\sum_{n=1}^{\infty}T_{n} (-n(n+1))P_{n} &= -I(x)+QS(x)a(x,x_{s})\\
D\sum_{n=1}^{\infty}T_{n} n(n+1)P_{n} &= -I(x)+QS(x)a(x,x_{s})\\
Q(x_{s})&= \frac{I(x)+D\sum_{n=1}^{\infty}T_{n} n(n+1)P_{n}}{S(x)a(x,x_{s})}
\end{aligned}$$

