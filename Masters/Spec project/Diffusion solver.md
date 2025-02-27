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
$$\begin{aligned}
A_{\alpha \beta }^{k}&= T_{k}\left(\frac{1}{3}\sum_{i=1}^{3}(\mathcal{H}_{\alpha }^{k}(\mathbf x_{i}^{g})\cdot \mathcal{H}_{\beta }^{k}(\mathbf x_{i}^{g}))+\Delta t \cdot \theta (c_{x,\alpha }^{k}c_{x,\beta }^{k}+c_{y,\alpha }^{k}c_{y,\beta }^{k})\right)\\

\end{aligned}\tag{EM}$$
The elemental load vector is
$$\begin{aligned}
f^{k}_{\alpha}&= \int_{\tau ^{k}}\mathcal{H}_{\alpha }^{k}\cdot v^{n}\text{ d}\mathbf x-\Delta t \cdot (1-\theta )\int_{\tau ^{k}}\partial _{x}\mathcal{H}_{\alpha }^{k}\cdot \partial _{x}v^{n}+\partial _{y}\mathcal{H}_{\alpha }^{k}\cdot \partial _{y}v^{n}\text{ d}\mathbf x\\
&= \int_{\tau ^{k}}\mathcal{H}_{\alpha }^{k}\cdot v^{n}\text{ d}\mathbf x-\Delta t \cdot (1-\theta )\int_{\tau ^{k}}c_{x,\alpha }^{k} \cdot \partial _{x}v^{n}+c_{y,\alpha }^{k}\cdot \partial _{y}v^{n}\text{ d}\mathbf x.
\end{aligned}$$
Let $v^{n}=\sum_{i=1}^{n}v^{n}_{i}\phi _{i}$. On an element $\tau ^{k}$, we can interpolate $v^{n}$ as
$$
v^{n}(\mathbf x)|_{\tau^{k}}=\sum_{\beta =1}^{3}v^{n}_{l(\beta ,k)}\mathcal{H}_{\beta }^{k}(\mathbf x),
$$
where $l(\beta,k)$ is the local-to-global mapping for node $\beta$ in the element $\tau ^{k}$.

Using the interpolation for $v^{n}$ and the same Gaussian quadrature, we can compute the first term of the elemental load vector as
$$
\begin{aligned}
\int_{\tau ^{k}}\mathcal{H}_{\alpha }^{k}(\mathbf x)\cdot v^{n}(\mathbf x)\text{ d}\mathbf x&= \int_{\tau ^{k}}\mathcal{H}_{\alpha }^{k}(\mathbf x) \cdot \left(\sum_{\beta =1}^{3}v_{l(\beta ,k)}^{n} \mathcal{H}^{k}_{\beta }(\mathbf x)\right) \text{ d}\mathbf x\\
&= \sum_{\beta =1}^{3}v_{l(\beta ,k)}^{n} \cdot \int_{\tau ^{k}}\mathcal{H}_{\alpha }^{k}(\mathbf x)\cdot \mathcal{H}_{\beta }^{k}(\mathbf x)\text{ d}x\\
&= \sum_{\beta =1}^{3}v_{l(\beta ,k)}^{n}\cdot \frac{1}{3}T_{k} \sum_{i=1}^{3}\mathcal{H}_{\alpha }^{k}(\mathbf x^{g}_{i})\cdot \mathcal{H}_{\beta }^{k}(\mathbf x^{g}_{i}).
\end{aligned}
$$

The second term of the elemental load vector is
$$
\begin{aligned}
\int_{\tau ^{k}}c_{x,\alpha }^{k} \cdot \partial _{x}v^{n}+c_{y,\alpha }^{k}\cdot \partial _{y}v^{n}\text{ d}\mathbf x&=\int_{\tau ^{k}}c_{x,\alpha }^{k} \cdot \partial _{x}\left(\sum_{\beta =1}^{3}v^{n}_{l(\beta ,k)}\mathcal{H}_{\beta }^{k}\right)+c_{y,\alpha }^{k}\cdot \partial _{y}\left(\sum_{\beta =1}^{3}v^{n}_{l(\beta ,k)}\mathcal{H}_{\beta }^{k} \right)\text{ d}\mathbf x\\
&= \sum_{\beta =1}^{3}v_{l(\beta ,k)}^{n}\int_{\tau ^{k}}c_{x,\alpha }^{k}\cdot c_{x,\beta }^{k}+c^{k}_{y,\alpha }\cdot c_{y,\beta }^{k} \text{ d}\mathbf x\\
&= T^{k}\sum_{\beta =1}^{3}v_{l(\beta ,k)}^{n}(c_{x,\alpha }^{k}\cdot c_{x,\beta }^{k}+c^{k}_{y,\alpha }\cdot c_{y,\beta }^{k} ).
\end{aligned}
$$

Thus, the elemental load vector becomes
$$
\begin{aligned}
f^{k}_{\alpha}&= \sum_{\beta =1}^{3}v_{l(\beta ,k)}^{n}T_{k}\left(\frac{1}{3}\sum_{i=1}^{3}(\mathcal{H}_{\alpha }^{k}(\mathbf x^{g}_{i})\cdot \mathcal{H}_{\beta }^{k}(\mathbf x^{g}_{i}))-\Delta t \cdot (1-\theta )(c_{x,\alpha }^{k}c_{x,\beta }^{k}+c_{y,\alpha }^{k}c_{y,\beta }^{k}) \right)\\
&= :\sum_{\beta =1}^{3}v_{l(\beta ,k)}^{n}\cdot F^{k}_{\alpha ,\beta }
\end{aligned}
$$

$$F^{k}_{\alpha ,\beta }=T_{k}\left(\frac{1}{3}\sum_{i=1}^{3}(\mathcal{H}_{\alpha }^{k}(\mathbf x^{g}_{i})\cdot \mathcal{H}_{\beta }^{k}(\mathbf x^{g}_{i}))-\Delta t \cdot (1-\theta )(c_{x,\alpha }^{k}c_{x,\beta }^{k}+c_{y,\alpha }^{k}c_{y,\beta }^{k}) \right)$$


For local nodes $\mathbf x_{\beta }^{k}=[x_{\beta }^{k},y_{\beta }^{k}]$ we must have that $\mathcal{H}_{\alpha }^{k}(\mathbf x_{\beta })=\delta _{\alpha \beta}$, which we can write in matrix notation:
$$
\begin{bmatrix}1  & x_{1}^{k} & y_{1}^{k} \\ 1 & x_{2}^{k} & y_{2}^{k} \\ 1 & x_{3}^{k} & y_{3}^{k}\end{bmatrix}\begin{bmatrix}c_{1}^{k} & c_{1,x}^{k} & c_{1,y}^{k} \\ c_{2}^{k} & c_{2,x}^{k} & c_{2,y}^{k} \\ c_{3}^{k} & c_{3,x}^{k} & c_{3,y}^{k}\end{bmatrix}=\begin{bmatrix}1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1\end{bmatrix},
$$
meaning that we can compute the coefficient matrix by inverting the Vandermonde matrix:
$$
C=\begin{bmatrix}c_{1}^{k} & c_{1,x}^{k} & c_{1,y}^{k} \\ c_{2}^{k} & c_{2,x}^{k} & c_{2,y}^{k} \\ c_{3}^{k} & c_{3,x}^{k} & c_{3,y}^{k}\end{bmatrix}=\begin{bmatrix}1  & x_{1}^{k} & y_{1}^{k} \\ 1 & x_{2}^{k} & y_{2}^{k} \\ 1 & x_{3}^{k} & y_{3}^{k}\end{bmatrix}^{-1}=V^{-1}.
$$


To test our solution, we can set
$$v(x,y,t)=\cos (2\pi x)\cos (2\pi y)e^{-t}$$
Then,
$$\begin{aligned}
\nabla v&= -2\pi \begin{bmatrix}\sin (2\pi x)\cos (2\pi y) \\ \cos (2\pi x)\sin (2\pi y)\end{bmatrix}e^{-8\pi ^{2}t}\\
\nabla ^{2}v&= -8\pi ^{2}\cos (2\pi x)\cos (2\pi y)e^{-8\pi ^{2}t}
\end{aligned}$$
and
$$\partial _{t}v=-8\pi ^{2}\cos (2\pi x)\cos (2\pi y)e^{-8\pi ^{2}t}$$
