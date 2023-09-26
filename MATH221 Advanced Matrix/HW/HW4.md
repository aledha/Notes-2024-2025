![[Pasted image 20230923122318.png]]

![[Pasted image 20230923122332.png]]
![[Pasted image 20230923122740.png|600]]


![[Pasted image 20230923122341.png]]

$$\begin{align*}
A&= LDM^{T}= MDL^{T}\\
AM^{-T}&= LD= MDL^{T}M^{-T}\\
M^{-1}AM^{-T}&= M^{-1}LD= DL^{T}M^{-T}\\
&M^{-1}LD=D(M^{-1}L)^{T}\\
\end{align*}$$
The inverse of a lower unit triangular matrix is lower unit triangular, and the product of two unit lower triangular matrix is unit lower triangular. Therefore, $M^{-1}L$ is unit lower triangular. Since
$$(M^{-1}LD)^{T}=D(M^{-1}L)^{T}=M^{-1}LD$$
$N$ must be symmetric. Since $N$ is both unit lower triangular and symmetric, it must be the identity.
$$M^{-1}L=I \quad\implies\quad L=M.$$

![[Pasted image 20230923122401.png]]

![[Pasted image 20230923122436.png]]
Firstly, let's compute the norm of $Y$,
$$\begin{align*}
\lVert Y \rVert_{F}&= \sqrt{\sum_{i,j=1}^{2n} \lvert Y_{ij} \rvert^{2}}\\
&= \sqrt{2\sum_{i,j=1}^{n}\lvert I_{ij} \rvert^{2} +\sum_{i,j=1}^{n}\lvert Z_{ij} \rvert^{2}}\\
&= \sqrt{2n+\lVert Z \rVert_{F}^{2}}.
\end{align*}$$
Let $X=Y^{-1}$, then
$$\begin{bmatrix}X_{11} & X_{12} \\ X_{21} & X_{22}\end{bmatrix}\begin{bmatrix}I & Z \\ 0 & I\end{bmatrix}=\begin{bmatrix}I & 0 \\ 0 & I\end{bmatrix}.$$
This results in the equations
$$\begin{cases}
X_{11}I+X_{12} 0=I \\
X_{21}I+X_{22}0=0 \\
X_{11}Z+X_{12}I=0 \\
X_{21}Z+X_{22}I=I
\end{cases}$$
We see that $X_{11}=I,\quad X_{21}=0$. The last two equations gives that $X_{12}=-Z$ and $X_{22}=I$. 
$$Y^{-1}=X=\begin{bmatrix}I & -Z \\ 0 & I\end{bmatrix}$$
Since we take absolute value in the Frobenius norm, 
$$\lVert Y^{-1} \rVert_{F}=\lVert Y \rVert_{F}=\sqrt{2n+\lVert Z \rVert_{F}^{2}}.$$
The condition number becomes
$$\kappa _{F}(Y)=\lVert Y \rVert_{F}\lVert Y^{-1} \rVert_{F}=2n+\lVert Z \rVert_{F}^{2}.$$

```ad-question
 Analyze the cost of recursive LU (RLU) presented in lecture, deriving and solving recurrences for A(n) = number of arithmetic operations and W(n) = number of words moved.

```
