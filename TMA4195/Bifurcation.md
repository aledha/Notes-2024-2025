"When things split in two"
Considering stability properties when we have an additional parameter.

Start with an example
$$\begin{aligned}
u'&= -u(u-1)(u-2)+\mu \\
&= f(\mu ,u)
\end{aligned}$$
When $\mu =0$, then $f$ is a third degree polynomial:
![[IMG_0302.jpg|300]]

$u=2$ is stable, while $u=1$ is unstable. Solution might oscillate around $u=2$.

If $\mu$ increases more and more, the stable equilibrium point moves to the right, and eventually the unstable point will disappear: 
![[IMG_0303.jpg|300]]
Say we started at $u=0$ and $\mu$ increases past the critical value so that one equilibrium point vanishes, then the system goes to the closest other point.
![[IMG_0303 2.jpg|300]]
## Bifurcation diagram
Another example:
$$u'=(u-\mu )(u-\mu ^{3})=:f(\mu ,u)$$
$f(\mu ,u)=0 \quad\implies\quad u_{e}=\mu ,\quad u_{e}=\mu ^{3}$.
The bifurcation diagram is the two curves for $u_{e}$:

![[IMG_0304.jpg|400]]
To finish the diagram, we need to mark the stability of the equilibrium points.

$$\begin{aligned}
f(\mu ,u)&= u ^{2}-(\mu +\mu ^{3})u+\mu ^{4}\\
\frac{\partial f}{\partial u}&= 2u-(\mu +\mu ^{3})
\end{aligned}$$
we want to track the sign of this partial derivative along the curves.
Along $u=\mu$:
$$\begin{aligned}
\frac{\partial f}{\partial u}(\mu ,\mu )&= 2\mu -\mu -\mu ^{3}\\
&=  \mu(1 -\mu ^{2})
\end{aligned}$$