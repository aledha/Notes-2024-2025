In this paper, two main classes of problems will arise: $\textit{ordinary differential equations}$ (ODEs) and $\textit{partial differential equations}$ (PDEs).

## PDEs
A partial differential equation is an equation with a multivariate function and at least one partial derivative of that function. In introducing the finite element method, we will the $\textit{Poisson equation}$ in one dimension as our model problem: $$
\begin{align}
-\frac{ \partial^2 u }{ \partial x ^2}  & =f(x), & x \in[0,1] ,\\
u(0) & =0, \\
u(1) & =0.
\end{align}
$$
In the finite element method (FEM), we wish to derive a $\textit{weak formulation}$ of the PDE. This can be done by multiplying \eqref{eq:} with a smooth $\textit{test function}$ $v$ and integrating over the domain:$$
\begin{equation}
\int_{0}^1\left( -\frac{ \partial^2 u }{ \partial x^2 } \right)v  \,\text{d} x=\int_{0}^1fv \,\text{d} x.
\end{equation}
$$

Then, we perform integration by parts on the left hand side of \eqref{eq:} to obtain $$
\begin{equation}
-\left[ \frac{ \partial u }{ \partial x } v \right]_{0}^1+\int_{0}^1\frac{ \partial u }{ \partial x } \frac{ \partial v }{ \partial x } \,\text{d} x=\int_{0}^1fv \,\text{d} x.
\end{equation}
$$
We impose the Dirichlet conditions on the test function $v$ as well, such that $v(0)=v(1)=0$ and $$
\begin{equation}
\int_{0}^1\frac{ \partial u }{ \partial x } \frac{ \partial v }{ \partial x } \,\text{d} x=\int_{0}^1fv\,\text{d} x.
\end{equation}
$$

Notice that \eqref{eq:} is well defined if the functions $\frac{ \partial u }{ \partial x }, \frac{ \partial v }{ \partial x },v$ and $f$ are square integrable over the domain, i.e., $\frac{ \partial u }{ \partial x }, \frac{ \partial v }{ \partial x },v,f \in L^2(0,1)$. We can describe these conditions with the $\textit{Sobolev space}$ $$
\begin{equation}
H^1(\Omega)=\left\{ f:\int_{\Omega} \lvert f \rvert^2+\lvert \nabla f \rvert ^2\,\text{d} x<\infty  \right\}.
\end{equation}
$$
The Sobolev space with embedded with the Dirichlet boundary conditions is defined as $$
\begin{equation}
H^1_{0}(\Omega)=\{f\in H^1(\Omega): f\vert_{\partial\Omega}=0\}.
\end{equation}
$$
We are now ready to describe the weak formulation of the Poisson equation \eqref{eq:}-\eqref{eq:}. It reads as: Find $u\in H^1_{0}(0,1)$ such that $$
\begin{equation}
\int_{0}^1\frac{ \partial u }{ \partial x } \frac{ \partial v }{ \partial x } \,\text{d} x=\int_{0}^1fv\,\text{d} x \qquad\forall v\in H_{0}^1(0,1).
\end{equation}
$$

If $u$ solves the weak formulation \eqref{eq:}, we call it a $\textit{weak solution}$ of the Poisson equation \eqref{eq:}. Conversely, a classical solution of \eqref{eq:} is called a $\textit{strong solution}$. The distinction lies in that we impose the weaker requirement $u\in H_{0}^1(0,1)$ for the weak solution, while a strong solution must be $u\in C^2(0,1)$.

It can be shown\todo{ref? show?} that a strong solution also solves the weak formulation. Further, it can be shown that if the weak solution is also $u\in C^2(0,1)$, it solves the strong formulation \eqref{eq:}.

In most cases, there is no analytical weak solution of a weak formulation. We must therefore approximate the function $u$ in the infinite-dimensional function space $H^1_{0}$ with a $u_{h}$ from a finite-dimensional subspace $V_{h}\subset H^1_{0}$.  Since $V_{h}$ is finite-dimensional, it can be written as a span of basis functions: $V_{h}=\text{span}\{\phi_{0},\dots,\phi_{N-1} \}$, where $N$ is the dimension of $V_{h}$. Then, any $u_{h}\in V_{h}$ can be written as a linear combination of those basis functions: $$
\begin{equation}
u_{h}(x)=\sum _{i=0}^{N-1}u_{i}\phi_{i}(x),
\end{equation}
$$
where $u_{i}$ are scalar coefficients. Substitution of \eqref{eq:} into \eqref{eq:} gives us a modified weak formulation: Find $u_{0},\dots,u_{N-1}$ such that $$
\begin{equation}
\sum_{i=0}^{N-1}u_{i}\int_{0}^1\frac{ \partial \phi_{i} }{ \partial x } \frac{ \partial v }{ \partial x } \,\text{d} x=\int_{0}^1fv\,\text{d} x \qquad\forall v\in V_{h}.
\end{equation}
$$
\eqref{eq:} holding for every $v\in V_{h}$ is equivalent to \eqref{eq:} holding for every basis function $\phi_{0},\dots,\phi_{N-1}$, so we rewrite the formulation to: Find $u_{0},\dots,u_{N-1}$ such that $$
\begin{equation}
\sum_{i=0}^{N-1}u_{i}\int_{0}^1\frac{ \partial \phi_{i} }{ \partial x } \frac{ \partial \phi_{j} }{ \partial x } \,\text{d} x=\int_{0}^1f\phi_{j}\,\text{d} x \qquad \text{for }j=0,\dots,N-1.
\end{equation}
$$
\eqref{eq:} can be written as the linear system $$
\begin{equation}
\mathbf{A}\mathbf{u}=\mathbf{b},
\end{equation}
$$
where $\mathbf{u}=[u_{0},\dots,u_{N-1}]^T$ and $$
\begin{align}
A_{ij} & =\int_{0}^1\frac{ \partial \phi_{i} }{ \partial x } \frac{ \partial \phi_{j} }{ \partial x } \,\text{d} x, \\
b_{j} & =\int_{0}^1f\phi_{j}\,\text{d} x.
\end{align}
$$
After solving \eqref{eq:} for $\mathbf{u}$, it is easy to construct $u_{h}(x)$ from \eqref{eq:}. 

Let $\mathcal{T}_{h}=\{K_{j}\}_{j=0}^{M-1}$ be a triangulation of the domain $\Omega$ in the sense that $\bigcup_{j=0}^{M-1}K_{j}=\overline{\Omega}$, and that the elements $K_{j}$ are non-overlapping. $M$ is the number of elements. Let $K_{ref}$ be the $\textit{reference element}$, which can be mapped to any element $K_{j}$ using the mapping $\mathcal{F}_{j}:K_{ref}\to K_{j}$. We define the Jacobian of this mapping as $\mathbf{J}_{j}$.

In our one-dimensional problem, the elements $K_{j}$ and the reference element $K_{ref}$ are line segments. Let $0=x_{0},\dots,x_{M}=1$ be a partitioning of the domain, and define the elements as $K_{j}=(x_{j-1},x_{j})$. Let $K_{ref}=[0,1]$. The mapping from $K_{ref}$ to $K_{j}$ is $$
\begin{equation}
\mathcal{F}_{j}(x)=x(x_{j}-x_{j-1}).
\end{equation}
$$


The function space $V_{h}$ is defined by the basis functions $\phi_{i}$, 

