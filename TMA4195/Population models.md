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

$N'=rN \quad\implies\quad N(t)=N(0)e^{rt}$

$\beta N_{0}$ scale for $H$:
$$N'=-\alpha (\beta N_{0})N$$

### Scaling
* $N\to N_0 N$
* $H\to \beta N_{0}H$
* $t\to \frac{1}{q}t$

$$\begin{aligned}
qN_{0}N'(t)&= rN_{0}N\left(1-\frac{N_{0}N}{N_{0}}\right)-\alpha \beta N_{0}HN_{0}N-u_{N}N_{0}N\\
qN'(t)&= rN\left(1-N\right)-\alpha \beta HN_{0}N-u_{N}N\\
\frac{q}{r}N'(t)&= N(1-N)-\frac{\alpha \beta N_{0}}{r}NH-\frac{u_{N}}{r}N
\end{aligned}$$
Let $\epsilon = \frac{q}{r}$, $\eta =\frac{\alpha \beta N_{0}}{r},\quad f_{N}=\frac{u_{N}}{r}$. The first equation becomes
$$\epsilon N'(t)= N(1-N)-\eta NK-f_{N}N$$

the second equation is
$$\begin{aligned}
q \beta N_{0}H'(t)&=  q\beta N_{0}H \left(1-\frac{\beta N_{0}H}{\beta N_{0}N} \right)-u_{H}\beta N_{0}H\\
H'(t)&= H\left(1-\frac{H}{N}\right)-f_{H}H
\end{aligned}$$
where $f_{H}=\frac{u_{H}}{q}$.

## Equilibrium points

We set the RHS of both equations to zero:
$$f(N)=N((1-N)-\eta H-f_{N} )=0$$
lets see what happens if $H=0$. then $N=0$ or $N=1-f_{N}$.
The other RHS is
$$H \left(1-\frac{H}{N}-f_{H} \right)=0, \quad N>0$$
Which has $(1-f_{N},0)$ as equilibrium points.
For $H\neq0$:
$$\begin{aligned}
1-\frac{H}{N}-f_{H}&= 0\\
H&= N(1-f_{H})
\end{aligned}$$
Substitute in the first equation
$$\begin{aligned}
1-N-\eta (1-f_{H})N-f_{N}&= 0\\
N&= \frac{1-f_{N}}{1+\eta (1-f_{H})}
\end{aligned}$$
Then we have found the eq point
$$\frac{1-f_{N}}{1+\eta (1-f_{H})},\frac{(1-f_{H})(1-f_{N})}{1+\eta (1-f_{H})}$$
$$\begin{aligned}
f_{1}(N,H)&= \frac{1}{\epsilon }\left(N-N^{2}-\eta HN-f_{N}N \right)\\
f_{2}(N,H)&= H-\frac{H^{2}}{N}-f_{H}H
\end{aligned}$$
Jacobi matrix is
$$J=\begin{bmatrix}\frac{1}{\epsilon }(1-2N-\eta H-f_{N}) & -\frac{\eta }{\epsilon }N \\ \frac{H^{2}}{N^{2} } & 1-2\frac{H}{N}-f_{H}\end{bmatrix}$$
When at equilibrium, we know that 
$$\begin{aligned}
N(1-N-\eta H-f_{N})&= 0\\
\eta H&= (1-f_{N})-N
\end{aligned}$$
Substitute this in the Jacobi, and $H=(1-f_{H})N$
$$\begin{aligned}
J&= \begin{bmatrix}\frac{1}{\epsilon }(1-2N-(1-f_{N})+N-f_{N}) & -\frac{\eta }{\epsilon }N \\ \frac{H^{2}}{N^{2} } & 1-2\frac{H}{N}-f_{H}\end{bmatrix}\\
&= \begin{bmatrix}-\frac{1}{\epsilon }N & -\frac{\eta }{\epsilon }N \\ (1-f_{H})^{2} & -(1-f_{H})\end{bmatrix}
\end{aligned}$$
Positive determinant, negative trace as long as $f_{H}<1$ $\quad\implies\quad$ *stable*

### Optimal fishing rate

$$N_{e}=\frac{1-f_{N}}{1+\eta (1-f_{H})}$$
The actual rate of catching $N$ is (using $f_{N}=\frac{u_{N}}{r}$)
$$\begin{aligned}
u_{N}N_{0}N_{e}&= rf_{N}N_{0}N_{e}\\
&= rN_{0}f_{N}\frac{1-f_{N}}{1+\eta (1-f_{H})}
\end{aligned}$$
parabola in $f_{N}$, has maximum at $f_{N}=\frac{1}{2}$.
