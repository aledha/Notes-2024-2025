In this paper, two main classes of problems will arise: $\textit{ordinary differential equations}$ (ODEs) and $\textit{partial differential equations}$ (PDEs). The following is a list of the main equations we will consider throughout this paper:
$$
\begin{align}
\nabla \cdot \mathbf{P} & =\boldsymbol{0},\qquad & \mathbf{X}\in\Omega, \\
\mathbf{u} & =\mathbf{u}_{D}, & \mathbf{X}\in \partial\Omega_{D}, \\
\mathbf{P}\mathbf{N} & =\mathbf{T}, & \mathbf{X}\in \partial\Omega_{N},  \\
\nabla \cdot(\mathbf{M}\nabla v)  & =\chi\left( C_{m}\frac{ \partial v }{ \partial t } +I_\text{ion}(v,\mathbf{s}) -I_\text{stim}\right) , & \quad \mathbf{X}\in \Omega, \\
\frac{ \partial \mathbf{s} }{ \partial t }  & =\mathbf{f}(\mathbf{s},v,t)  & \mathbf{X}\in \Omega, \\
\mathbf{n}\cdot(\mathbf{M}\nabla v) & =0,\quad & \mathbf{X}\in \partial \Omega.
\end{align}
$$

\eqref{eq:intro force balance} with boundary conditions \eqref{eq:intro mech dirichlet}-\eqref{eq:intro mech neumann} describe a continuum mechanical model of cardiac contraction, which will be derived in more detail in \autoref{sec:mech}. Here, $\mathbf{P}$ is the first Piola-Kirchoff stress tensor, $\mathbf{u}$ is the displacement vector, $\mathbf{N}$ is the normal vector, and $\mathbf{T}$ is the traction acting on the boundary.

\eqref{eq:intro mono} with boundary condition \eqref{eq:intro monobc} is a reaction-diffusion equation describing how the depolarization wave travels through the heart, while \eqref{eq:intro cell ode} describes the dynamics of ions traveling between the extracellular and intracellular cell spaces. \eqref{eq:intro mono} and \eqref{eq:intro cell ode} are a coupled system. Here, $\mathbf{M}$ is the conductivity tensor, $v$ is the transmembrane potential, $\chi$ is the cells surface to volume ratio, $C_{m}$ is the cell membranes capacitance, $I_\text{ion}$ is the current arising from ions traveling across the membrane, $I_\text{stim}$ is an applied stimulating current, and $\mathbf{s}$ is the cells state vector.

\eqref{eq:intro force balance} and \eqref{eq:intro mono} are nonlinear PDEs. That is, they include partial derivatives of $\mathbf{u}$ and $v$, the unknown quantities we wish to find. These equations generally do not have analytical solutions, and we will therefore approximate these by use of the \emph{finite element method} (FEM). This method will be described in \autoref{sec:fem}. Further, \eqref{eq:intro force balance} must be solved with a root finding algorithm\todo{short section on Newtons method?}. \eqref{eq:intro mono} is also time-dependant, so it must be discretized in both space and time.

\eqref{eq:intro cell ode} is a system of first-order ODEs. That is, they contain only derivatives with respect to time $t$. There are a wide range of schemes that approximate the solutions of ODE systems, which vary in accuracy, stability, and computational load. In \autoref{sec:ode solvers}, we introduce some of these methods. 


## PDEs
A partial differential equation is an equation with a multivariate function and at least one partial derivative of that function. In introducing the finite element method, we will consider the $\textit{Poisson equation}$ in one dimension as our model problem: $$
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

To construct $\mathbf{A}$ and $\mathbf{b}$, we must first choose the forms of the basis functions $\phi_{i}$. Let $0=x_{0},\dots,x_{M}=1$ be a partitioning of the domain, with step sizes $h_{i}=x_{i}-x_{i-1}$. The simplest choice of $\phi_{i}$ are the \emph{first order Lagrange basis functions}:
$$
\begin{equation}
\phi _{i}(x)=\begin{cases} 
\frac{x-x_{i-1}}{h_{i}}, & x\in[x_{i-1},x_{i}), \\
\frac{x_{i+1}-x}{h_{i+1}}, & x\in (x_{i},x_{i+1}], \\
0, & \text{else},
\end{cases}
\end{equation}
$$
for $i=1,\dots M-1$, and $$
\begin{align}
\phi _{0}(x) & =\begin{cases}
\frac{x_{1}-x}{h_{1}}, & x\in[0,x_{1}], \\
0, & \text{else},
\end{cases} \\
\phi _{M}(x) & =\begin{cases}
\frac{x-x_{M-1}}{h_{M}}, & x\in[x_{M-1},x_{M}], \\
0, & \text{else}.
\end{cases}
\end{align}
$$
These piecewise linear basis functions are often called \emph{hat functions}, and have the property that $$
\begin{equation}
\phi _{j}(x_{i})=\begin{cases} 1, & i,=j \\ 0, & i≠j,\end{cases}
\end{equation}
$$
and $\phi_{i}$ has compact support on the interval $[x_{i-1},x_{i+1}]$. We could now construct $\mathbf{A}$ and $\mathbf{b}$ and solve the linear system, but it is easy to see that this will become increasingly hard for a higher-dimensional problem or a more complex choice of basis functions. Instead, we will attempt to generalize the construction of $\mathbf{A}$ and $\mathbf{b}$.

Let $\mathcal{T}_{h}=\{K_{j}\}_{j=0}^{M-1}$ be a triangulation of the domain $\Omega$ in the sense that $\bigcup_{j=0}^{M-1}K_{j}=\overline{\Omega}$, and that the elements $K_{j}$ are non-overlapping. $M$ is the number of elements. Let $K_{ref}$ be the $\textit{reference element}$, which can be mapped to any element $K_{j}$ using the mapping $\mathcal{F}_{j}:K_{ref}\to K_{j}$. We define the Jacobian of this mapping as $\mathbf{J}_{j}$.

In our one-dimensional problem, the elements $K_{j}$ and the reference element $K_{ref}$ are line segments. Let the elements be $K_{j}=(x_{j-1},x_{j})$. We can now rewrite \eqref{eq:}-\eqref{eq:} to $$
\begin{align}
A_{ij} & =\sum_{k=0}^{M-1}\int_{K_{k}}\frac{ \partial \phi_{i} }{ \partial x } \frac{ \partial \phi_{j} }{ \partial x } \,\text{d} x, \\
b_{j} & =\int_{0}^1f\phi_{j}\,\text{d} x.
\end{align}
$$


and let the reference element be $K_{ref}=[0,1]$. The mapping from $K_{ref}$ to $K_{j}$ is $$
\begin{equation}
\mathcal{F}_{j}(\bar{x})=x_{j-1}+\bar{x}(x_{j}-x_{j-1}).
\end{equation}
$$
Next we define the basis vectors on the reference element as $$
\begin{align}
\psi_{0}(\bar{x}) & =1-\bar{x}, \\
\psi_{1} (\bar{x})& =\bar{x},
\end{align}
$$
such that 
$$
\begin{equation}
\int_{K_{j}}\phi_{i}(x)\,\text{d} x=\int_{K_{ref}}\phi_{i}(\mathcal{F}_{j}(\bar{x}))\cdot\lvert \det  J_{j}(\bar{x}) \rvert \,\text{d} \bar{x}
\end{equation}
$$



Then we can rewrite \eqref{eq:} to $$
\begin{align}
A_{ij} & =\int_{0}^1\frac{ \partial \phi(\mathcal{F}_{j}(\bar{x})) }{ \partial x } \frac{ \partial \phi_{j} }{ \partial x } \,\text{d} x, \\
b_{j} & =\int_{0}^1f\phi_{j}\,\text{d} x.
\end{align}
$$