To analyze the convergence of our solver, we require a test problem that has a solution to which the solver converges as the mesh is refined. There are two ways to generate this kind of solution: orchestrate a problem that has an analytical solution, or solve any well-posed problem for a very fine mesh, which can be compared to solutions for coarser meshes. We start with the latter.

Let the reference configuration be the unit cube $\Omega=[0,1]\times[0,1]\times[0,1]$ and let the fiber directions be $$
\begin{align*}
	\mathbf{f}_{0}  & =[1,0,0]^T, \\
\mathbf{s}_{0} & =[0,1,0]^T, \\
\mathbf{n}_{0} & =[0,0,1]^T.
\end{align*}
$$
We use the transversely isotropic Holzapfel-Ogden model, as described in \autoref{sec:constitutive eq}, and set the parameters as $a=2.28,b=9.726,a_{f}=1.68,b_{f}=15.779$. We arbitrarily set the the tension as $$
\begin{equation}
%\label{eq:}
	T_{a}(x_{1},x_{2},x_{3})=5e^{ -5((x_{2}-0.5)^2+(x_{3}-0.5)^2) }.
\end{equation}
$$
We set the tension on the $x_{1}=1$ boundary as $\mathbf{T}=[1,0,0]^T$, and fix the geometry with a Dirichlet condition on the $x_{1}=0$ boundary: $$
\begin{equation}
%\label{eq:}
	\mathbf{u}(0,x_{2},x_{3})=\boldsymbol{0}.
\end{equation}
$$
For some $\Delta x$, discretize the domain to $x_{i,0},x_{i,1},\dots x_{i,N}$ where $x_{i,j}=j\Delta x$ for $i=1,2,3$. Then the domain can be divided into $N^3$ cuboidal cells. We obtain the triangulation $\mathcal{T}_{h}$ by fitting two tetrahedron in each cell. As discussed in \autoref{}, the displacement $\mathbf{u}$ can be found by applying Newton's method to the Galerkin formulation \eqref{eq:}-\eqref{eq:}.

We wish to analyze how $\mathbf{u}$ behaves for different choices of $\Delta x$. First we find the "true solution" $\mathbf{u}_\text{fine}$ by solving for $\Delta x_{\text{fine}}=0.075$. then, with the coarser discretizations $\Delta x=0.1,0.15,0.2,0.3,0.4$, we solve for each $\mathbf{u}_{i}$ and find the error in the $L_{2}$ norm as $$
\begin{equation*}
	E_{i}=\left( \int_{\Omega}\lvert \mathbf{u}_\text{fine}-\mathbf{u}_{i} \rvert ^2 \,\text{d} \mathbf{x} \right)^{1/2} \quad \text{for }i=1,2,3,4,5.
\end{equation*}
$$






## Method of Manufactured Solution
In the context of static continuum mechanics, the method of manufactured solution can be summarized as
1. Pick a reference configuration $\Omega$.
2. Pick a current configuration $\omega$.
3. Analytically derive boundary conditions and an expression for $T_{a}$.

