To analyze the convergence of our solver, we require a test problem that has a solution to which the solver converges for finer meshes. There are two ways to generate this kind of solution: orchestrate a problem that has an analytical solution, or solve any well-posed problem for a very fine mesh, which can be compared to solutions for coarser meshes. We start with the latter.

Let the reference configuration be the unit cube $\Omega=[0,1]\times[0,1]\times[0,1]$ and let the fiber directions be am




## Method of Manufactured Solution
In the context of static continuum mechanics, the method of manufactured solution can be summarized as
1. Pick a reference configuration $\Omega$.
2. Pick a current configuration $\omega$.
3. Analytically derive boundary conditions and an expression for $T_{a}$.

