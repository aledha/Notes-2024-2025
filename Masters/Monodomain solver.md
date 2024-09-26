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
\int_{H}\psi \cdot (v^{n+1}-v^{n})\text{ d}x &=  \Delta t \cdot \theta \int_{H}\psi\cdot\nabla ^{2}v^{n+1} \text{ d}x+ \Delta t \cdot (1-\theta )\int_{H}\psi \cdot \nabla ^{2}v^{n} \text{ d}x\\
\int_{H}\psi \cdot (v^{n+1}-v^{n})\text{ d}x &= \Delta t \cdot \theta \int_{\partial H}\psi n \cdot \nabla v^{n+1}\text{ d}x +\Delta t \cdot \theta \int_{\partial H}\psi n \cdot \nabla v^{n}\text{ d}x\\
&\quad -\Delta t \cdot \theta \int_{H}\nabla \psi \cdot \nabla v^{n+1} \text{ d}x- \Delta t \cdot (1-\theta)\int_{H}\nabla \psi \cdot \nabla v^{n}
\end{aligned}
$$
for all $\psi \in V$.

The boundary integrals vanish because of the boundary condition $n \cdot \nabla v=0$. The formulation simplifies to finding $v^{n+1}\in V$ such that
$$
\int_{H}\psi v^{n+1} \text{ d}x +\Delta t \cdot \theta \int_{H}\nabla \psi \cdot \nabla v^{n+1}\text{ d}x=\int_{H}\psi v^{n}\text{ d}x -\Delta t \cdot (1-\theta )\int_{H}\nabla \psi \cdot \nabla v^{n} \text{ d}x
$$
for all $\psi \in V$.

Lets partition the domain $H$ into a set of non-overlapping triangles $\{\tau_{k}\}_{k=1}^{m}$, and denote this triangulation as $\Omega _{h}=\mathop{\cup}_{k=1}^{m}\tau _{k}$. Denote the vertices of the triangles as $\mathbf x_{j}$ for $j=1,\dots,n$.

Now we need to approximate the infinite dimensional function space $V$ with some finite dimensional function space $V_{h}$. Let $\phi _{1}, \phi _{2},\dots,\phi _{n}$ be a set of basis piecewise linear functions for $V_{h}$ such that
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
In order to build the matrix $A$ and the vector $f$, we will utilize the stamping method.