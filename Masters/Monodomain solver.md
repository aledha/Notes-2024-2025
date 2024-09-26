We want to solve the monodomain model, which is given by
$$
\begin{aligned}
\frac{\partial s}{\partial t}&= f(s,v,t),&x\in H,\\
\frac{\lambda }{1+\lambda }\nabla \cdot (M_{i}\nabla v)&= \frac{\partial v}{\partial t}+I_{\text{ion}}(v,s), &x\in H,\\
n \cdot (M_{i}\nabla v)&= 0, &x\in \partial H.
\end{aligned}
$$
To start, we will implement a solver for just the diffusion term, and then we will add the reactionary term later. The model simplifies to 
$$
\begin{aligned}
\frac{\partial s}{\partial t}&= f(s,v,t),&x\in H,\\
\frac{\lambda }{1+\lambda }\nabla \cdot (M_{i}\nabla v)&= \frac{\partial v}{\partial t}, &x\in H,\\
n \cdot (M_{i}\nabla v)&= 0, &x\in \partial H.
\end{aligned}
$$
## Analytical Solution of the Simplified Monodomain Model
To start, we will implement a solver for just the diffusion term, and then we will add the reactionary term later. We will also assume $H$ being the unit square, $H=[0,1]\times[0,1]$. Our model problem is then
$$
\begin{aligned}
\nabla^2 v&= \frac{\partial v}{\partial t}, &x\in H,\\
n \cdot \nabla v&= 0, &x\in \partial H.
\end{aligned}
$$
Denoting $v(t_{n})=v^{n}$ for the potential at the time $t_{n}=n \cdot \Delta t$, we will use the $\theta$-rule for the time discretization:
$$
\begin{aligned}
\frac{v^{n+1}-v^{n}}{\Delta t}&=  \theta (\nabla ^{2}v^{n+1}) +(1-\theta )(\nabla ^{2}v^{n})\\
v^{n+1}-v^{n}&=  \Delta t \cdot \theta (\nabla ^{2}v^{n+1}) +\Delta t \cdot (1-\theta )(\nabla ^{2}v^{n}).
\end{aligned}
$$

To obtain a Galerkin formulation of the problem, multiply by a test function $\psi \in V$ for some function space $V$ and integrate over the domain. Our problem is to find $v^{n+1}\in V$ such that
$$
\begin{aligned}
\int_{H}\psi \cdot (v^{n+1}-v^{n})\text{ d}\mathbf x &=  \Delta t \cdot \theta \int_{H}\psi\cdot\nabla ^{2}v^{n+1} \text{ d}\mathbf x+ \Delta t \cdot (1-\theta )\int_{H}\psi \cdot \nabla ^{2}v^{n} \text{ d}\mathbf x\\
\int_{H}\psi \cdot (v^{n+1}-v^{n})\text{ d}\mathbf x &= \Delta t \cdot \theta \int_{\partial H}\psi n \cdot \nabla v^{n+1}\text{ d}\mathbf x +\Delta t \cdot \theta \int_{\partial H}\psi n \cdot \nabla v^{n}\text{ d}\mathbf x\\
&\quad -\Delta t \cdot \theta \int_{H}\nabla \psi \cdot \nabla v^{n+1} \text{ d}\mathbf x- \Delta t \cdot (1-\theta)\int_{H}\nabla \psi \cdot \nabla v^{n} \text{ d}\mathbf x
\end{aligned}
$$
for all $\psi \in V$.

The boundary integrals vanish because of the boundary condition $n \cdot \nabla v=0$. The formulation simplifies to finding $v^{n+1}\in V$ such that
$$
\int_{H}\psi v^{n+1} \text{ d}\mathbf x +\Delta t \cdot \theta \int_{H}\nabla \psi \cdot \nabla v^{n+1}\text{ d}\mathbf x=\int_{H}\psi v^{n}\text{ d}\mathbf x -\Delta t \cdot (1-\theta )\int_{H}\nabla \psi \cdot \nabla v^{n} \text{ d}\mathbf x
$$
for all $\psi \in V$.

Lets partition the domain $H$ into a set of non-overlapping triangles $\{\tau_{k}\}_{k=1}^{m}$, and denote this triangulation as $\Omega _{h}=\mathop{\cup}_{k=1}^{m}\tau _{k}$. Denote the vertices of the triangles as $\mathbf x_{j}$ for $j=1,\dots,n$.

Now we need to approximate the infinite dimensional function space $V$ with some finite dimensional function space $V_{h}$. Let $\phi _{1}, \phi _{2},\dots,\phi _{n}$ be a set of piecewise linear functions that spans $V_{h}$ such that
$$
\phi _{i}(\mathbf x_{j})=\begin{cases}
1, & \quad\text{for }i=j, \\
0, & \quad\text{for }i\neq j.
\end{cases}
$$
Then, any $v\in V_{h}$ can be written as
$$
v= \sum_{j=1}^{n}v_{j}\phi _{j},
$$
where $v_{j}$ are scalars. Let $v^{n+1}=\sum_{j=1}^{n}v_{j}\phi _{j}$. The formulation is now:
Find $v_{j}$, $j=1,\dots,n$ such that
$$
\begin{aligned}
\int_{H}\psi \left(\sum_{j=1}^{n}v_{j}\phi _{j} \right) \text{ d}x +\Delta t \cdot \theta \int_{H}\nabla \psi \cdot \nabla \left(\sum_{j=1}^{n}v_{j}\phi _{j} \right)\text{ d}x&= \int_{H}\psi v^{n}\text{ d}x -\Delta t \cdot (1-\theta )\int_{H}\nabla \psi \cdot \nabla v^{n} \text{ d}x\\
\sum_{j=1}^{n} v_{j}\left(\int_{H}\psi \phi _{j} \text{ d}x +\Delta t \cdot \theta \int_{H}\nabla \psi \cdot \nabla \phi _{j} \text{ d}x \right)&= \int_{H}\psi v^{n}\text{ d}x -\Delta t \cdot (1-\theta )\int_{H}\nabla \psi \cdot \nabla v^{n} \text{ d}x
\end{aligned}
$$
for every $\psi \in V_{h}$. The condition that the equation is fulfilled for every $\psi \in V_{h}$ is equivalent to the equation being fulfilled for every basis vector $\phi _{i}, i=1,\dots,n$. Thus we can rewrite further to:
Find $v_{j},j=1,\dots,n$ such that
$$
\sum_{j=1}^{n} v_{j}\left(\int_{H}\phi _{i} \phi _{j} \text{ d}x +\Delta t \cdot \theta \int_{H}\nabla \phi _{i} \cdot \nabla \phi _{j} \text{ d}x \right)= \int_{H}\phi _{i} v^{n}\text{ d}x -\Delta t \cdot (1-\theta )\int_{H}\nabla \phi _{i} \cdot \nabla v^{n} \text{ d}x
$$
for $i=1,\dots,n$. 

This is a linear system of $n$ equations with $n$ unknowns, and can therefore be written in the matrix notation
$$
Av=f,
$$
where
$$
\begin{aligned}
A_{ij}&= \int_{H}\phi _{i} \phi _{j} \text{ d}x +\Delta t \cdot \theta \int_{H}\nabla \phi _{i} \cdot \nabla \phi _{j} \text{ d}x,\\
f_{i}&= \int_{H}\phi _{i} v^{n}\text{ d}x -\Delta t \cdot (1-\theta )\int_{H}\nabla \phi _{i} \cdot \nabla v^{n} \text{ d}x.
\end{aligned}
$$

For assembly, we will apply a stamping method. Consider an element $\tau ^{k}$ with local nodes $\mathbf x_{1}^{k},\mathbf x_{2}^{k},\mathbf x_{3}^{k}$ and local basis functions $\mathcal{H}_{1}^{k},\mathcal{H}_{2}^{k},\mathcal{H}_{3}^{k}$, where $\mathcal{H}^{k}_{\alpha }=c_{\alpha }^{k}+c_{x,\alpha }^{k}x+ c_{y,\alpha }^{k}y$. Then the elemental matrix is
$$\begin{align*}
A^{k}_{\alpha \beta} &= \int_{\tau ^{k}} \mathcal{H}_{\alpha }^{k}(\mathbf x) \cdot \mathcal{H}^{k}_{\beta }(\mathbf x)\text{ d}\mathbf x+\Delta t \cdot \theta \int_{\tau ^{k}}\partial _{x}\mathcal{H^{k}_{\alpha }}\cdot \partial _{x}\mathcal{H^{k}_{\beta  }}+\partial _{y}\mathcal{H^{k}_{\alpha }}\cdot \partial _{y}\mathcal{H^{k}_{\beta  }}\text{ d}\mathbf x\\
&= \int_{\tau ^{k}} \mathcal{H}_{\alpha }^{k}(\mathbf x) \cdot \mathcal{H}^{k}_{\beta }(\mathbf x)\text{ d}\mathbf x+\Delta t \cdot \theta (c_{x,\alpha }^{k}c_{x,\beta }^{k}+c_{y,\alpha }^{k}c_{y,\beta }^{k})T_{k},
\end{align*}$$
where $T_{k}$ denotes the area of one element. For the second term, we can use the Gaussian quadrature
$$\int_{\tau ^{k}}f(\mathbf x)\text{ d}\mathbf x\approx T_{k}\sum_{i=1}^{3}w_{i}^{g}f(\mathbf x_{i}^{g}),$$
where $w_{i}^{g}=\frac{1}{3}$ and $\mathbf x_{i}^{g}=\sum_{j=1}^{3}(\frac{\mathbf x_{j}}{6}+\delta _{ij}\frac{\mathbf x_{i}}{2})$ for $i=1,2,3$. Then the first term of the elemental matrix reads
$$\int_{\tau ^{k}}\mathcal{H}_{\alpha }^{k}(\mathbf x)\cdot \mathcal{H}_{\beta  }^{k}(\mathbf x)\text{ d}\mathbf x=\frac{1}{3}T_{k}\sum_{i=1}^{3}\mathcal{H}_{\alpha }^{k}(\mathbf x_{i}^{g})\cdot \mathcal{H}_{\beta }^{k}(\mathbf x_{i}^{g}).$$
Since the quadrature is second order accurate and the integrand is the product two first order polynomials, this approximation is accurate. The elemental matrix is now
$$A_{\alpha \beta }^{k}=\frac{1}{3}T_{k}\sum_{i=1}^{3}(\mathcal{H}_{\alpha }^{k}(\mathbf x_{i}^{g})\cdot \mathcal{H}_{\beta }^{k}(\mathbf x_{i}^{g}))+\Delta t \cdot \theta (c_{x,\alpha }^{k}c_{x,\beta }^{k}+c_{y,\alpha }^{k}c_{y,\beta }^{k})T_{k}.$$
The elemental load vector is
$$\begin{aligned}
f^{k}_{\alpha}&= \int_{\tau ^{k}}\mathcal{H}_{\alpha }^{k}\cdot v^{n}\text{ d}\mathbf x+\int_{\tau ^{k}}\partial _{x}\mathcal{H}_{\alpha }^{k}\cdot \partial _{x}v^{n}+\partial _{y}\mathcal{H}_{\alpha }^{k}\cdot \partial _{y}v^{n}\text{ d}\mathbf x\\
&= \int_{\tau ^{k}}\mathcal{H}_{\alpha }^{k}\cdot v^{n}\text{ d}\mathbf x+\int_{\tau ^{k}}c_{x,\alpha }^{k} \cdot \partial _{x}v^{n}+c_{y,\alpha }^{k}\cdot \partial _{y}v^{n}\text{ d}\mathbf x.
\end{aligned}$$
In order to calculate $v^{n}$, we let 