![[Pasted image 20240305141731.png]]
$$u''''(x)=f(x),$$
Multiplying by a function $v \in V_{h}$ and integrating over the domain
$$\int_{0}^{1}u''''(x)v(x) \text{ d}x=\int_{0}^{1}f(x)v(x) \text{ d}x.$$
Integrating the LHS by parts twice,
$$\begin{align*}
\left[u'''(x)v(x) \right]_{0}^{1}-\int_{0}^{1}u'''v'(x) \text{ d}x&= \int_{0}^{1}f(x)v(x) \text{ d}x,\\
\left[u'''(x)v(x) \right]_{0}^{1}-\left[u''(x)v'(x) \right]_{0}^{1}+\int_{0}^{1}u''(x)v''(x) \text{ d}x&= \int_{0}^{1}f(x)v(x) \text{ d}x.
\end{align*}$$
We can impose the condition on $V_{h}$ that
$$V_{h}=\{v \in C^{1}(\left[0,1 \right]):v(0)=v'(0)=v(1)=v'(1)=0 \},$$
such that the first two terms vanish. Our Galerkin formulation is find $u_{h}\in V_{h}$ such that
$$\int_{0}^{1}u_{h}''(x)v''(x)\text{ d}x=\int_{0}^{1}f(x)v(x)\text{ d}x \quad\forall\quad v \in V_{h}.$$

![[Pasted image 20240305141817.png]]
$$\begin{align*}
\mathcal{H}_{1}(x)&= 0 \cdot H_{0}(x)+a\cdot H_{1}(x)+ 0 \cdot \tilde H_{0}(x)+b \tilde H_{1}(x)\\
&= a \cdot H_{1}(2x)+b \cdot \tilde H_{1}(2x) \\
\mathcal{H}_{2}(x)&= a \cdot H_{0}(2x-1) + 0 \cdot H_{1}(2x-1)+c \cdot \tilde H_{0}(2x-1)+0 \cdot \tilde H_{1}(2x-1)\\
&= a \cdot H_{0}(2x-1)+ c \cdot \tilde H_{0}(2x-1)
\end{align*}$$

Let us consider using a linear combination of Hermite polynomials as a basis,
$$\begin{align*}
\psi _{1}(x)&= aH_{0}(x)+bH_{1}(x)+cH_{2}(x) +dH_{3}(x),\\
\psi _{2}(x)&= eH_{0}(x)+fH_{1}(x)+gH_{2}(x)+hH_{3}(x).
\end{align*}$$
where
$$\begin{align*}
H_{0}(x)&= 1,\\
H_{1}(x)&= 2x,\\
H_{2}(x)&= 4x^{2}-2,\\
H_{3}(x) &= 8x^{3}-12x.
\end{align*}$$
Parametrise by adding a midpoint to each element. Each element has four local nodes and four local basis functions. 
$$\begin{bmatrix}H_{0}(x_{1}) & H_{1}(x_{1}) & H_{2}(x_{1}) & H_{3}(x_{1}) \\ H_{0}(x_{2}) & H_{1}(x_{2}) & H_{2}(x_{2}) & H_{3}(x_{2}) \\ H_{0}(x_{3}) & H_{1}(x_{3}) & H_{2}(x_{3}) & H_{3}(x_{3}) \\ H_{0}(x_{4}) & H_{1}(x_{4}) & H_{2}(x_{4}) & H_{3}(x_{4})\end{bmatrix} \begin{bmatrix}a_{1} & a_{2} & a_{3} & a_{4} \\ b_{1} & b_{2} & b_{3} & b_{4} \\ c_{1} & c_{2} & c_{3} & c_{4} \\ d_{1} & d_{2} & d_{3} & d_{4}\end{bmatrix}=\begin{bmatrix}0 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\ 0 & 0 & 1 & 0 \\ 0 & 0 & 0 & 1\end{bmatrix}$$


![[Pasted image 20240305141848.png]]

![[Pasted image 20240305141859.png]]
$$\begin{align*}
-\nabla ^{2}u(x,y)&= 1 \quad\text{on }\Omega \\
n \cdot \nabla u&= 0 \quad\text{on }\Gamma _{N}\\
u&= 0 \quad\text{on }\Gamma _{D}
\end{align*}$$

$$\begin{align*}
\int_{\Omega }-(\nabla ^{2}u)v \text{ d}x&= \int_{\Omega }v \text{ d}x\\
\int_{\Omega }\nabla u \cdot \nabla v \text{ d}x -\oint_{\partial \Omega } (n \cdot \nabla u)v \text{ d}x&= \int_{\Omega }v \text{ d}x\\
\int_{\Omega }\nabla u \cdot \nabla v \text{ d}x&= \int_{\Omega }v \text{ d}x
\end{align*}$$

![[Pasted image 20240305141914.png]]