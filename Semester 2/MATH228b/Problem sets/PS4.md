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
Here is a plot of these basis functions. We see that $\phi _{1}$ controls the value at $x=1/2$, while $\phi _{2}$ controls the derivative at $x=1/2$. 
![[Pasted image 20240311183148.png|400]]

![[Pasted image 20240305141848.png]]
Since we have derived a bases for $V_{h}$, we can now write $u_{h}(x)=u_{1}\phi _{1}(x)+u_{2}\phi _{2}(x)$. The Galerkin formulation simplifies to: Find $u_{1},u_{2}$ such that
$$\int_{0}^{1}u_{h,j}\phi _{j}''(x)\phi _{i}''(x)\text{ d}x=\int_{0}^{1}f(x)\phi _{i}(x)\text{ d}x \quad\text{for}\quad i=1,2 .$$
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
f_{2}&= \int_{0}^{1/2}(480x-120)(8x^{3}-4x^{2}) \text{ d}x + \int_{1/2}^{1}(480x-120)(8x^{3}-20x^{2}+16x-4)\text{ d}x\\
&= 8
\end{align*}$$

Now we can compute $u_{h}(x)=u_{h,1}\cdot \phi _{1}(x)+u_{h,2}\cdot \phi _{2}(x)$. Let's also compute the exact solution to compare the error.
$$\begin{align*}
u''''(x)&= 480x-120\\
u'''(x)&= 240x^{2}-120x+C_{1}\\
u''(x)&= 80x^{3}-60x^{2}+C_{1}x+C_{2}\\
u'(x)&= 20x^{4}-20x^{3}+C_{1}'x^{2}+C_{2}x+C_{3}\\
u(x)&= 4x^{5}-5x^{4}+C_{1}''x^{3}+C_{2}'x^{2}+C_{3}x+C_{4}
\end{align*}$$
Imposing the conditions,
$$\begin{align*}
u(0)&= C_{4}=0\\
u'(0)&= C_{3}=0\\
u'(1)&=20-20+3C_{1}''+2C_{2}'=0 \quad\implies\quad C_{1}''= -\frac{2}{3}C_{2}'\\
u(1)&= -1+C_{1}''+C_{2}'=0 \\
&\qquad -1- \frac{2}{3}C_{2}'+C_{2}'=0\\
&\qquad C_{2}'=3\\
&\qquad C_{1}''=-2
\end{align*}$$
So the exact solution is
$$u(x)=4x^{5}-5x^{4}-2x^{3}+3x^{2}$$
Here are the exact and numerical solution plotted
![[Pasted image 20240315105306.png|500]]

<div style="page-break-after: always;"></div>

![[Pasted image 20240305141859.png]]
See attached code. 
Here are my results of the examples
![[Pasted image 20240315105534.png|400]]
![[Pasted image 20240315105547.png|400]]
![[Pasted image 20240315105559.png|400]]

<div style="page-break-after: always;"></div>

![[Pasted image 20240305141914.png]]
See attached code. My results are
![[Pasted image 20240315105627.png|500]]
which is to be expected, due to the geometric singularity that arises in the polygon.