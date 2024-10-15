Let $u(x,t)$ be the number of cars per length.
We model the velocity as
$$v(u)=v_{m} \left(1- \left(\frac{u}{u_{m}} \right)^{p} \right),$$
where $v_{m}$ is the max velocity, $u_{m}$ is the maximum car density, and $p>0$ some parameter.
![[IMG_0351.jpg|400]]

Let the flux be denoted by $\vec{q}$, and then the flux is the number of cars times the speed of the cars
$$\vec{q}=uv(u)$$
Then, by conservation,
$$\begin{aligned}
u_{t}+(uv(u))_{x}&= 0\\
	u_{t}+\left(uv_{m} \left(1-\left(\frac{u}{u_{m}} \right)^{p} \right) \right)_{x}&= 0.
\end{aligned}$$
Scaling:
* $u\to u_{m}u$
* $x\to Lx$
* $t\to \frac{L}{v_{m}}t$

Then,
$$\begin{aligned}
\frac{u_{m}v_{m}}{L}u_{t}+\frac{v_{m}}{L}\left(u_{m}u(1-u^{p}) \right)_{x}&= 0\\
u_{t}+(u(1-u^{p}))_{x}&= 0
\end{aligned}$$
### Case 1:  "Waiting for green light"
$$u(x,0)=\begin{cases}
1 & \quad\text{for }x<0 ,\\
0 & \quad\text{for }x>0.
\end{cases}$$
Let's also assume that $p=1$. So the equation becomes
$$u_{t}+\underbrace{(1-2u)}_{f(u)}u_{x}= 0.$$
For $x_{0}<0$:
$u(x_{0},0)=1$ and
$$x=f(1)t+x_{0}=-t+x_{0}$$
For $x_{0}>0$:
$u(x_{0},0)=0$ and 
$$x=f(0)t+x_{0}=t+x_{0}.$$
We then have two groups of characteristics. 
The rarefaction between is
$$f(u)=1-2u \quad\Leftrightarrow\quad f^{-1}(y)=\frac{1-y}{2}$$
Now we can write down the solution:
$$u(x,t)=\begin{cases}
1 & \quad\text{for }x<-t \\
\frac{1-\frac{x}{t}}{2} & \quad\text{for }-t<x<t \\
0 & \quad\text{for }x>t
\end{cases}$$
#### Position of car that starts at $x=-1$
Let's try to find the position of the car $x=y(t)$ that starts at $x=-1$ at $t=0$.

The car can't start before time 1: $y(1)=-1$. It follows the rarefaction wave
$$\begin{aligned}
V&= (1-u)\\
&= 1-\frac{1-\frac{y(t)}{t}}{t}\\
&= y'(t)
\end{aligned}$$
This is a differential equation in $y$:
$$\begin{aligned}
y'&= \frac{1}{2}\left(1+\frac{y}{t}\right)\\
y'-\frac{1}{2t}y&= \frac{1}{2}.
\end{aligned}$$
Integrating factior method:
$$\begin{aligned}
\exp\left(\int -\frac{1}{2t}\text{ d}t\right)&= \exp\left(-\frac{1}{2}\ln t\right)\\
&= \frac{1}{t^{1/2}}
\end{aligned}$$
Now,
$$\begin{aligned}
y'-\frac{1}{2t}y&= \frac{1}{2}\\
\left(y \frac{1}{t^{1/2}}\right)'&= \frac{1}{2t^{1/2}}\\
t^{-1/2}y&= t^{1/2}+C\\
y&= t+Ct^{1/2}\\
y(1)&= 1+C=-1\\
y(t)&= t-2t^{1/2}
\end{aligned}$$

### Case 2: "Traffic up ahead"
Now the initial condition is
$$u(x,0)=\begin{cases}
u_{1} & \quad\text{for }x<0 \\
\frac{u_{2}-u_{1}}{L}x+u_{1} & \quad\text{for }0<x<L  \\
u_{2} & \quad\text{for }x>L
\end{cases}$$
The original differential equation was
$$u_{t}+\left(v_{m}u\left(1-\frac{u}{u_{m}}\right) \right)_{x}=0$$
Scaling:
* $x\to Lx$
* $t\to \frac{L}{v_{m}}t$
* $u\to u_{m}u$

So
$$u_{t}+(u(1-u))_{x}=0$$
and the initial condition is 
$$\begin{aligned}
u_{m}u(x)&= \begin{cases}
u_{1} & \quad\text{for }x>0 \\
\frac{u_{2}-u_{1}}{L}x+u_{1} & \quad\text{for }0<x<L \\
u_{2} & \quad\text{for }x>L
\end{cases}\\
\\
u(x)&= \begin{cases}
\frac{u_{1}}{u_{m}} & \quad\text{for }x>0 \\
\left(\frac{u_{2}}{u_{m}}-\frac{u_{1}}{u_{m}} \right)x+\frac{u_{1}}{u_{m}} & \quad\text{for }0<x<L \\
\frac{u_{2}}{u_{m}} & \quad\text{for }x>L
\end{cases}\\
\\
&= \begin{cases}
\alpha _{1} & \quad\text{for }x<0\\
(\alpha _{2}-\alpha _{1})x+\alpha _{1} & \quad\text{for }0<x<1\\
\alpha _{2} & \quad\text{for }x>1
\end{cases}
\end{aligned}$$
where $\alpha _{i}=\frac{u_{i}}{u_{m}}$.
Recall that $f(u)=1-2u$. 
If we assume that $\alpha _{1}>\frac{1}{2}$, then $f(\alpha _{1})<0$. 
Also, $\alpha _{2}>\alpha _{1}$ so $f(\alpha _{2})<f(\alpha _{1})$, meaning that the characteristics meet
![[IMG_0353.jpg|400]]

Let's figure out the time when the chars cross:
$$\begin{aligned}
(1-2\alpha _{1})t&= (1-2\alpha _{2})t+1\\
2(\alpha _{2}-\alpha _{1}t)&= 1\\
t_{s}&= \frac{1}{2(\alpha _{2}-\alpha _{1})}
\end{aligned}$$
and the $x$-value when they cross:
$$\begin{aligned}
x_{s}&= (1-2\alpha _{1})t_{s}\\
&= \frac{1-2\alpha _{1}}{2(\alpha _{2}-\alpha _{1})}
\end{aligned}$$