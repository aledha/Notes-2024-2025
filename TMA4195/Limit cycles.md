
Consider a dampened harmonic motion:
![[IMG_0301.jpg|600]]
Hooke's law:
$$F=-kx$$
Friction:
$$F=-ax'$$
Newtons
$$
\begin{aligned}
mx''&= -kx-ax'\\
	x''+\frac{a}{m}x'+\frac{k}{m}x&=0 
\end{aligned}
$$
The friction term $\frac{a}{m}x'$ sucks energy out of the system.
### $a=0$ 
we have a solution
$$x(t)=A \cos \sqrt{\frac{k}{m}}t+B \sin \sqrt{\frac{k}{m}}t$$
which is just a circle, conserving energy.

We can rewrite the second order to ODE into a system of first order ODEs
$$\begin{aligned}
x&= x_{1}\\
x'&= x_{2}\\
x'_{1}&= x_{2}\\
x'_{2}&= -\frac{k}{m}x_{1}-\frac{a}{m}x_{2}
\end{aligned}$$
$(0,0)$ is the only equilibrium point
$$
\begin{bmatrix}x_{1}'  \\ x_{2}'\end{bmatrix}= \begin{bmatrix}0 & 1  \\ -\frac{k}{m} & -\frac{a}{m}\end{bmatrix}
$$


## Van der Pol Oscillations

$$x''-\mu (1-x^{2})x'+x=0,$$
where $\mu >0$.

$$
\begin{aligned}
x_{1}&= x\\
x_{2}&= x'
\end{aligned} \quad\implies\quad \begin{aligned}
x_{1}'&= x_{2}\\
x_{2}'&= \mu (1-x^{2})x_{2}-x_{1}
\end{aligned}
$$
$x_{1}=0,\quad x_{2}=0$ gives $x_{1}'=x_{2}'=0$, an equilibrium point.
Jacobi is
$$
J = \begin{bmatrix}0 & 1 \\ 2\mu x_{1}x_{2}-1 & \mu (1-x^{2}_{1})\end{bmatrix}
$$
For $x_{1}=x_{2}=0$,
$$J = \begin{bmatrix}0 & 1 \\ -1 & \mu \end{bmatrix}$$
$\text{trace}(J)=\mu ,\quad \det J=1$. 
Since $\mu >0$, this is an unstable equilibrium point.

Inspect the equation:
$$x''-\mu (1-x^{2})x'+x=0.\tag{*}$$
When $x^{2}>1$, energy is fed into the system, and when $x^{2}<1$, energy is drained from the system.

$\mu (1-x^{2})$ is an even function in $x$, while $x$ is odd.

## Li'enard equation
This was an case of the more general
$$x''+f(x)x'+g(x)=0$$
where $f$ is even and $g$ is odd.

If 
1. $g(x)>0,\quad x>0$.
2. Define $F(x)=\int_{0}^{x}f(s)\text{ d}s$. 
   $\lim_{x \to \infty}F(x)=\infty$
3. $F(x)$ has a single zero $p>0$,
   and $F(x)<0$ for $0<x<p$
Then the solution is a *limit cycle*.

Let's inspect $(*)$:
$$g(x)=x>0$$
$$\begin{aligned}
F(x)&= -\mu \int_{0}^{x}(1-s^{2})\text{ d}s\\
&= -\mu \left(x-\frac{1}{3}x^{3}\right)\\
&= -\mu x \left(1-\frac{1}{3}x^{2} \right)
\end{aligned}$$
$F$ goes to infinity when x goes to infinity. 
$F$ has the single zero $p=\sqrt{3}$, and $F(x)<0$ for $0<x<\sqrt{3}$.
Then the solution is a limit cycle.