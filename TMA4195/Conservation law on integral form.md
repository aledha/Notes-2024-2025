$J(0,t)-J(a,t)$

$$\frac{\text{d}}{\text{d}t}\int_{a}^{b}c(x) T(x,t)\text{ d}x+\left(k(b)\frac{\partial T}{\partial x}(b,t)-k(a)\frac{\partial T}{\partial x}(a,t) \right)=0$$
Solve
$$\begin{aligned}
\frac{\partial T}{\partial t}&= \frac{k_{1}}{c_{1}}\frac{\partial ^{2}T}{\partial x^{2}} \quad\text{for }0<x<M\\
\frac{\partial T}{\partial t}&= \frac{k_{2}}{c_{2}}\frac{\partial ^{2}T}{\partial x^{2}} \quad\text{for }M<x<L
\end{aligned}$$
we also have the BC
$$\begin{aligned}
T(0,t)&= T_{0},\quad T(b,t)=T_{1}\\
T(M^{-},t)&= T(M^{+},t)\\
-k_{1}\frac{\partial T}{\partial x}(M^{-},t)&= -k_{2}\frac{\partial T}{\partial x}(M^{+},t)
\end{aligned}$$
if $k_{1}≠k_{2}\quad\implies\quad$
$$\frac{\partial T}{\partial x}(M^{-},t)=\frac{k_{2}}{k_{1}}\frac{\partial T}{\partial x}(M^{-},t)$$

## Method of characteristics
$$u_{t}+a(u,x,t)u_{x}=b(u,x,t)$$
and $u(x,0)=u_{0}$.
Reduce this to a dynamical system
$$\begin{aligned}
	x'&= f_{1}(x,z,t)\qquad x(0)=x_{0}\\
z'&= f_{2}(x,z,t)\qquad z(0)=u_{0}(x_{0})
\end{aligned}$$
for each $x_{0}\in \mathbb{R}$.
For each $x_{0}$, we want to find a curve $x(t;x_{0})=x(t)$ and
$$z(t;x_{0})=z(t)=u(x(t;x_{0}),t)=u(x(t),t)$$
Given $x,t$, we can find $x_{0}(x,t)$. Then,
$$u(x,t)=z(t,x_{0}(x,t))$$
$$\begin{aligned}
x'&= a(z,x,t)\\
z'&= b(z,x,t)\\
x(0)&= x_{0}\\
z_{0}&= u_{0}(x_{0})
\end{aligned}$$
solve this for every $x_{0}$.

### Example
$$u_{t}+\underbrace{3t^{2}}_{a}u_{x}= \underbrace{u^{2}}_{b},\qquad u(x,0)=u_{0}.$$
Set 
$$\begin{aligned}
x'&= 3t^{2}\quad\implies\quad x(t)= t^3+x_0\\
z'&= z^{2} \\
\frac{\text{d}z}{\text{d}z^{2}}&= \text{ d}t\\
-\frac{1}{z}&= t-C\\
z(t)&= \frac{1}{C-t}\\
z(0)& =\frac{1}{C}=u_{0}(x_{0})\\
z(t)&= \frac{u_{0}(x_{0})}{1-u_{0}(x_{0})t}.
\end{aligned}$$
We see that
$$x_{0}=x-t^{3}$$
then,
$$u(x,t)=\frac{u_{0}(x-t^{3})}{1-u_{0}(x-t^{3})t}$$

## Hyperbolic conservation laws
Look at 
$$\begin{aligned}
u_{t}+f(u)u_{x}&= 0\\
u_{t}+(F(u))_{x}&= 0
\end{aligned}$$
$a=f(u),b=0$ where $F'(u)=f(u)$.
$F(u)$ flux density (=flux in 1D)
$u$ conserved density

### Example 1
$$u_{t}+au_{x}=0,\qquad u(x,0)=u_{0},$$
and $a \in \mathbb{R}$.
$$\begin{aligned}
x'&= a\\
x(t)&= at+x_{0}\\
z'&= 0\\
z(t)&= u_{0}(x_{0})
\end{aligned}$$
then
$$\begin{aligned}
x_{0}&= x-at\\
u(x,t)&= u_{0}(x-at)
\end{aligned}$$
which is simply a translation of the initial value.

### Example 2
$$u_{t}+f(u)u_{x}=0\qquad u(x_{0})=\begin{cases}
u^{-} & x<0 \\
u^{+} & x>0
\end{cases}$$
$$\begin{aligned}
x'&= f(z)\\
z'&= 0
\end{aligned}\quad\implies\quad \begin{aligned}
z(t)&= u_{0}(x_{0})\\
x'&= f(u_{0}(x_{0}))
\end{aligned}$$
since $z(t)=u_{0}(x_{0})$ is constant,
$$\begin{aligned}
x(t)&= f(u_{0}(x_{0}))t+x_{0}\\
z(t)&= u_{0}(x_{0})
\end{aligned}$$

Assume $f(u^{-})<f(u^{+})$:
For characteristics starting at $x_{0}<0$, then
$$x=f(u^{-})t+x_{0}.$$
For $x_{0}>0$, then
$$x=f(u^{+})t+x_{0}$$