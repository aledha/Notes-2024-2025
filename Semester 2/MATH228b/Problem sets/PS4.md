![[Pasted image 20240305141731.png]]
$$u''''(x)=f(x),$$
Multiplying by a function $v \in V_{h}$ and integrating over the domain
$$\int_{0}^{1}u_{h}''''(x)v(x) \text{ d}x=\int_{0}^{1}f(x)v(x) \text{ d}x.$$
Integrating the LHS by parts twice,
$$\begin{align*}
\left[u_{h}'''(x)v(x) \right]_{0}^{1}-\int_{0}^{1}u_{h}'''v'(x) \text{ d}x&= \int_{0}^{1}f(x)v(x) \text{ d}x,\\
\left[u_{h}'''(x)v(x) \right]_{0}^{1}-\left[u_{h}''(x)v'(x) \right]_{0}^{1}+\int_{0}^{1}u_{h}''(x)v''(x) \text{ d}x&= \int_{0}^{1}f(x)v(x) \text{ d}x.
\end{align*}$$
We can impose the condition on $V_{h}$ that
$$V_{h}=\{v \in C^{1}(\left[0,1 \right]):v(0)=v'(0)=v(1)=v'(1)=0 \},$$
such that the first two terms vanish. Our Galerkin formulation is find $u_{h}\in V_{h}$ such that
$$\int_{0}^{1}u_{h}''(x)v''(x)\text{ d}x=\int_{0}^{1}f(x)v(x)\text{ d}x \quad\forall\quad v \in V_{h}.$$

![[Pasted image 20240305141817.png]]
We have degree 3 polynomials on each, meaning that we initially have a total of 8 degrees. The condition on each boundary reduces this by 4, and the differentiability reduces the DoF by 2. We are left with 2 degrees of freedom, and $\text{dim}(V_{h})=2$. As we will see, these two degrees correspond to the value and the derivative at $x=1/2$.

Consider Hermite **interpolation**,
$$f_{I}(x)=f(0)H_{0}(x)+f(1)H_{1}(x)+f'(0) \tilde H_{0}(x)+f'(1)\tilde H_{1}(x),$$
where
$$\begin{align*}
H_{0}(x) &=  2x^{3} - 3x^{2} + 1\qquad 
H_{1}(x) = 3x^{2} - 2x^{3}\\
\tilde H_{0}(x) &=  x^{3} - 2x^{2} + x \qquad 
\tilde H_{1}(x) = x^{3} - x^{2}
\end{align*}$$
Each element has two local basis functions. In the first element, we want the first basis function to satisfy $\psi _{1}(0)=\psi _{1}'(0)=\psi _{1}'(1/2)=0$ and $\psi _{1}(1/2)=1$. The second basis function should satisfy $\psi _{2}(0)=\psi _{2}'(0)=\psi _{2}(1/2)=0$ and $\psi _{2}'(1/2)=1$. Interpolating using these values gives
$$\psi  _{1}(x)=H_{1}(2x), \quad \psi _{2}(x)=\tilde H_{1}(2x).$$
Similarly, on the second element we get the local basis functions
$$\psi _{3}(x)=H_{0}(2x-1), \quad \psi _{4}(x)=\tilde H_{0}(2x-1).$$
So the two global basis functions are
$$\begin{align*}
\phi _{1}(x)&= \begin{cases}
H_{1}(2x)  & \quad\text{for }x \in [0,1/2)\\
H_{0}(2x-1) & \quad\text{for } x \in [1/2,1]
\end{cases}\\
\phi _{2}(x)&= \begin{cases}
\tilde H_{1}(2x)  & \quad\text{for }x \in [0,1/2)\\
\tilde H_{0}(2x-1) & \quad\text{for } x \in [1/2,1]
\end{cases}
\end{align*}$$

$$\begin{align*}
\phi _{1}(x)&= \begin{cases}
12x^{2}-16x^{3}  & \quad\text{for }x \in [0,1/2)\\
16x^{3}-36x^{2}+24x-4 & \quad\text{for } x \in [1/2,1]
\end{cases}\\
\phi _{2}(x)&= \begin{cases}
8x^{3}-4x^{2} & \quad\text{for }x \in [0,1/2)\\
 8 x^3 - 20 x^2 + 16 x - 4 & \quad\text{for } x \in [1/2,1]
\end{cases}
\end{align*}$$
![[Pasted image 20240311183148.png|400]]

![[Pasted image 20240305141848.png]]
Since we have derived a bases for $V_{h}$, we can now write $u_{h}(x)=u_{1}\phi _{1}(x)+u_{2}\phi _{2}(x)$. The Galerkin formulation simplifies to: Find $u_{1},u_{2}$ such that
$$\int_{0}^{1}u_{j}\phi _{j}''(x)\phi _{i}''(x)\text{ d}x=\int_{0}^{1}f(x)\phi _{i}(x)\text{ d}x \quad\text{for}\quad i=1,2 .$$
This can be written as a linear system,
$$A \mathbf u= \mathbf f,$$
where $a_{ij}=\int_{0}^{1}\phi _{j}''(x)\phi _{i}''(x)\text{ d}x$ and $f_{i}=\int_{0}^{1}f(x)\phi _{i}(x)\text{ d}x$.

$$\begin{align*}
\phi _{1}(x)&= \begin{cases}
12x^{2}-16x^{3}  & \quad\text{for }x \in [0,1/2)\\
16x^{3}-36x^{2}+24x-4 & \quad\text{for } x \in [1/2,1]
\end{cases}\\
\phi _{2}(x)&= \begin{cases}
8x^{3}-4x^{2} & \quad\text{for }x \in [0,1/2)\\
 8 x^3 - 20 x^2 + 16 x - 4 & \quad\text{for } x \in [1/2,1]
\end{cases}
\end{align*}$$
$$\begin{align*}
\phi _{1}'(x)&= \begin{cases}
24x-48x^{2}  & \quad\text{for }x \in [0,1/2) \\
48x^{2}-64x+24 & \quad\text{for }x \in [1/2,1]
\end{cases}\\
\phi _{1}''(x)&= \begin{cases}
24-96x & \quad\text{for }x \in [0,1/2)\\
96x-64 & \quad\text{for }x \in [1/2,1]
\end{cases}
\end{align*}$$
$$\begin{align*}
\phi _{2}'(x)&= \begin{cases}
24x^{2}-8x  & \quad\text{for }x \in [0,1/2)\\
24x^{2}-40x+16 & \quad\text{for }x \in [1/2,1]
\end{cases}\\
\phi _{2}''(x)&= \begin{cases}
48x-8  & \quad\text{for }x \in [0,1/2)\\
48x-40 & \quad\text{for }x \in [1/2,1]
\end{cases}
\end{align*}$$
Then, 
$$\begin{align*}
a_{11}&= \int_{0}^{1/2}(24-96x)^{2}\text{ d}x+\int_{1/2}^{1}(96x-64)^{2}\text{ d}x\\
&= 224\\
a_{22}&= \int_{0}^{1/2}(48x-8)^{2}\text{ d}x+\int_{1/2}^{1}(48x-40)^{2}\text{ d}x\\
&= 64\\
a_{12}=a_{21}&= \int_{0}^{1/2}(24-96x)(48x-8)\text{ d}x+\int_{1/2}^{1}(96x-64)(48x-40)\text{ d}x\\
&= -16
\end{align*}$$
and
$$\begin{align*}
f_{1}&= \int_{0}^{1/2}(480x-120)(12x^{2}-16x^{3}) \text{ d}x + \int_{1/2}^{1}(480x-120)(16x^{3}-36x^{2}+24x-4)\text{ d}x\\
&= 60\\
f_{2}&= \int_{0}^{1/2}(480x-120)(8x^{3}-4x^{2}) \text{ d}x + \int_{1/2}^{1}(480x-120)(8x^{3}-20x^{2}+16x-4)\text{ d}x
\end{align*}$$

![[Pasted image 20240305141859.png]]
$$\begin{align*}
-\nabla ^{2}u(x,y)&= 1 \quad\text{on }\Omega \\
n \cdot \nabla u&= 0 \quad\text{on }\Gamma _{N}\\
u&= 0 \quad\text{on }\Gamma _{D}
\end{align*}$$
We will get a triangular mesh $T_{h}$ from the mesh generator written in the homework last week. The space of piecewise linear continuous functions on this mesh is
$$V_{h}= \{v \in C^{0}(\Omega  ):v|_{K}\in \mathbb P_{1}\quad\forall\quad K \in T_{h} \}.$$

We integrate both sides of Poissons's equation in order to obtain the variational form. We seek $u_{h} \in V_{h}$ such that
$$\begin{align*}
\int_{\Omega }-(\nabla ^{2}u_{h})v \text{ d}x&= \int_{\Omega }v \text{ d}x \quad\forall\quad v \in V_{h},\\
\int_{\Omega }\nabla u_{h} \cdot \nabla v \text{ d}x -\oint_{\partial \Omega } (n \cdot \nabla u_{h})v \text{ d}x&= \int_{\Omega }v \text{ d}x \quad\forall\quad v \in V_{h},
\end{align*}$$
where we have used the divergence theorem. For implementations sake, we will first assume Neumann conditions on the entire boundary, and later impose Dirichlet conditions. The Galerkin form is the following: find $u_{h}\in V_{h}$ such that
$$\int_{\Omega }\nabla u_{h} \cdot \nabla v \text{ d}x= \int_{\Omega }v \text{ d}x \quad\forall\quad v \in V_{h}.$$
$V_{h}$ can be written as a span of the nodal basis functions, $V_{h}=\text{span}\{\phi _{1}, \dots, \phi _{n} \}$, where $n$ is the number of nodes. Since $u_{h}\in V_{h}$, we can write it as a sum of the nodal basis functions for $V_{h}$, i.e., $u_{h}(x)=\sum_{j=1}^{n}u_{h, j}\phi _{j}$, where $u_{h,j}$ are scalars. 
The Galerkin form can be rewritten to
$$\begin{align*}
\int_{\Omega }\nabla \left(\sum_{j=1}^{n}u_{h,j}\phi _{j} \right)\cdot \nabla \phi _{i}\text{ d}x&= \int_{\Omega }\phi _{i}\text{ d}x \quad\text{for }i=1,\dots,n,
\end{align*}$$
which can be written as a linear system,
$$A \mathbf u=\mathbf b,$$
where 
$$\begin{align*}
A_{ij}&= \int_{\Omega }\nabla \phi _{i} \cdot \nabla \phi _{j}\text{ d}x,\\
b_{i}&= \int_\Omega \phi _{i}\text{ d}x.
\end{align*}$$

Let's consider a single element, $T^{k}$, with the three local nodes $\mathbf x_{1}^{k},\mathbf x_{2}^{k}, \mathbf x_{3}^{k}$. The local basis functions 


![[Pasted image 20240305141914.png]]