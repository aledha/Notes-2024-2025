*Natural growth*:
$$\begin{aligned}
u'&= ku,\\
u(0)&= u_{0}.
\end{aligned}$$

*Logistic growth*:
$$\begin{aligned}
u'&= ku\left(1-\frac{u}{u_{e}}\right),\\
u(0)&= u_{0}
\end{aligned}$$
Two equilibrium points: $u^{(1)}=0, \quad u^{(2)}=u_{e}$.
### Scale 
* $t\to \frac{1}{k}t$
* $u\to u_{e}u$
$$\begin{aligned}
u_{e}ku'&= ku_{e}u \left(1-\frac{u_{e}u}{u} \right)\\
u'&= u(1-u).
\end{aligned}$$
Two equi points: $u^{(1)}=0,\quad u^{(2)}=1$.
$$\begin{aligned}
f(u)&= u-u^{2}\\
f'(u)&= 1-2u
\end{aligned}$$
$u^{(1)}$ is unstable, $u^{(2)}$ is stable.

## Prey-predator model with hunting
We have two species: Prey $N$ and predator $H$. 
$N(t),\quad H(t)$ is the number at time $t$.
$H$ eats $N$, humans eat both.
Predator reproduces slower than prey.

$$\begin{aligned}
N'(t)&= rN\left(1-\frac{N}{N_{0}}\right)-\alpha NH-u_{N}N
\end{aligned}$$
$r$ is the reproduction rate, $\alpha$ is the rate they get eaten by $H$, $u_{N}$ is the rate humans eat $N$.
$$H'(t)=qH \left(1-\frac{H}{\beta N} \right)-u_{H}H$$