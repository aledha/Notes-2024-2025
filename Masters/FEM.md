In this paper, two main classes of problems will arise: $\textit{ordinary differential equations}$ (ODEs) and $\textit{partial differential equations}$ (PDEs).

## PDEs
A partial differential equation is an equation with a multivariate function and at least one partial derivative of that function. In introducing the finite element method, we will the $\textit{Poisson equation}$ in one dimension as our model problem: $$
\begin{align}
-\frac{ \partial^2 u }{ \partial x ^2}  & =f(x), & x \in[0,1] ,\\
u(0) & =0, \\
u(1) & =0.
\end{align}
$$
