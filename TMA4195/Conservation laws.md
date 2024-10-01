(in 3D)
Expressing conservation of some entity $A$.
* Conserved density: $\rho (x,t)$
* Flux density: $J(x,t)$
* Source density: $q(x,t)$
$[\rho]=[A]m^{-3}$, $[\mathbf J]=[A]m^{-2}s^{-1}$.

**Continuum models**: Use moving average by choosing an averaging scale $r_{2}$. Then 
$$\overline{\phi }=\frac{1}{\text{Volume}(B_{r_{2}}(x))}\iiint_{B_{r_{2}}(x)}\phi (y) \text{ d}y$$

Conserved denisty: 
amount of $A$ in $\Omega$ $=\iiint_{\Omega }\rho (\mathbf x,t)\text{ d}V$.

Total amount of $A$ passing $S$ per time = flux. 
```ad-Definition
title: Net flux.

Given a normal vector $\mathbf n$ and flux $\mathbf J$, the flux through a surface $S$ is
$$\iint_{S}\mathbf J \cdot \mathbf n \text{ d}S$$
```

#### Example
$\mathbf J=a \frac{\mathbf x}{\lVert \mathbf x \rVert^3}$. Then
$\lVert \mathbf J \rVert=\frac{\lvert a \rvert \cdot \lVert x \rVert}{\lVert x \rVert^{3}}=\frac{\lvert a \rvert}{\lVert x \rVert^{2}}$.

Let's calculate the flux out of a ball centered at the origin. The normal vector of the ball is then $\mathbf n=\frac{\mathbf x}{\lVert \mathbf x \rVert}$ Then,
$$\begin{aligned}
\vec{J}\cdot \vec{n}&= a \frac{\vec{x}}{\lVert \vec{x} \rVert^{3}}\cdot \frac{\vec{x}}{\lVert \vec{x} \rVert}\\
&= a \frac{\lVert \vec{x} \rVert^{2}}{\lVert \vec{x} \rVert^{4}}\\
&= \frac{a}{\lVert \vec{x} \rVert^{2}}.
\end{aligned}$$
Since $S$ is a sphere with radius $R$,
$$\vec{J}\cdot \vec{n}=\frac{a}{R^{2}}$$
The flux is
$$\begin{aligned}
\int_{S_{R}}\vec{J}\cdot \vec{x}\text{ d}S&= \int_{S_{R}}\frac{a}{R^{2}}\text{ d}s\\
&= \frac{a}{R^{2}}4\pi R^{2}\\
&= 4a \pi 
\end{aligned}$$

```ad-Definition
title: Source/Sink.
Density $q(\vec{x},t)$.
In general,
$$\iiint_{\Omega }q(\vec{x},t)\text{ d}V$$
is the external supply of $A$ per time.
```

```ad-Definition
title: Universal conservation law.
collapse: open
For a domain $\Omega$, and let the surface $\partial \Omega$ have $\vec{n}$ pointing out.
$$\frac{\text{d}}{\text{d}t}\iiint_{\Omega }\rho (\vec{x},t)\text{ d}V=-\iint_{\partial \Omega}\vec{J}\cdot \vec{n}\text{ d}s+\iiint_{\Omega }q(\vec{x},t)\text{ d}V$$

Using divergence theorem,

$$\iiint_{\Omega }\frac{\partial \rho}{\partial t} (\vec{x},t)\text{ d}V+\iiint_{\Omega }\nabla \cdot \vec{J}\text{ d}V-\iiint_{\Omega }q(\vec{x},t)=0$$

$$\iiint_{\Omega }\left(\frac{\partial \rho }{\partial t}+\nabla \cdot \vec{J}-q \right) \text{ d}V=0$$

For arbitrary $\Omega$, 
$$\frac{\partial \rho }{\partial t}+\nabla \cdot \vec{J}-q=0$$
```
