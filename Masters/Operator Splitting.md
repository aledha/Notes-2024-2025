Operator splitting is a numerical technique to solve problems of the form
$$
\begin{equation}
%\label{eq:opsplit}
\frac{ \partial y }{ \partial t } =L_{1}(y)+L_{2}(y),
\end{equation}
$$
where $L_{1},L_{2}$ are operators on $y$. 

For a parameter $\theta \in[0,1]$ and a time step $\Delta t$, denote $t_{n}=n\Delta t$ and $t_{n+\theta}=n\Delta t+\theta \Delta t$. Letting $y^{n}=y(t_{n})$, we solve for $y^{n+1}$ by applying the following steps.
1. With $y^{n}$ as an initial condition, solve $\frac{ \partial y }{ \partial t }=L_{1}(y)$ for $t\in[t_{n},t_{n+\theta}]$ and denote the solution as $y_{\theta}^{n}$.
2. With $y^{n}_{\theta}$ as an initial condition, solve $\frac{ \partial y }{ \partial t }=L_{2}(y)$ for $t\in[t_{n},t_{n+1}]$ and denote the solution as $y_{\theta}^{n+1}$.
3. With $y^{n+1}_{\theta}$ as an initial condition, solve $\frac{ \partial y }{ \partial t }=L_{1}(y)$ for $t\in[t_{n+\theta},t_{n+1}]$ and denote the solution as $y^{n+1}$.

This method is called $\textit{Godunov splitting}$, while the special case of $\theta=\frac{1}{2}$ is called $\textit{Strang splitting}$. It can be shown \todo{show?} that Strang splitting is second order accurate in time, while Godunov splitting is first order accurate in time.

To apply operator splitting to the monodomain equation \eqref{eq:mono}, we must rewrite it to be of the form \eqref{eq:opsplit}: $$
\begin{equation}
\frac{ \partial v }{ \partial t } =\frac{1}{\chi C_{m}}\nabla \cdot(\mathbf{M}\nabla v)-\frac{1}{C_{m}}I_\text{ion}(v,\mathbf{s})+\frac{1}{C_{m}}I_\text{stim}.
\end{equation}
$$
Now we let $\mathbf{y}=\begin{bmatrix}v \\ \mathbf{s}\end{bmatrix}$ such that $$
\begin{equation}
\frac{ \partial \mathbf{y} }{ \partial t } =\frac{ \partial  }{ \partial t } \begin{bmatrix}
v  \\
\mathbf{s} 
\end{bmatrix}=\begin{bmatrix}
\frac{1}{\chi C_{m}}\nabla \cdot(\mathbf{M}\nabla v)-\frac{1}{C_{m}}I_\text{ion}(v,\mathbf{s}) \\
\mathbf{f}(\mathbf{s},v,t)
\end{bmatrix}.
\end{equation}
$$
Then we choose the operators as $$
\begin{align}
L_{1}(\mathbf{y})=L_{1} \left( \begin{bmatrix}
v \\
\mathbf{s}
\end{bmatrix} \right)  & =\begin{bmatrix}
-\frac{1}{C_{m}}I_\text{ion}(v,\mathbf{s}) \\
\mathbf{f}(\mathbf{s},v,t)
\end{bmatrix}, \\
L_{2}(\mathbf{y})=L_{2} \left( \begin{bmatrix}
v \\
\mathbf{s}
\end{bmatrix} \right)  & =\begin{bmatrix}
\frac{1}{\chi C_{m}}\nabla \cdot(\mathbf{M}\nabla v)\\
0
\end{bmatrix}.
\end{align}
$$
Now we have reduced the problem of solving the monodomain equation into the subproblems
$$
\begin{align}
\frac{ \partial v }{ \partial t }  & =-\frac{1}{C_{m}}I_\text{ion}(v,\mathbf{s}), \\
\frac{ \partial \mathbf{s} }{ \partial t }  & =\mathbf{f}(\mathbf{s},v,t), \\
\frac{ \partial v }{ \partial t }  & =\frac{1}{\chi C_{m}}\nabla \cdot(\mathbf{M}\nabla v)+\frac{1}{C_{m}}I_\text{stim}.
\end{align}
$$

\eqref{eq:}-\eqref{eq:} is a system of ODEs, which can be solved with, for example, the forward Euler or generalized Rush-Larsen scheme. \eqref{eq:} is a PDE, which we will solve with the finite element method.

## Variational formulation
Firstly, we need to discretize \eqref{eq:} in time, which we will do with a $\theta$-method. For a given time step $\Delta t$, let $v^n \in V_{h}$ be an approximation to $v(n \Delta t)$ for some suitable function space $V_{h}$. The $\theta$-method then reads $$
\begin{equation}
\frac{v^{n+1}-v^n }{\Delta t}   =\frac{\theta}{\chi C_{m}}\nabla \cdot(\mathbf{M}\nabla v^{n+1})+\frac{1-\theta}{\chi C_{m}}\nabla \cdot(\mathbf{M}\nabla v^{n})+\frac{1}{C_{m}}I_\text{stim}.
\end{equation}
$$
To obtain a variational formulation, we multiply \eqref{eq:} by a test function $\phi \in V_{h}$ and integrate over our domain $\Omega$. The variational problem currently reads: Given $v^n$, find $v^{n+1}\in V_{h}$ such that $$
\begin{equation}
\int_{\Omega}\phi(v^{n+1}-v^n )\,\text{d} \mathbf{X} =\int_{\Omega}\phi\left( \frac{\Delta t\theta}{\chi C_{m}}\nabla \cdot(\mathbf{M}\nabla v^{n+1})+\frac{\Delta t(1-\theta)}{\chi C_{m}}\nabla \cdot(\mathbf{M}\nabla v^{n}) +\frac{1}{C_{m}}I_\text{stim} \right)\,\text{d} \mathbf{X},
\end{equation}
$$
for all $\phi \in V_{h}$. Rewriting \eqref{eq:} gives
$$
\begin{equation}
\int_{\Omega}\phi v^{n+1}\,\text{d} \mathbf{X}-\frac{\Delta t\theta}{\chi C_{m}}\int_{\Omega} \phi\nabla \cdot(\mathbf{M}\nabla v^{n+1}) \,\text{d} \mathbf{X}=\int_{\Omega}\phi\left(  v^{n}+\frac{1}{C_{m}}I_\text{stim} \right) \,\text{d} \mathbf{X}+\frac{\Delta t(1-\theta)}{\chi C_{m}}\int_{\Omega}\phi\nabla \cdot(\mathbf{M}\nabla v^{n})\,\text{d} \mathbf{X}.
\end{equation}
$$

We can apply the divergence theorem on the integral in the second term of the left hand side of \eqref{eq:}: $$
\begin{equation}
\int_{\Omega}\phi\nabla \cdot(\mathbf{M}\nabla v^{n+1}) \,\text{d} \mathbf{X}   =\int_{\partial \Omega}\phi \mathbf{n}\cdot(\mathbf{M}\nabla v^{n+1})\,\text{d} \mathbf{X}-\int_{\Omega}\nabla \phi \cdot(\mathbf{M}\nabla v^{n+1})\,\text{d} \mathbf{X},
\end{equation}
$$
where the boundary integral vanishes because of the boundary condition \eqref{eq:monobc}, such that$$
\begin{equation}
\int_{\Omega}\phi\nabla \cdot(\mathbf{M}\nabla v^{n+1}) \,\text{d} \mathbf{X}   =-\int_{\Omega}\nabla \phi \cdot(\mathbf{M}\nabla v^{n+1})\,\text{d} \mathbf{X}.
\end{equation}
$$
We get a similar result on the integral in the second term of the right hand side of \eqref{eq:}. Our variational problem then reads: Given $v^n\in V_{h}$, find $v^{n+1}\in V_{h}$ such that $$
\begin{equation}
\int_{\Omega}\phi v^{n+1}\,\text{d} \mathbf{X}+\frac{\Delta t\theta}{\chi C_{m}}\int_{\Omega} \nabla\phi \cdot(\mathbf{M}\nabla v^{n+1}) \,\text{d} \mathbf{X}=\int_{\Omega}\phi\left(  v^{n}+\frac{1}{C_{m}}I_\text{stim} \right) \,\text{d} \mathbf{X}-\frac{\Delta t(1-\theta)}{\chi C_{m}}\int_{\Omega}\nabla\phi \cdot(\mathbf{M}\nabla v^{n})\,\text{d} \mathbf{X},
\end{equation}
$$
for every $\phi \in V_{h}$.

## Monolithic Variational Formulation
Firstly, we need to discretize \eqref{eq:} in time, which we will do with a $\theta$-method. For a given time step $\Delta t$, let $v^n \in V_{h}$ be an approximation to $v(n \Delta t)$ and $\mathbf{s}^n\in S_{h}$ be an approximation for $\mathbf{s}(n\Delta t)$ for some suitable function spaces $V_{h}$ and $S_{h}$. Applying the $\theta$-method to \eqref{eq:} gives
$$
\begin{align}
\frac{v^{n+1}-v^n }{\Delta t} & =  \frac{\theta}{\chi C_{m}}\nabla \cdot(\mathbf{M}\nabla v^{n+1})+\frac{1-\theta}{\chi C_{m}}\nabla \cdot(\mathbf{M}\nabla v^{n}) \\
 &\quad-\frac{\theta}{C_{m}}I_\text{ion}(v^{n+1},\mathbf{s}^{n+1})-\frac{1-\theta}{C_{m}}I_\text{ion}(v^n,\mathbf{s}^n), \\
\frac{\mathbf{s}^{n+1}-\mathbf{s}^n}{\Delta t} & =  \theta \mathbf{f}(\mathbf{s}^{n+1},v^{n+1},t_{n+1})+(1-\theta)\mathbf{f}(\mathbf{s}^n,v^n,t_{n}).
\end{align}
$$

To obtain a variational formulation, we multiply \eqref{eq:} by the test functions $\phi \in V_{h}$ and $\boldsymbol{\psi} \in S_{h}$ and integrate over our domain $\Omega$. The variational problem currently reads: Given $v^n,\mathbf{s}^n$, find $v^{n+1}\in V_{h}$ and $\mathbf{s}^{n+1}\in S_{h}$ such that 
$$
\begin{align}
\int_{\Omega}\phi(v^{n+1}-v^n )\,\text{d} \mathbf{X}  & =\int_{\Omega}\phi\left( \frac{\Delta t\theta}{\chi C_{m}}\nabla \cdot(\mathbf{M}\nabla v^{n+1})+\frac{\Delta t(1-\theta)}{\chi C_{m}}\nabla \cdot(\mathbf{M}\nabla v^{n})\right)\,\text{d} \mathbf{X} \\
 & \quad+\int_{\Omega}\phi \left( -\frac{\Delta t\theta }{C_{m}}I_\text{ion}(v^{n+1},\mathbf{s}^{n+1})-\frac{\Delta t(1-\theta)}{C_{m}}I_\text{ion}(v^n,\mathbf{s}^n) \right)\,\text{d} \mathbf{X},  \\
\int_{\Omega}\boldsymbol{\psi}\cdot(\mathbf{s}^{n+1}-\mathbf{s}^n) \,\text{d} \mathbf{X}& = \int_{\Omega} \theta \boldsymbol{\psi}\cdot \mathbf{f}(\mathbf{s}^{n+1},v^{n+1},t_{n+1})+(1-\theta)\boldsymbol{\psi} \cdot\mathbf{f}(\mathbf{s}^n,v^n,t_{n}),
\end{align}
$$
for every $\phi \in V_{h}$ and $\boldsymbol{\psi}\in S_{h}$. Rewriting \eqref{eq:} to collect like terms yields $$
\begin{equation}
\int_{\Omega}\boldsymbol{\psi}\cdot(\mathbf{s}^{n+1}- \theta\mathbf{f}(\mathbf{s}^{n+1},v^{n+1},t_{n+1})) \,\text{d} \mathbf{X} = \int_{\Omega}  \boldsymbol{\psi}\cdot (\mathbf{s}^n+(1-\theta)\mathbf{f}(\mathbf{s}^n,v^n,t_{n}))\,\text{d} \mathbf{X},
\end{equation}
$$
while \eqref{eq:} becomes$$
\begin{align}
 & \int_{\Omega}\phi\left(v^{n+1} +\frac{\Delta t\theta }{C_{m}}I_\text{ion}(v^{n+1},\mathbf{s}^{n+1}) \right) \,\text{d} \mathbf{X} -\frac{\Delta t\theta}{\chi C_{m}}\int_{\Omega}\phi\nabla \cdot(\mathbf{M}\nabla v^{n+1}) \,\text{d} \mathbf{X}  \\
& =\int_{\Omega}\phi \left(v^n-\frac{\Delta t(1-\theta)}{C_{m}}I_\text{ion}(v^n,\mathbf{s}^n) \right)\,\text{d} \mathbf{X} +\frac{\Delta t(1-\theta)}{\chi C_{m}}\int_{\Omega}\phi\nabla \cdot(\mathbf{M}\nabla v^{n})\,\text{d} \mathbf{X}.
\end{align}
$$
We can apply the divergence theorem on the integral in the second term of the left hand side of \eqref{eq:}: $$
\begin{equation}
\int_{\Omega}\phi\nabla \cdot(\mathbf{M}\nabla v^{n+1}) \,\text{d} \mathbf{X}   =\int_{\partial \Omega}\phi \mathbf{n}\cdot(\mathbf{M}\nabla v^{n+1})\,\text{d} \mathbf{X}-\int_{\Omega}\nabla \phi \cdot(\mathbf{M}\nabla v^{n+1})\,\text{d} \mathbf{X},
\end{equation}
$$
where the boundary integral vanishes because of the boundary condition \eqref{eq:monobc}, such that$$
\begin{equation}
\int_{\Omega}\phi\nabla \cdot(\mathbf{M}\nabla v^{n+1}) \,\text{d} \mathbf{X}   =-\int_{\Omega}\nabla \phi \cdot(\mathbf{M}\nabla v^{n+1})\,\text{d} \mathbf{X}.
\end{equation}
$$
We get a similar result on the integral in the second term of the right hand side of \eqref{eq:}. Then, the monolithic variational reads: Given $v^n,\mathbf{s}^n$, find $v^{n+1}\in V_{h}$ and $\mathbf{s}^{n+1}\in S_{h}$ such that $$
\begin{align}
 & \int_{\Omega}\left( \phi v^{n+1} +\frac{\Delta t\theta }{C_{m}}(\phi I_\text{ion}(v^{n+1},\mathbf{s}^{n+1})  +\nabla\phi \cdot(\mathbf{M}\nabla v^{n+1})) \right)  \,\text{d} \mathbf{X}  \\
& =\int_{\Omega} \left( \phi v^n-\frac{\Delta t(1-\theta)}{C_{m}}\left( \phi I_\text{ion}(v^n,\mathbf{s}^n)  +\nabla\phi \cdot(\mathbf{M}\nabla v^{n}) \right) \right)  \,\text{d} \mathbf{X},  & \forall \phi \in V_{h}, \\
 & \int_{\Omega}\boldsymbol{\psi}\cdot(\mathbf{s}^{n+1}- \theta\mathbf{f}(\mathbf{s}^{n+1},v^{n+1},t_{n+1})) \,\text{d} \mathbf{X} = \int_{\Omega}  \boldsymbol{\psi}\cdot (\mathbf{s}^n+(1-\theta)\mathbf{f}(\mathbf{s}^n,v^n,t_{n}))\,\text{d} \mathbf{X}  , & \forall \boldsymbol{\psi}\in S_{h}.
\end{align}
$$
## Monolithic
The final coupling scheme we consider is a \emph{monolithic} scheme. 
