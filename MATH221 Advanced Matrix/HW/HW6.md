![[Pasted image 20231009094318.png|800]]


![[Pasted image 20231009120333.png|800]]
![[Pasted image 20231009094350.png|800]]
Let's suppose that $x^{*}$ minimizes $\lVert Ax-b \rVert_{2}$. Then, the gradient of $(Ax-b)^{T}(Ax-b)$ must be zero at this point.
$$\begin{align*}
0&= \lim_{e  \to 0}\frac{(A(x^{*}+e)-b)^{T}(A(x^{*}+e)-b)- (Ax^{*}-b)^{T}(Ax^{*}-b)}{\lVert e \rVert_{2}}\\
&= \lim_{e  \to 0} \frac{((Ax^{*}-b)^{T}+(Ae)^{T})((Ax^{*}-b) +Ae)- (Ax^{*}-b)^{T}(Ax^{*}-b)}{\lVert e \rVert_{2}}\\
&= \lim_{e  \to 0} \frac{(Ax^{*}-b)^{T}Ae+e^{T}A^{T}(Ax^{*}-b)+e^{T}A^{T}Ae}{\lVert e \rVert_{2}}\\
&= \lim_{e  \to 0} \frac{2e^{T}A^{T}(Ax^{*}-b)+e^{T}A^{T}Ae}{\lVert e \rVert_{2}}

\end{align*}$$
The second term goes to zero
$$\frac{e^{T}A^{T}Ae}{\lVert e \rVert_{2}} \le \frac{\lVert A \rVert_{2}^2\lVert e \rVert_{2}^{2}}{\lVert e \rVert_{2}}\stackrel{e\to0}{\to}0.$$
Since the whole expression should equal zero, we must then have that the first term is also zero,
$$\lim_{e \to 0} \frac{2e^{T}A^{T}(Ax^{*}-b)}{\lVert e \rVert_{2}}=0$$
Denoting $r=b-Ax$, we must therefore have that 
$$A^{T}r=0$$
And by our definition of $r=b-Ax$, we get that $r+Ax=b$ and end up with the linear system

$$\begin{bmatrix}I & A \\ A^{T} & 0 \end{bmatrix}\begin{bmatrix}r \\ x\end{bmatrix}=\begin{bmatrix}b \\ 0\end{bmatrix}.$$

![[Pasted image 20231009094407.png|800]]
$$A=U \Sigma V^{T}$$
What is the condition number of the coefficient matrix, in terms of the singular values of A? Hint: Use the SVD of A
$$\begin{align*}
Z&= \begin{bmatrix}I & A \\ A^{T} & 0\end{bmatrix}\\
&= \begin{bmatrix}I & U \Sigma V^{T} \\ V \Sigma ^{T}U^{T} & 0\end{bmatrix}\\
&= \begin{bmatrix}U & 0\\
0 & V\end{bmatrix} \begin{bmatrix}U^{T} & \Sigma V^{T}\\
\Sigma ^{T}U^{T} & 0 \end{bmatrix}\\
&= \begin{bmatrix}U & 0\\
0 & V\end{bmatrix} \begin{bmatrix}I & \Sigma \\
\Sigma ^{T} & 0 \end{bmatrix} \begin{bmatrix}U^{T} & 0\\
0 & V^{T}\end{bmatrix}
\end{align*}$$

$$\kappa(Z)= \frac{\sigma _{1}}{\sigma _{n}}$$

![[Pasted image 20231009094421.png|800]]



![[Pasted image 20231009094446.png|800]]
We want to minimize the following expression
$$\lVert D(Ax-b) \rVert_{2}=\lVert \tilde Ax-\tilde b \rVert_{2},$$
where $\tilde A=DA,\quad \tilde b=Db$. Following the exact same steps as in question 3.3, we end up at the same normal equations,
$$\begin{bmatrix}I & \tilde A \\ \tilde A^{T} & 0 \end{bmatrix}\begin{bmatrix}r \\ x\end{bmatrix}=\begin{bmatrix}\tilde b \\ 0\end{bmatrix}.$$
With our definitions,
$$\begin{bmatrix}I & D A \\  A^{T}D & 0 \end{bmatrix}\begin{bmatrix}r \\ x\end{bmatrix}=\begin{bmatrix}D b \\ 0\end{bmatrix}.$$

More generally, let's move on to minimizing $\lVert Ax-b \rVert_{C}=((Ax-b)^{T}C(Ax-b))^{\frac{1}{2}}$, where $C$ is symmetric positive definite.
Since $C$ is symmetric positive definite, there exists exactly one matrix $E$ such that $E^{2}=C$.  $E$ is also symmetric positive definite, so $C=E^{T}E$. Then, we have
$$\lVert Ax -b\rVert_{C}=((Ax-b)^{T}E^{T}E(Ax-b))^{\frac{1}{2}}=\lVert E(Ax-b) \rVert_{2}.$$
With the same reasoning as before, we arrive at the matrix equations
$$\begin{bmatrix}I & E A \\  A^{T}E & 0 \end{bmatrix}\begin{bmatrix}r \\ x\end{bmatrix}=\begin{bmatrix}E b \\ 0\end{bmatrix}$$

![[Pasted image 20231009094510.png|800]]
$$A=\begin{bmatrix} * &   &   &  \\ u_{2}v_{1}  & *  \\ \vdots & \ddots & * \\ u_{n-1}v_{1} & \ddots &  \ddots & *  \\ u_{n}v_{1} & \dots  & \dots & u_{n}v_{n-1} & * \end{bmatrix}$$
Let's consider the Givens rotation
$$R(n,n-1)=\left[\begin{array}{c|cc}I   \\ \hline       &  c & -s \\     &   s & c\end{array} \right],$$
where $c$ and $s$ are chosen such that 
$$\begin{bmatrix}c & -s \\ s & c\end{bmatrix}\begin{bmatrix}u_{n-1}v_{1}  \\ u_{n}v_{1}\end{bmatrix}=\begin{bmatrix}\sqrt{(u_{n-1}v_{1})^{2}+(u_{n}v_{1})^{2}} \\ 0\end{bmatrix},$$
which simplifies to
$$\begin{bmatrix}c & -s \\ s & c\end{bmatrix}\begin{bmatrix}u_{n-1} \\ u_{n}\end{bmatrix}=\begin{bmatrix}\sqrt{u_{n-1}^{2}+u_{n}^{2}} \\ 0\end{bmatrix}$$
https://math.mit.edu/~plamen/18.335/Solns2.pdf


![[Pasted image 20231009094533.png|800]]
We have that $\text{rank}(A)=m$ and that $\text{rank}(A)+\text{dim}(\text{ker}(A))=n$. Then the kernel is $(n-m)$-dimensional.
Let $x^{*}$ minimize $\lVert Ax-b \rVert_{2}$.
For any $y \in \text{ker}(A)$, we have that $x^{*}+y$ is a solution, as it minimises $\lVert Ax-b \rVert_{2}$.  
The solution is therefore $(n-m)$-dimensional.

A natural way to make the solution unique is to impose an additional condition


![[Pasted image 20231009094546.png|800]]
errata: The question says A is m-by-n, so the vectors u(i) in Part 1 should be of length m, not n, and the loop in Part 2 should be "for i=1:min(m-1,n)", not "for i=1:m".(RuoChen Liang)

$$P=(I-2u_{b}u_{b}^{T})\cdots(I-2u_{2}u_{2}^{T})(I-2u_{1}u_{1}^{T})$$

$$P=I-UTU^{T}=I-\begin{bmatrix}u_{1}, \dots, u_{b}\end{bmatrix}\begin{bmatrix}t_{11} & 0 & 0 \\ \vdots & \ddots & 0 \\ t_{b1} & \dots & t_{bb}\end{bmatrix}\begin{bmatrix}u_{1} \\ \vdots \\ u_{b}\end{bmatrix}$$




$$\begin{align*}
P&= I\\
	&-2u_{b}u_{b}^{T}-\dots-2u_{1}u_{1}^{T}\\
&+2
\end{align*}$$