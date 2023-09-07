For $u: \mathbb{R}_{t}\times \mathbb{R}^{d}_{x}\to \mathbb{R}$ and $H: \mathbb{R}_{x}^{d}\times \mathbb{R}^{d}_{p}\to \mathbb{R}$,
$$\begin{cases}
\partial_{t}u+H(x,D_{x}u(x))  =0 & \text{in }(0,\infty)_{t}\times \mathbb{R}^{d} \\
u= g \quad\text{on }\{ t=0\},
\end{cases}$$
where $H$ is the Hamiltonian. 
Let us try the method of characteristics. $F$ can be written as
$$F=p_{t}+H(x,p),$$
note that $H$ is only in space not time, so the characteristic equations become
$$\begin{align*}
&\dot{t}=1 \qquad \qquad  \qquad \dot{p}_{t}=0\\
	& \underbrace{\dot{x}^{j}=\partial_{p_{j}}H(x,p)\qquad \dot{p}_{j}=-\partial_{x^{j}}H(x,p)}_\text{Hamilton's equations}
\end{align*}$$
We get local existence in time and uniqueness from the method of characteristics.
Usually in Hamilton's equations, one uses $q$ instead of $x$.

```ad-question
Are we guaranteed global existance in general?
```
**Answer: no**

Let's see an example where global existence breaks down. 
With $d=1$ and $H(x,p)=\frac{1}{2}p^{2}$, the HJE becomes
$$\begin{cases}
\partial_{t}u+ \frac{1}{2}(\partial_{x}u)^{2} =0 \\
u=g
\end{cases}$$
If we take the derivative w.r.t $x$ of both sides, and denote $v=\partial_{x}u$, we get
$$\begin{cases}
\partial_{t} v+v \partial_{x}v=0 \\
v=\partial_{x}g
\end{cases},$$
which is **Burger's** equation.
$F=p_{t}+zp_{x}$. Using the method of characteristics, we get that $t=s$ and
$$\dot{x}=z, \qquad \dot{z}=p_{x}z +p_{t}, \qquad \dot{p}=-p^{2}$$
The solution for $p(t)=\frac{p(0)}{1+tp(0)}$ becomes $\infty$ when $t=- \frac{1}{p(0)}$.

We can therefore not expect global solutions to Burgers equations. But,

```ad-question
Can we still formulate a notion of a good weak solution that is both **global** and **unique**?

```


**How the HJE comes from classical mechanics**
1. We can represent classical mechanics as an optimization problem (Lagrangian formulation $\to$ calculus of variations)
2. We can transfer the optimization problem to the Hamilton-Jacobi equation
3. HJE gives rise to Hamilton's mechanics

Let's look at Newton's 2nd law, where we for simplicity say that the mass $m=1$.
$$\ddot x=-\nabla V(x),$$
where $V$ is the potential.
To represent this as an optimization problem, look at the **Lagrangian viewpoint**
First we denote the set of all doubly continuous possible paths through $\mathbb{R}^{d}$ as
$$\mathcal{A}=\{\chi: \left[0,T \right] \to \mathbb{R}^{d}, \chi \in C^{2}\}.$$
We also define
$$\mathcal{S}(\chi )=\int_{0}^{t}L(\chi ,\dot \chi (s))\text{ d}s,$$
where 
$$L(x,v)=\underbrace{K}_{\text{Kinetic energy}}-\underbrace{P}_\text{Potential energy}= \frac{1}{2}\lvert v \rvert^{2}-V(x)$$
The **action principle** allows us to transfer the ODE to an optimization problem. The principle says that the trajectory of the system follows the trajectory of the ***minimal*** $\mathcal{S}$, i.e. where $\nabla \mathcal{S}(\chi )=0$. (Think of a ball rolling down a hill. It would prefer to roll straight down, without taking any detours which decreases its mechanical energy.)

So far:
$\ddot x_{*}=-\nabla V(x_{*}) \quad\Leftrightarrow\quad x_{*}(s)$ minimizes $S(x_{*})$.

## Sideline: Calculus of variations
Using *calculus of variations* (def: a field of mathematical analysis that uses variations, which are small changes in functions and functionals, to find maxima and minima of functionals).
	We look at a compactly supported function $\phi$ which is zero on the boundary, i.e. $\phi (0)=0=\phi (t)$
$$\begin{align*}
\frac{\text{d}}{\text{d}h} \mathcal{S}(x(s)+h \phi (s)) \bigg|_{h=0}&= 0\quad\forall\quad \phi \in C_{c}^{2}((0,t)\to \mathbb{R}^{d})\\
\frac{\text{d}}{\text{d}h}\int_{0}^{t}\left(\frac{1}{2}\lvert \dot x+h \dot \phi  \rvert^{2}-V(x+h \phi ) \right) \text{ d}s\bigg|_{h=0}&= 0\\
\int_{0}^{t}(\dot x+h \dot \phi ) \dot \phi \bigg|_{h=0}-\phi ^{j} \cdot \nabla V(x+h \phi )\bigg|_{h=0} \text{ d}s&=  0\\
\int_{0}^{t}\dot x \dot \phi -\phi ^{j}\nabla V(x) \text{ d}s&= 0
\end{align*}$$
#ask why $\phi ^{j}$? if $j$ is supposed to be there, why did it disappear?

Taking advantage of $\phi$ being zero on the boundary, we can use integration by parts on the first term:
$\int_{0}^{t} \dot x \dot \phi \text{ d}s= \phi \dot x \bigg|_{0}^{t}-\int_{0}^{t}\ddot x \phi \text{ d}s=\int_{0}^{t}-\ddot x \phi \text{ d}s$. The equation becomes
$$\begin{align*}
\int_{0}^{t}-\ddot x \phi -\phi \nabla V(x) \text{ d}s&= 0\\
\int _{0}^{t}\phi \cdot (-\ddot x-\nabla V(x))\text{ d}s &= 0 \quad\forall\quad \phi \in C^{2}_{c}((0,t)\to \mathbb{R}^{d})
\end{align*}$$
A solution $x$ for the equation above is called a *weak solution*. We can see that if $x$ satisfies Newtons 2nd ($\ddot x=-\nabla V(x)$), the equation is trivially satisfied. Any "strong" solution is also a weak solution.


Hamiltons idea: keep track of $\mathcal{S}(x_{*})$


## Lagrangian mechanics (optimization) to the Hamilton-Jacobi equation
Now, we have a function $\chi _{*}(t)=x$, such that $\chi _{*}^{(t,x)}$ that is a minimiser of $\mathcal{S}$.
Then our solution is $u(t,x)=\mathcal{S}$  evaluated at $\chi _{*}$, i.e.,
$$\begin{align*}
u(t,x)&= \int_{0}^{t}L(\chi _{*}^{(t,x)}(s),\dot \chi _{*}^{(t,x)}(s))\text{ d}s\\
&= \inf_\limits{\chi \in \mathcal{A}(t,x)}\left\{\int_{0}^{t}L(\chi (s), \dot \chi (s)) \text{ d}s\right\}, 
\end{align*}$$
where $\mathcal{A}(t,x)=\{\chi \in C^{2}([0,t]\to \mathbb{R}^{d}), \chi (t)=x \},$  i.e. all differentiable curves in $\mathbb{R}^{d}$, that is $x$ at time $t$.

The idea for deriving the PDE (HJE) that $u$ solves is to use dynamical programming, since we have optimal substructure.
$$u(t,x)=\inf_\limits{\chi \in \mathcal{A}(t,x)}\left\{ \int_{t-h}^{t}L(\chi ,\dot \chi )\text{ d}s +u(t-h,\chi (t-h))\right\}$$
If we are given an minimal curve up to $t-h$, the remaining curve in $(t-h,t)$ must also be minimal.
Moving $u(t,x)$ to the other side and performing Taylor expansion:
$$\begin{align*}
0&= \inf_\limits{\chi \in \mathcal{A}(t,x)}\left\{ \int_{t-h}^{t}L(\chi ,\dot \chi )\text{ d}s +u(t-h,\chi (t-h))-u(t,x)\right\}
\end{align*}$$
We have $\int_{0}^{t}L(\chi ,\dot \chi ) \text{ d}s=h \cdot L(x, \dot \chi (t))+\mathcal{O}(h)$,
$u(t-h,\chi (t-h))=-h \partial_{t}u(t,x)-h \sum_{j}^{} \dot \chi ^{j}(t)\partial_{x^{j}}u(t,x)+\mathcal{O}(h)$ 

Then the expression reads
$$\begin{align*}
0&= \inf_\limits{\chi \in \mathcal{A}(t,x)} \left\{h \left[L(x,\dot \chi(t))- \partial_{t}u(t,x)-\sum\limits_{j}^{}\dot \chi^{j} (t)\partial_{x^{j}}u(t,x) \right]+\mathcal{O}(h) \right\}\\
&= h \left[L(x,v)- \partial_{t}u(t,x)-\sum_{j}^{}v^{j}\partial_{x^{j}}u(t,x) \right]+\mathcal{O}(h)\\
&= h \left[L(x,v)- \partial_{t}u(t,x)-v \cdot Du(t,x) \right]+\mathcal{O}(h)
\end{align*}$$
Where $v=\dot \chi (t)$ is the minimiser.
Taking $h\to 0$ gives us back the **Hamilton-Jacobi equation**!
$$\partial_{t}u(t,x)+H(x,Du)=0,$$
where $H(x,p)=-\inf\limits_{v \in \mathbb{R}^{d} } \{L(x,v)-v \cdot p \}$ 