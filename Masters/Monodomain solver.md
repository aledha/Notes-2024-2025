We want to solve the monodomain model, which is given by
$$
\begin{aligned}
\frac{\partial s}{\partial t}&= f(s,v,t),&x\in H,\\
\frac{\lambda }{1-\lambda }\nabla \cdot (M_{i}\nabla v)&= \frac{\partial v}{\partial t}+I_{\text{ion}}(v,s), &x\in H,\\
n \cdot (M_{i}\nabla v)&= 0, &x\in \partial H.
\end{aligned}
$$
To start, we will implement a solver for just the diffusion term, and then we will add the reactionary term later. The model simplifies to 
$$
\begin{aligned}
\frac{\partial s}{\partial t}&= f(s,v,t),&x\in H,\\
\frac{\lambda }{1-\lambda }\nabla \cdot (M_{i}\nabla v)&= \frac{\partial v}{\partial t}+I_{\text{ion}}(s), &x\in H,\\
n \cdot (M_{i}\nabla v)&= 0, &x\in \partial H.
\end{aligned}
$$
## Analytical Solution of the Simplified Monodomain Model
We'll start off with $H$ being the unit square, $H=[0,1]\times[0,1]$, and $M_{i}=1$.
In order to test the convergence of our numerical scheme, we introduce a potential
$$
v(x,y,t)= \sin (2\pi x)\cos (2\pi y)e^{-t}.
$$
Then the time derivative is
$$
\frac{\partial v}{\partial t}=-\sin(2\pi x)\cos (2\pi y)e^{-t}.
$$
The space derivatives are
$$
\nabla v=e^{-t}\begin{bmatrix}2\pi \cos (2\pi x)\cos (2\pi y) \\ -2\pi \sin (2\pi x)\sin (2\pi y)\end{bmatrix},
$$
and 
$$
\begin{aligned}
\nabla \cdot \nabla v&= 2\pi e^{-t}(-2\pi \sin (2\pi x)\cos (2\pi y)  -2\pi \sin (2\pi x)\cos (2\pi y))\\
&= -4\pi ^{2}\sin(2\pi x)\cos (2\pi y)e^{-t}.
\end{aligned}
$$