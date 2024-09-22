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

In order to test the convergence of our numerical scheme, we need to introduce a potential that satisfies the boundary condition $n \cdot \nabla v=0$ on $\partial H$. One potential that satisfies this is
$$
v(x,y,t)= \cos (2\pi x)\cos (2\pi y)e^{-t}.
$$
Then the time derivative is
$$
\frac{\partial v}{\partial t}=-\cos(2\pi x)\cos (2\pi y)e^{-t}.
$$
The space derivatives are
$$
\nabla v=-2\pi e^{-t}\begin{bmatrix} \sin (2\pi x)\cos (2\pi y) \\  \cos (2\pi x)\sin (2\pi y)\end{bmatrix},
$$
and 
$$
\begin{aligned}
\nabla \cdot \nabla v&= -2\pi e^{-t}(2\pi \cos (2\pi x)\cos (2\pi y) + 2\pi \cos (2\pi x)\cos (2\pi y))\\
&= -8\pi ^{2}\cos(2\pi x)\cos (2\pi y)e^{-t}.
\end{aligned}
$$
We see that the boundary condition $n \cdot \nabla v=0$ is fulfilled on $\partial H$.