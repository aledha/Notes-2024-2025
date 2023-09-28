![[Pasted image 20230923122318.png]]
Factorizing A into $PLU$ uses $\frac{2}{3}n^{3}+\mathcal{O}(n^{2})$ flops, while both forward and back substitution for matrices uses $n^{3}$ flops (HW3). The first algorithm requires $\frac{5}{3}n^{3}+\mathcal{O}(n^{2})$ flops.

Computing the inverse using Gaussian elimination requires $2n^{3}+\mathcal{O}(n^{2})$, while standard matrix multiplication requires $n^{2}(2n-1)$, resulting in $4n^{3}+\mathcal{O}(n^{2})$ flops.

We see that the the first algorithm requires asymptotically fewer flops than the second.

![[Pasted image 20230923122332.png]]
![[Pasted image 20230923122740.png|600]]
1. Denote $\alpha(i)$ such that $P_{i,\alpha (i)}=1$, which is the only nonzero element in the $i$-th row. Then,
$$(PX)_{ij}=\sum_{k=1}^{n}P_{ik}X_{kj}=P_{i,\alpha (i)}X_{\alpha (i),j}=X_{\alpha(i),j},$$
which happens to each $i$. In other words, row number $i$ gets permuted to row $\alpha (i)$. If $\alpha (i)≠i$, then another row must get permuted to row $i$, for example $\alpha (k)=i$. This can be seen by the fact that in the permutation matrix, each row and column has exactly one nonzero entry. $PX$ is the same as $X$ but with its rows permuted.

$XP$ is very similar. Define $\beta (i)$ such that $P_{\beta (j),j}=1$ and all other entries in column $j$ be zero. Then,
$$(XP)_{ij}=\sum_{k=1}^{n}X_{i,k}P_{k,j}=X_{i,\beta(j)}$$
Column number $j$ gets permuted to column number $\beta (j)$. With the same reasoning as before, $XP$ is the same as $X$ but with its columns permuted.

2. Define $\alpha (i)$ as the previous proof.
$$(PP^{T})_{ij}=\sum_{k=1}^{n}P_{ik}P_{jk}$$
The first factor is zero if $k≠\alpha (i)$, while the second factor is zero if $k≠\alpha (j)$. Therefore,
$$\begin{align*}
(PP^{T})_{ij}&= \begin{cases}
1  & \quad\text{for }\alpha (i)=\alpha (j), \\
0  & \quad\text{else},
\end{cases}\\
&= \begin{cases}
1  & \quad\text{for }i=j,\\
0 & \quad\text{else},
\end{cases}\\
&= \delta _{ij}=I_{ij}.
\end{align*}$$
In conclusion,
$$PP^{T}=I \quad\Leftrightarrow\quad P^{T}=P^{-1}.$$

3. Since $P$ is orthogonal,
$$\begin{align*}
 PP^{T}&=I\\
\text{ det}(PP^{T})&= \text{ det}(I)\\
 \text{ det}(P)\text{ det}(P^{T})&=1\\
\text{ det}(P)^{2}&= 1\\
\text{ det}(P)&= \pm 1
\end{align*}$$
where I have used the fact that $\text{ det}(AB)=\text{ det}(A)\text{ det}(B)$ and $\text{ det}(A^{T})=\text{ det}(A)$.

4. By the definition, $P_{2}$ is the identity matrix with its rows permuted. As showed in 1), $P_{1}P_{2}$ is the same as $P_{2}$ with its rows permuted. So $P_{1}P_{2}$ is still the identity matrix with its columns permuted, and is therefore a permutation matrix.


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

![[Pasted image 20230926170809.png|600]]
For each recursion, we have the following contributions:
	Line 7: $A(n,m/2)$
	Line 8: $(m/2)^3$ 
	Line 9: $(n-m/2)m/2$ from the subtraction, $\left(n-\frac{m}{2}\right)\frac{m}{2}\cdot (\frac{m}{2}+ (\frac{m}{2}-1))$ from standard matrix multiplication
		Total for line 9 is $((n-m/2)m/2)(1+m/2+m/2-1)=\frac{nm^{2}}{2}- \frac{m^{3}}{4}$  
	Line 10: $A(n-m/2,m/2)$

Combining all of these,
$$\begin{align*}
A(n,m)&= A\left(n,\frac{m}{2}\right)+A\left(n- \frac{m}{2},\frac{m}{2}\right) +\frac{m^{3}}{8}+\frac{nm^{2}}{2}- \frac{m^{3}}{4}\\
A(n,m)&=A\left(n, \frac{m}{2}\right)+A\left(n- \frac{m}{2}, \frac{m}{2}\right)+\frac{nm^{2}}{2} -\frac{m^{3}}{8}\\
A(n,m)&=A\left(n, \frac{m}{2}\right)+A\left(n- \frac{m}{2}, \frac{m}{2}\right)+m^{2}\left(\frac{n}{2} -\frac{m}{8}\right)\\
\end{align*}$$

Let's assume that we start with $m=n$. In the recurrence tree, for a given depth $i$, we have $2^{i}$ calls. Each of them has the same argument for $m= \frac{m}{2i}$, while they have different arguments for $n \in \{ \frac{m}{2^{i}},2 \frac{m}{2^{i}},3\frac{m}{2^{i}},\dots,m \}$.

Thus, if we assume that $n=m=2^{k}$
$$A(n)= \sum_{i=1}^{k} \sum_{j=1}^{2^{i}}A^{*}\left(j \frac{n}{2^{i}}, \frac{n}{2^{i}}\right),$$
Where $A^{*}$ is $A(n,m)$ without the recurrence terms, i.e., $A^{*}(n,m)= m^{2}\left( \frac{n}{2}- \frac{m}{8}\right)$. Then
$$\begin{align*}
A(n)&= \sum_{i=1}^{\text{log}_{2}n}\sum_{j=1}^{2^{i}} \left( \frac{n}{2^{i}}\right)^{2} \left(\frac{1}{2} \frac{j n}{2^{i}}-  \frac{1}{8} \frac{n}{2^{i}}\right)\\
&= \sum_{i=1}^{\text{log}_{2}n} \left(\frac{n}{2^{i}} \right)^{3}\sum_{j=1}^{2^{i}} \left(\frac{j}{2}- \frac{1}{8} \right)\\
&= \sum_{i=1}^{\text{log}_{2}n} \left(\frac{n}{2^{i}} \right)^{3} \left[\frac{1}{4}2^{i}\left(2^{i}+1 \right)- \frac{1}{8}2^{i} \right]\\
	&= \sum_{i=1}^{\text{log}_{2}n} \frac{n^{3}}{2^{2i}} \left(\frac{1}{4} 2^{i}+ \frac{1}{8} \right)\\
&= \frac{n^{3}}{4}\sum_{i=1}^{\text{log}_{2}n}(2^{-i}+ \frac{1}{2}2^{-2i})\\
&= \frac{n^{3}}{4} \cdot \left[2^{-1} \frac{1- 2^{-\text{log}_{2}n}}{1-2^{-1}}+ \frac{1}{2}2^{-2} \frac{1-2^{-2\text{log}_{2}n}}{1-2^{-2}} \right]\\
&= \frac{n^{3}}{4} \cdot \left[1- n^{-1}+   \frac{5}{3}- \frac{5}{3}n^{-2} \right]\\
&= \frac{2n^{3}}{3}+\mathcal{O}(n^{2})
\end{align*}$$


