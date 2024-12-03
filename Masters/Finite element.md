$$
\frac{\partial v}{\partial t}=\frac{1}{\chi C_{m}}\frac{\lambda }{1+\lambda }\nabla \cdot(M_{i}\nabla v)+\frac{1}{C_{m}}I_\text{stim},
$$

To to solve the PDE \ref{}, we will utilize a $\theta$-method to discretize in time:
$$
\begin{equation}
\frac{v^{n+1}-v^{n}}{\Delta t}= \frac{1}{\chi C_{m}}\frac{\lambda }{1+\lambda }\left(\theta \nabla \cdot(M_{i}\nabla v^{n+1})+(1-\theta )\nabla \cdot(M_{i}\nabla v^{n}) \right)+\frac{1}{C_{m}}I_\text{stim}. %\label{eq:thetarule}
\end{equation}
$$
Notice that this $\theta$ differs from the parameter $\theta$ used in the operator splitting. However, a parameter choice of $\theta =\frac{1}{2}$ gives the second order Crank-Nicholson scheme, and the same choice for $\theta$ gives second order accuracy for the operator splitting. Similarly, $\theta\neq \frac{1}{2}$ gives a first order scheme for both the $\theta$-method and the operator splitting. Hence, we treat the parameter as the same. 

Let $\alpha= \frac{\Delta t}{\chi C_{m}} \frac{\lambda}{1+\lambda}$ and $\beta= \frac{\Delta t}{C_{m}}$, then \ref{eq:thetarule} becomes
$$
\begin{equation}
v^{n+1}-v^n =\alpha\theta \nabla \cdot(M_{i}\nabla v^{n+1})+\alpha(1-\theta)\nabla \cdot(M_{i}\nabla v^n)+\beta I_\text{stim}. %\label{eq:timediscrete}
\end{equation}
$$

Now, we can reformulate \ref{eq:timediscrete} into a Galerkin formulation: 
For some suitable function space $V$, find $v^{n+1}\in V$, given $v^n\in V$, such that for every $\phi \in V$,
$$
\begin{align*}
\int_{H}(v^{n+1}-v^n)\phi \text{ d} \mathbf{x} & =\int_{H}(\alpha\theta \nabla \cdot(M_{i}\nabla v^{n+1})+\alpha(1-\theta)\nabla \cdot(M_{i}\nabla v^n)+\beta I_\text{stim})\phi \text{ d} \mathbf{x} \\
\int_{H}v^{n+1}\phi \text{ d} \mathbf{x} -\alpha\theta\int_{H}\nabla \cdot(M_{i}\nabla v^{n+1})\phi \text{ d} \mathbf{x} & =\int_{H}(\beta I_\text{stim}+v^n)\phi \text{ d} \mathbf{x}+ \alpha(1-\theta)\int_{H}\nabla \cdot(M_{i}\nabla v^n)\phi \text{ d} \mathbf{x} 
\end{align*}
$$

Using Greene's theorem, we can rewrite the last term of both sides as
$$
\begin{align*}
-\alpha\theta\int_{H}\nabla \cdot(M_{i}\nabla v^{n+1})\phi \text{ d} \mathbf{x} & = -\alpha\theta \int_{\partial H}\mathbf{n}\cdot(M_{i}\nabla v^{n+1})\phi \text{ d} \mathbf{x}+\alpha\theta\int_{H}(M_{i}\nabla v^{n+1})\cdot \nabla \phi \text{ d} \mathbf{x}, \\
\alpha(1-\theta)\int_{H}\nabla \cdot(M_{i}\nabla v^{n})\phi \text{ d} \mathbf{x} & = \alpha(1-\theta) \int_{\partial H}\mathbf{n}\cdot(M_{i}\nabla v^{n})\phi \text{ d} \mathbf{x}-\alpha(1-\theta)\int_{H}(M_{i}\nabla v^{n+1})\cdot \nabla \phi \text{ d} \mathbf{x},
\end{align*}
$$

where the boundary integrals vanish due to the boundary condition \ref{}. Substituting the terms back gives
$$
\begin{equation}
\int_{H}v^{n+1}\phi  +\alpha\theta(M_{i}\nabla v^{n+1})\cdot\nabla\phi \text{ d} \mathbf{x}  =\int_{H}(\beta I_\text{stim}+v^n)\phi - \alpha(1-\theta)(M_{i}\nabla v^n)\cdot \nabla\phi \text{ d} \mathbf{x} .%\label{eq:galerkin}
\end{equation}
$$

The bilinear and linear form are
$$\begin{align}
a(v^{n+1},\phi )&= \int_{H}v^{n+1}\phi  +\alpha\theta(M_{i}\nabla v^{n+1})\cdot\nabla\phi\text{ d}\mathbf x,\\ %\label{eq:bilinearform}
L(\phi )&= \int_{H} (\beta I_\text{stim}+v^n)\phi - \alpha(1-\theta)(M_{i}\nabla v^n)\cdot \nabla\phi \text{ d} \mathbf{x}.%\label{eq:linearform}
\end{align}$$


