![[Pasted image 20231009094318.png|800]]
![[Pasted image 20231011152517.png|500]]
The second for loop can be written as
$$\begin{align*}
r_{ji}&= q_{j}^{T}a_{i}\tag{CGS}\\
r_{ji}&= q_{j}^{T}q_{i}=q_{j}^{T}\left(a_{i}-\sum_{k=1}^{j-1}r_{ki}q_{k}\right)\tag{MGS}
\end{align*}$$
At this point, $\{q_{k} \}_{k \le j}$ forms a sequence of orthogonal vectors, resulting in that $q^{T}_{j}\sum_{k=1}^{j-1}r_{ki}q_{k}=0$, and the two formulas are equivalent.
![[Pasted image 20231009120333.png|800]]
![[Pasted image 20231009094350.png|800]]
Let's suppose that $x^{*}$ minimizes $\lVert Ax-b \rVert_{2}$, which also minimizes $\lVert Ax-b \rVert_{2}^{2}$. Then, the gradient of $(Ax-b)^{T}(Ax-b)$ must be zero at this point.
$$\begin{align*}
0&= \lim_{e  \to 0}\frac{(A(x^{*}+e)-b)^{T}(A(x^{*}+e)-b)- (Ax^{*}-b)^{T}(Ax^{*}-b)}{\lVert e \rVert_{2}}\\
&= \lim_{e  \to 0} \frac{((Ax^{*}-b)^{T}+(Ae)^{T})((Ax^{*}-b) +Ae)- (Ax^{*}-b)^{T}(Ax^{*}-b)}{\lVert e \rVert_{2}}\\
&= \lim_{e  \to 0} \frac{(Ax^{*}-b)^{T}Ae+e^{T}A^{T}(Ax^{*}-b)+e^{T}A^{T}Ae}{\lVert e \rVert_{2}}\\
&= \lim_{e  \to 0} \frac{2e^{T}A^{T}(Ax^{*}-b)+e^{T}A^{T}Ae}{\lVert e \rVert_{2}}

\end{align*}$$
The second term goes to zero since
$$\frac{e^{T}A^{T}Ae}{\lVert e \rVert_{2}} \le \frac{\lVert A \rVert_{2}^2\lVert e \rVert_{2}^{2}}{\lVert e \rVert_{2}}\stackrel{e\to0}{\to}0.$$
As the whole expression should go to zero, the first term should go to zero as well
$$\lim_{e \to 0} \frac{2e^{T}A^{T}(Ax^{*}-b)}{\lVert e \rVert_{2}}=0$$
Denoting $r=b-Ax^{*}$, we must therefore have that 
$$A^{T}r=0$$
And by our definition of $r=b-Ax^{*}$, we get that $r+Ax=b$ and end up with the linear system

$$\begin{bmatrix}I & A \\ A^{T} & 0 \end{bmatrix}\begin{bmatrix}r \\ x\end{bmatrix}=\begin{bmatrix}b \\ 0\end{bmatrix}.$$

![[Pasted image 20231009094407.png|800]]
We are interested in the singular values of $Z$.
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
The matrices on the left and right are clearly unitary, so the singular values of $Z$ must be the same as the singular values of $X=\begin{bmatrix}I_{m} & \Sigma  \\ \Sigma ^{T} & 0\end{bmatrix}$.
$$XX^{T}=\begin{bmatrix}I_{m} & \Sigma  \\ \Sigma ^{T} & 0\end{bmatrix}\begin{bmatrix}I_{m} & \Sigma  \\ \Sigma ^{T} & 0\end{bmatrix}=\begin{bmatrix}I_{m}+\Sigma \Sigma ^{T} & \Sigma  \\ \Sigma ^{T} & \Sigma^{T} \Sigma\end{bmatrix}$$
I feel like I should be able to find the singular values of $X$, but I'm having trouble. 
Only thing I could think of was using Geshgorins circle theorem, but that would only get me the bound 
$$\sigma _{\min}(A)^{2}-\sigma _\text{max}(A)\le \sigma(Z)^{2} \le 1+\sigma _\text{max}(A)^{2}+\sigma _\text{max}(A) $$
$$\kappa(Z)= \frac{\sigma _{1}}{\sigma _{n}}$$

![[Pasted image 20231009094421.png|800]]
Gaussian elimination, being wary of dimensions,
$$\begin{align*}
Z&= \left[\begin{array}{cc|cc}I_{m} & A & I_{m} & 0\\
A^{T} & 0 & 0 & I_{n}\end{array}\right]\\
&= \left[\begin{array}{cc|cc}I_{m} & A & I_{m} & 0\\
0 & -A^{T}A & -A^{T} & I_{n}\end{array}\right]\\
&= \left[\begin{array}{cc|cc}I_{m} & 0 & I_{m}-A(A^{T}A)^{-1}A^{T} & A(A^{T}A)^{-1}\\
0 & -A^{T}A & -A^{T} & I_{n}\end{array}\right]\\
&= \left[\begin{array}{cc|cc}I_{m} & 0 & I_{m}-A(A^{T}A)^{-1}A^{T} & A(A^{T}A)^{-1}\\
0 & I_{n} & (-A^{T}A)^{-1}(-A^{T}) & (-A^{T}A)^{-1}\end{array}\right]
\end{align*}$$
Our inverse of the coefficient matrix is
$$Z^{-1}=\begin{bmatrix} I_{m}-A(A^{T}A)^{-1}A^{T} & A(A^{T}A)^{-1}\\
 (A^{T}A)^{-1}A^{T} & -(A^{T}A)^{-1}\end{bmatrix},$$
where the $(2,1)$ block entry is reminiscent of the solution of the normal equations: $x=(A^{T}A)^{-1}A^{T}b$.

![[Pasted image 20231009094446.png|800]]
We want to minimize the following expression
$$\lVert D(Ax-b) \rVert_{2}=\lVert \tilde Ax-\tilde b \rVert_{2},$$
where $\tilde A=DA,\quad \tilde b=Db$. Following the exact same steps as in question 3.3, we end up at the same block matrix equation,
$$\begin{bmatrix}I & \tilde A \\ \tilde A^{T} & 0 \end{bmatrix}\begin{bmatrix}r \\ x\end{bmatrix}=\begin{bmatrix}\tilde b \\ 0\end{bmatrix}.$$
With our definitions,
$$\begin{bmatrix}I & D A \\  A^{T}D & 0 \end{bmatrix}\begin{bmatrix}r \\ x\end{bmatrix}=\begin{bmatrix}D b \\ 0\end{bmatrix}.$$
and the equivalent normal equations
$$\begin{cases}
r=D(b-Ax) \\
A^{T}Dr=0.
\end{cases}$$

More generally, let's move on to minimizing $\lVert Ax-b \rVert_{C}=((Ax-b)^{T}C(Ax-b))^{\frac{1}{2}}$, where $C$ is symmetric positive definite.
Since $C$ is symmetric positive definite, there exists exactly one matrix $E$ such that $E^{2}=C$.  $E$ is also symmetric (and positive definite), so $C=E^{T}E$. Then, we have
$$\lVert Ax -b\rVert_{C}=((Ax-b)^{T}E^{T}E(Ax-b))^{\frac{1}{2}}=\lVert E(Ax-b) \rVert_{2}.$$
With the same reasoning as before, we arrive at the block matrix equations
$$\begin{bmatrix}I & E A \\  A^{T}E & 0 \end{bmatrix}\begin{bmatrix}r \\ x\end{bmatrix}=\begin{bmatrix}E b \\ 0\end{bmatrix},$$
and the equivalent normal equations
$$\begin{cases}
r=E(b-Ax) \\
A^{T}Er=0.
\end{cases}$$

![[Pasted image 20231009094510.png|800]]
$$A=\begin{bmatrix} * & *  &   *&* & *  \\ u_{2}v_{1}  & * & * & * & *  \\ \vdots & \ddots & *  & * & *\\ u_{n-1}v_{1} & \ddots &  \ddots & *   & *\\ u_{n}v_{1} & \dots  & \dots & u_{n}v_{n-1} & * \end{bmatrix}$$
Let's consider the Givens rotation
$$R(n,n-1)=\left[\begin{array}{c|cc}I   \\ \hline       &  c & -s \\     &   s & c\end{array} \right],$$
where $c$ and $s$ are chosen such that 
$$\begin{bmatrix}c & -s \\ s & c\end{bmatrix}\begin{bmatrix}u_{n-1}v_{1}  \\ u_{n}v_{1}\end{bmatrix}=\begin{bmatrix}\sqrt{(u_{n-1}v_{1})^{2}+(u_{n}v_{1})^{2}} \\ 0\end{bmatrix},$$
which simplifies to
$$\begin{bmatrix}c & -s \\ s & c\end{bmatrix}\begin{bmatrix}u_{n-1} \\ u_{n}\end{bmatrix}=\begin{bmatrix}\sqrt{u_{n-1}^{2}+u_{n}^{2}} \\ 0\end{bmatrix}.$$
Crucially, $c$ and $s$ are chosen independent of $v_{1}$, meaning that this Givens rotation does not only kill the bottom left term $u_{n}v_{1}$, but also all the terms on the bottom up to $u_{n}v_{n-2}$. For some $i<n-1$, we have that
$$\begin{bmatrix}c & -s \\ s & c\end{bmatrix}\begin{bmatrix}u_{n-1}v_{i} \\ u_{n}v_{i}\end{bmatrix}=v_{i}\begin{bmatrix}c & -s \\ s & c\end{bmatrix}\begin{bmatrix}u_{n-1} \\ u_{n}\end{bmatrix}=v_{i}\begin{bmatrix}\sqrt{u_{n-1}^{2}+u_{n}^{2}} \\ 0\end{bmatrix}.$$
I claim that the same thing occurs for the rows above. This can be seen by noting that after the first step, $R(n,n-1)A$ looks like
$$A=\begin{bmatrix} * &  * & *  & * & * \\ u_{2}v_{1}  & *  & * & *  & *\\ \vdots & \ddots & * & *  & *\\ v_{1}\sqrt{u_{n-1}^{2}+u_{n}^{2}} & \dots &  v_{n-2}\sqrt{u_{n-1}^{2}+u_{n}^{2}} & *  & * \\ 0 & \dots  & 0 & * &* \end{bmatrix}$$
Repeating the same logic as above, by replacing $u_{n}$ with $\sqrt{u_{n-1}^{2}+u_{n}^{2}}$ and replacing $u_{n-1}$ with $u_{n-2}$, we get the same result, that one rotation kills the row up to the 2-subdiagonal.

After $n-2$ rotations, all terms under the subdiagonal have vanished. With an additional $n-1$ rotations, the subdiagonal also vanishes. 

Each rotation costs $\mathcal{O}(n)$, so my algorithm costs $\mathcal{O}(n^{2})$.
![[Pasted image 20231009094533.png|800]]
We have that $\text{rank}(A)=m$ and that $\text{rank}(A)+\text{dim}(\text{ker}(A))=n$. Then the kernel is $(n-m)$-dimensional.
Let $x^{*}$ minimize $\lVert Ax-b \rVert_{2}$.
For any $y \in \text{ker}(A)$, we have that $x^{*}+y$ is a solution, as it minimises $\lVert Ax-b \rVert_{2}$.  
The solution is therefore $(n-m)$-dimensional.

A natural way to make the solution unique is to impose a restriction on $x$,
$$\min_{x}\lVert Ax-b \rVert_{2}^{2}+\lVert x \rVert_{2}^{2}$$
with the same strategy as in 3.3.1, the gradient of the above equation at a solution $x^{*}$ must equal zero,
$$\begin{align*}
0&=  \lim_{e  \to 0}\frac{(A(x^{*}+e)-b)^{T}(A(x^{*}+e)-b)+(x^{*}+e)^{T}(x^{*}+e)- (Ax^{*}-b)^{T}(Ax^{*}-b)-(x^{*})^{T}x^{*}}{\lVert e \rVert_{2}}\\
&= \lim_{e  \to 0} \frac{2e^{T}A^{T}(Ax^{*}-b)+e^{T}A^{T}Ae+2e^{T}x^{*}+e^{T}e}{\lVert e \rVert_{2}}
\end{align*}$$
We see that the second and third terms goes to zero as $e$ goes to zero, so then $x^{*}$ must satisfy
$$\lim_{e \to 0} \frac{2e^{T}A^{T}(Ax^{*}-b)+2e^{T}x^{*}}{\lVert e \rVert_{2}}=\lim_{e \to 0}\frac{2e^{T}(A^{T}(Ax^{*}-b)+x^{*})}{\lVert e \rVert_{2}}=0.$$
In consequence, we must have $A^{T}(Ax^{*}-b)+x^{*}=0$. Denoting $r=b-Ax$, we can set up the linear system
$$\begin{bmatrix}I & A \\ -A^{T} & I \end{bmatrix}\begin{bmatrix}r \\ x\end{bmatrix}=\begin{bmatrix}b \\ 0\end{bmatrix}.$$
With the normal equation
$$(A^{T}A+I)x^{*}=A^{T}b$$
Given the SVD of $A$, we can end up with an exact solution,
$$\begin{align*}
(V \Sigma^{T} U^{T}U \Sigma V^{T}+I_{n})x^{*}&= V \Sigma U^{T}b\\
(V \Sigma ^{T}\Sigma V^{T}+VV^{T})x^{*}&= V \Sigma U^{T}b\\
	V(\Sigma ^{T}\Sigma +I_{n})V^{T}x^{*}&= V \Sigma U^{T}b\\
x^{*}&= V(\Sigma ^{T}\Sigma +I_{n})^{-1}\Sigma U^{T}b\\
	x^{*}&= \sum_{i=1}^{m} \frac{\sigma _{i}}{\sigma _{i}^{2}+1}v_{i}u_{i}^{T}b
\end{align*}$$

![[Pasted image 20231009094546.png|800]]
errata: The question says A is m-by-n, so the vectors u(i) in Part 1 should be of length m, not n, and the loop in Part 2 should be "for i=1:min(m-1,n)", not "for i=1:m".(RuoChen Liang)

$$P=(I-2u_{b}u_{b}^{T})\cdots(I-2u_{2}u_{2}^{T})(I-2u_{1}u_{1}^{T})$$

$$P=I-UTU^{T}=I-\begin{bmatrix}u_{1}, \dots, u_{b}\end{bmatrix}\begin{bmatrix}t_{11} & 0 & 0 \\ \vdots & \ddots & 0 \\ t_{b1} & \dots & t_{bb}\end{bmatrix}\begin{bmatrix}u_{1} \\ \vdots \\ u_{b}\end{bmatrix}$$




$$\begin{align*}
P&= I\\
	&-2u_{b}u_{b}^{T}-\dots-2u_{1}u_{1}^{T}\\
&+2
\end{align*}$$