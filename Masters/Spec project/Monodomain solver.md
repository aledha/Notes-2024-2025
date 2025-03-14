We want to solve the monodomain model \ref{}.

We start off with 2 dimensions. Let $H$ be the unit square $[0,1]\times[0,1]$,  $C_{m}=1$, $\chi=1$,  and $M_{i}=\mathbf{I}$. Then the model simplifies to
$$
\begin{aligned}
\frac{\partial s}{\partial t}&= f(s,v,t),&x\in H,\\
\frac{\partial v}{\partial t}&= \frac{\lambda }{1+\lambda }\nabla^{2} v+I_\text{stim}-I_{\text{ion}}(v,s), &x\in H,\\
n \cdot (\nabla v)&= 0, &x\in \partial H.
\end{aligned}
$$
## Analytical solution
To test our solver, we will generate expressions for $\nabla^2v$, $f$, $I_\text{stim}$, and $I_\text{ion}$ with the analytical solution
$$
\begin{equation}
v(x,y,t)=\cos (2\pi x)\cos (2\pi y)\sin t.
\end{equation}
$$
Then,
$$
\begin{equation*}
\nabla v=-2\pi \sin t \begin{bmatrix}\sin (2\pi x)\cos (2\pi y) \\ \cos (2\pi x)\sin (2\pi y)\end{bmatrix},
\end{equation*}
$$
where we see that the boundary condition $n \cdot \nabla v=0$ is satisfied. Further,
$$
\begin{equation}
\nabla ^{2}v = -8\pi ^{2}\cos (2\pi x)\cos (2\pi y)\sin t,%\label{eq:laplacev}
\end{equation}
$$
and
$$
\begin{equation}
\frac{\partial v}{\partial t}=\cos (2\pi x)\cos (2\pi y)\cos t. %\label{eq:dvdt}
\end{equation}
$$

We let
$$
\begin{align}
\frac{\partial s}{\partial t}&=f(s,v,t)=v\\
s&= -\cos (2\pi x)\cos (2\pi y)\cos t. %\label{eq:anal_s}
\end{align}
$$
Now,
$$
\begin{align*}
\frac{\partial v}{\partial t}&= \frac{\lambda }{1+\lambda }\nabla^{2} v+I_{\text{stim}}-I_{\text{ion}}(v,s)\\
I_{\text{ion}}-I_\text{stim}&= \frac{\lambda }{1+\lambda }\left(-8\pi ^{2}\cos (2\pi x)\cos (2\pi y)\sin t \right)-\cos (2\pi x)\cos (2\pi y)\cos t\\
&= -\left(\frac{8\pi ^{2}\lambda }{1+\lambda }\sin t + \cos t\right) \cos (2\pi x)\cos (2\pi y).
\end{align*}
$$

We can let 
$$
\begin{align*}
I_\text{ion}&= s\\
&= -\cos (2\pi x)\cos (2\pi y)\cos t.
\end{align*}
$$

such that
$$
\begin{align}
I_\text{stim}&= I_{\text{ion}}+\left(\frac{8\pi ^{2}\lambda }{1+\lambda }\sin t + \cos t\right) \cos (2\pi x)\cos (2\pi y)\nonumber\\
I_\text{stim}&= \frac{8\pi ^{2}\lambda }{1+\lambda }\cos (2\pi x)\cos (2\pi y)\sin t. %\label{eq:analistim}
\end{align}
$$

With the initial conditions
$$
\begin{align}
v(0)&= 0,\\
s(0)&= -\cos (2\pi x)\cos (2\pi y),
\end{align}
$$
we can set up the operator splitting scheme described in \ref{sec:operatorsplitting}.

The ODE system \ref{eq:odesplitv} and \ref{eq:odesplits} becomes
$$
\begin{align}
\frac{ \partial v }{ \partial t }  & =-\frac{1}{C_{m}}I_\text{ion}=-s, \\ %\label{eq:analodesplitv}
\frac{ \partial s }{ \partial t }  & =f(s,v,t)=v. %\label{eq:analodesplits}
\end{align}
$$



## Operator splitting
We will solve this by use of operator splitting. 

1. First, given $v(t_{n})=v^{n}$ and $s(t^{n})=s^{n}$, solve
	$$
\begin{aligned}
\frac{\partial v}{\partial t}&= -I_{\text{ion}}(v,s),\\
\frac{\partial s}{\partial t}&= f(v,s),
\end{aligned}
$$
	for $t_{n}<t \le t_{n}+\theta \Delta t$. Denote the solutions as $v_{\theta }^{n}$ and $s_{\theta }^{n}$.

2. Then, solve
	$$
\frac{\partial v}{\partial t}=\frac{\lambda }{1+\lambda }\nabla ^{2}v+I_\text{stim},
$$
	for $t_{n}<t \le t_{n}+\Delta t$, with the initial condition $v(t_{n})=v_{\theta }^{n}$. The solution is denoted as $v_{\theta }^{n+1}$.
3. Finally, solve the system
	$$
\begin{aligned}
\frac{\partial v}{\partial t}&= -I_{\text{ion}}(v,s),\\
\frac{\partial s}{\partial t}&= f(v,s),
\end{aligned}
$$
	for $t_{n}+\theta \Delta t <t \le t_{n}+\Delta t$ with the initial conditions $v(t_{n}+\theta \Delta t)=v_{\theta }^{n+1}$ and $s(t_{n}+\theta \Delta t)=s^{n}_{\theta }$.

### Solver for step 1 and step 3
We will use another $\theta$-rule to solve the system of ODEs:
$$\begin{aligned}
\frac{y^{n+1}-y^{n}}{\Delta t}&= (1-\theta )f(t_{n},y^{n})+\theta f(t_{n+1},y^{n+1})\\
y^{n+1}-\Delta t \theta f(t_{n+1},y^{n+1})&= y^{n}+\Delta t(1-\theta )f(t_{n},y^{n}).
\end{aligned}$$
The rule applied to the system
$$\begin{aligned}
\frac{\partial v}{\partial t}&= -s,\\
\frac{\partial s}{\partial t}&= v,
\end{aligned}$$
yields
$$
\begin{aligned}
v^{n+1}+\Delta t \theta s^{n+1}&=  v^{n}-\Delta t(1-\theta )s^{n},\\
s^{n+1}-\Delta t \theta v^{n+1}&= s^{n}+\Delta t(1-\theta )v^{n},
\end{aligned}
$$
$$\begin{aligned}
\begin{bmatrix}1 & \Delta t \theta  \\ -\Delta t \theta  & 1\end{bmatrix}\begin{bmatrix}v^{n+1}\\
s^{n+1}\end{bmatrix}&=\begin{bmatrix}v^n-\Delta t(1-\theta )s^n\\
s^n+\Delta t(1-\theta )v^n\end{bmatrix} \\
\mathbf A \mathbf x&= \mathbf b,
\end{aligned}$$

Setting $\theta =0$ gives us the forward Euler method:
$$\begin{aligned}
v^{n+1}&= v^{n}-\Delta ts^{n}\\
s^{n+1}&= s^{n}+\Delta tv^{n}
\end{aligned}$$

### Solver for step 2
In order to solve the PDE in step 2, we will utilize a $\theta$-rule to discretize in time:
$$
\begin{aligned}
\frac{v^{n+1}-v^{n}}{\Delta t}&= \frac{\lambda }{1+\lambda }\left(\theta \nabla ^{2}v^{n+1}+(1-\theta )\nabla ^{2}v^{n} \right)+I_\text{stim}.
\end{aligned}
$$
Notice that this $\theta$ differs from the parameter $\theta$ for the operator splitting. However, a parameter choice of $\theta =\frac{1}{2}$ gives a second order accuracy in time for both the operator splitting and the $\theta$-rule. Now, we can reformulate the time-discrete equation into a Galerkin formulation: 
For some suitable function space $V$, find $v^{n+1}\in V$ such that for every $\phi \in V$,
$$
\begin{aligned}
\int _{H}(v^{n+1}-v^{n})\phi  \text{ d}\mathbf x&=\Delta t\int_{H} \frac{\lambda }{1+\lambda }\left(\theta \nabla ^{2}v^{n+1}+(1-\theta )\nabla ^{2}v^{n}\right) +I_\text{stim}\phi \text{ d}\mathbf x\\
\int_{H}v^{n+1}\phi \text{ d}\mathbf x-\gamma \theta \int_{H}\phi \cdot \nabla ^{2}v^{n+1}\text{ d}\mathbf x&= \int_{H}v^{n}\phi +\Delta t \cdot I_\text{stim}\phi  \text{ d}\mathbf x+\gamma (1-\theta )\int_{H}\phi \cdot \nabla ^{2}v^{n}\text{ d}\mathbf x\\
\int_{H}v^{n+1}\phi  \text{ d}\mathbf x -\gamma \theta \int_{\partial H}\phi n \cdot \nabla v^{n+1} \text{ d}\mathbf x+\gamma \theta \int_{H}\nabla \phi \cdot \nabla v^{n+1}\text{ d}\mathbf x &= \int_{H}v^{n}\phi +\Delta t \cdot I_\text{stim}\phi  \text{ d}\mathbf x+\gamma (1-\theta )\int_{\partial H}\phi n \cdot \nabla v^{n}\text{ d}\mathbf x- \gamma (1-\theta)\int_{H}\nabla \phi \cdot \nabla v^{n}\text{ d}\mathbf x\\
\int_{H}\phi v^{n+1}+\gamma \theta \nabla \phi \cdot \nabla v^{n+1}\text{ d}\mathbf x&= \int_{H}\phi (v^{n}+\Delta t \cdot I_\text{stim})-\gamma (1-\theta )\nabla \phi \cdot \nabla v^{n}\text{ d}\mathbf x,
\end{aligned}
$$
where $\gamma = \frac{\Delta t\lambda }{1+\lambda }$. 
The bilinear and linear form are
$$\begin{aligned}
a(v^{n+1},\phi )&= \int_{H}\phi v^{n+1}+\gamma \theta \nabla \phi \cdot \nabla v^{n+1}\text{ d}\mathbf x\\
L(\phi )&= \int_{H}\phi (v^{n}+\Delta t \cdot I_\text{stim})-\gamma (1-\theta )\nabla \phi \cdot \nabla v^{n}\text{ d}\mathbf x
\end{aligned}$$


