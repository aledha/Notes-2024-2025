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
\frac{\text{d}z}{z^{2}}&= \text{ d}t\\
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
## Special type: hyperbolic conservation law
$$u_{t}+f(u)u_{x}=0, \qquad u(x,0)=u_{0}(x)$$
Now, $b=0$ and $a=f(u)$. Since $z'=b=0$, the value of $u$ along a characteristic is constant
$$\begin{aligned}
z'&= 0\\
z(t,x_{0})&= u_{0}(x_{0})\\
x'&= f(u)\\
x'&= f(u_{0}(x_{0}))\\
x&= f(u_{0}(x_{0}))t+x_{0}
\end{aligned}$$
To find $x_{0}=x_{0}(x,t)$, draw the characteristics.

### Riemann problem
$$u_{t}+f(u)u_{x}=0,\qquad u(x,0)=\begin{cases}
u^{-} & x<0 \\
u^{+} & x>0
\end{cases}$$
Let's look at the case where $f(u^{-})<f(u^{+})$.

If $f$ is monotonous between $u^{-}$ and $u^{+}$, then
$$u(x,t)=\begin{cases}
u^{-} & \quad\text{for }x<f(u^{-})t \\
f^{-1}\left(\frac{x}{t} \right) & \quad\text{for }f(u^{-})t<x<f(u^{+})t \\
u^{+} & \quad\text{for }x>f(u^{+})t
\end{cases}$$
$f^{-1}\left(\frac{x}{t} \right)$ is the *rarefaction*

### Example
$$u_{t}+u^{3}u_{x}=0,\qquad u(x,0)=\begin{cases}
0 & x<0 \\
1 & x>0
\end{cases}$$
Char are 
$$x=f(u_{0}(x_{0}))t+x_{0}$$
for $x_{0}>0$, 
$$x=1^{3}t+x_{0}=t+x_{0}.$$
For $x_{0}<0$,
$$x=0+x_{0}=x_{0}.$$
For $0<x<t$, the rarefaction is
$$\begin{aligned}
u(x,t)&= f^{-1}\left(\frac{x}{t} \right)\\
&= \left(\frac{x}{t} \right)^{\frac{1}{3}}
\end{aligned}$$
**What happens when characteristics intersect?**
Same equation but
$$u_{t}+u^{3}u_{x}=0,\qquad u(x,0)=\begin{cases}
1 & x<0 \\
0 & x>0
\end{cases}$$
For $x_{0}<0:\quad x=t+x_0$. 
For $x_{0}>0:\quad x=x_{0}$.
We have a shock at $x=0$ for $t=0$ since the characteristics collide.
$$u_{t}+f(u)u_{x}=0\quad\Leftrightarrow\quad u_{t}+(F(u))_{x}=0$$
$F(u)$ is the flux. Pick an interval $[a,b]$, where $a<0$ and $b>0$.
$$\begin{aligned}
\frac{\text{d}}{\text{d}t}\int_{a}^{b}u \text{ d}x&= F(u_{0}(a))-F(u_{0}(b))\\
&= F(1)-F(0)
\end{aligned}$$
Assume the shock moves at a speed $V$. In general:
$$\begin{aligned}
(u^{-}-u^{+})V \Delta t&= F(u^{-})\Delta t-F(u^{+})\Delta t\\
V&= \frac{F(u^{-})-F(u^{+})}{u^{-}-u^{+}}
\end{aligned}$$
We have $f(u)=u^{3}$, we can choose $F(u)=\frac{1}{4}u^{4}$. 
We have $u^{-}=1,\quad u^{+}=0$. Then 
$$V=\frac{\frac{1}{4}1^{4}-\frac{1}{4}0^4}{1-0}=\frac{1}{4}.$$
The position of shock is $s(t)=\frac{t}{4}$. Solution can be written as
$$u(x,t)=\begin{cases}
1 & \quad\text{for }x<\frac{t}{4} \\
0 & \quad\text{for }x>\frac{t}{4}
\end{cases}$$

---
$$u_{t}+u^{2}u_{x}=0,\qquad u(x,0)=\begin{cases}
0 & x<0 \\
1 & 0<x<1 \\
0 & x>1
\end{cases}$$
* For $x_{0}<0:\quad x=x_{0}$.
* For $0<x_{0}<1:\quad x=t+x_{0}$
* For $x_{0}>1:\quad x=x_{0}$.
Shock at $x=1$ for $t=0$.
$$\begin{aligned}
F(u)&= \frac{1}{3}u^{3}\\
u^{-1}&= 1, \quad u^{+}=0\\
V&= \frac{\frac{1}{3}1^{3}-0}{1-0}\\
&= \frac{1}{3}
\end{aligned}$$
Position of shock is
$$s(t)=1+\frac{t}{3}$$
since it starts at $x=1$.

After a time $t_{m}$, the rarefaction wave collides with the shock. $t_{m}$ satisfies
$$\begin{aligned}
t_{m}=1+\frac{t_{m}}{3}\\
t_{m}=\frac{3}{2}
\end{aligned}$$
For $0<x<t$, we have rarefaction
$$u(x,t)=f^{-1}\left(\frac{x}{t} \right)$$
since $u^{2}$ is monotonous between $0$ and $1$. Rarefaction is
$$u(x,t)=\sqrt{\frac{x}{t}}$$

For $t<\frac{3}{2}$:
$$u(x,t)=\begin{cases}
0 & \quad\text{for }x<0 \\
\sqrt{\frac{x}{t}} & \quad\text{for }0<x<t \\
1 & \quad\text{for }t<x<1+\frac{t}{3} \\
0 & \quad\text{for }x>1+\frac{t}{3}
\end{cases}$$

For $t>\frac{3}{2}$, the left value of the shock is the rarefaction part evaluated at the position of the shock:
$$u^{-}=\sqrt{\frac{s(t)}{t}}.$$
$$\begin{aligned}
V&= s'\\
&= \frac{\frac{1}{3} \left(\sqrt{\frac{s(t)}{t}} \right)^{3}-0}{\sqrt{\frac{s(t)}{t}}}\\
s'&= \frac{1}{3}\frac{s(t)}{t}\\
\frac{\text{d}s}{s}&= \frac{1}{3}\frac{\text{ d}t}{t}\\
\ln s&= \ln t^{\frac{1}{3}}+C\\
s(t)&= \tilde C t^{\frac{1}{3}}
\end{aligned}$$
The speed at the shock is
$$\begin{aligned}
s\left(\frac{3}{2}\right)&= \frac{3}{2}\\
s(t)&= \left(\frac{3}{2}\right)^{2/3}t^{1/3}
\end{aligned}$$
For $t>\frac{3}{2}$:
$$u(x,t)=\begin{cases}
0 & \quad\text{for }x<0 \\
\left(\frac{x}{t}\right)^{1/2} & \quad\text{for }0<x<\left(\frac{3}{2}\right)^{2/3}t^{1/3} \\
0 & \quad\text{for }\left(\frac{3}{2}\right)^{2/3}t^{1/3}<x
\end{cases}$$
