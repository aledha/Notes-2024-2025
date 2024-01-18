Alexander Hatle
![[Pasted image 20230915180413.png]]
Suppose that
$$\begin{align*}
(A+uv^{T})x&= y\\
Ax&= y-uv^{T}x \\
x&= A^{-1}y-A^{-1}u \underbrace{v^{T}x}_{=:z}
\end{align*}$$
$z$ is a scalar, and solving for $z$ yields
$$\begin{align*}
z&=  v^{T}x=v^{T}A^{-1}y-v^{T}A^{-1}uz\\
(1+v^{T}A^{-1}u)z&= v^{T}A^{-1}y\\
z&= \frac{v^{T}A^{-1}y}{1+v^{T}A^{-1}u}
\end{align*}$$

$$\begin{align*}
x&= A^{-1}y-A^{-1}u \frac{v^{T}A^{-1}y}{1+v^T A^{-1}u}\\
x&= \left(A^{-1}-\frac{A^{-1}uv^{T}A^{-1}}{1+v^{T}A^{-1}u}\right)y
\end{align*}$$
Inverting the first expression gives that $x=(A+uv^{T})^{-1}y$, which implies that
$$(A+uv^{T})^{-1}=A^{-1}-\frac{A^{-1}uv^{T}A^{-1}}{1+v^{T}A^{-1}u}.$$


Sherman-Morrison-Woodbury:
$$(A+UV^{T})^{-1}=A^{-1}-A^{-1}UT^{-1}V^{T}A^{-1},$$
where $T=I+V^{T}A^{-1}U$.

$$\begin{align*}
(I+V^{T}A^{-1}U)x&≠0 \quad\text{for }x≠0\\
x&≠-V^{T}A^{-1}Ux
\end{align*}$$

$$\begin{align*}
\text{ det}(A+VU^{T})&=\text{ det}(A(I+A^{-1}VU^{T}))\\
&= \text{ det}(A) \cdot \text{ det}(I+A^{-1}VU^{T})≠0
\end{align*}$$

A matrix A is the inverse of a matrix B if and only if $AB=BA=I$.
So we want to show that this expression
$$\begin{align*}
&(A^{-1}-A^{-1}UT^{-1}V^{T}A^{-1})(A+UV^{T})\\
&=  A^{-1}A+A^{-1}UV^{T}\\
&-A^{-1}UT^{-1}V^{T}A^{-1}A-A^{-1}UT^{-1}V^{T}A^{-1}UV^{T}
\end{align*}$$
equals the identity matrix, or equivalently (since $A^{-1}A=I$)
$$\begin{align*}
A^{-1}UV^{T}-A^{-1}UT^{-1}V^{T}A^{-1}A-A^{-1}UT^{-1}V^{T}A^{-1}UV^{T}&= 0\\
A^{-1}UV^{T}-A^{-1}UT^{-1}V^{T}-A^{-1}UT^{-1}V^{T}A^{-1}UV^{T}&= 0\\
A^{-1}U(V^{T}-T^{-1}V^{T}-T^{-1}V^{T}A^{-1}UV^{T})&= 0\\
V^{T}-T^{-1}V^{T}-T^{-1}V^{T}A^{-1}UV^{T}&= 0
\end{align*}$$
$$\begin{align*}
V^{T}&= T^{-1}V^T(I+A^{-1}UV^{T})\\
TV^{T}&= V^{T}(I+A^{-1}UV^{T})\\
(I+V^{T}A^{-1}U)V^{T}&= V^{T}(I+A^{-1}UV^{T})\\
V^{T}+V^{T}A^{-1}UV^{T}&= V^{T}+V^{T}A^{-1}UV^{T}\\
V^{T}&= V^{T}
\end{align*}$$
Now we need to show the other side, that
$$\begin{align*}
(A+UV^{T})(A^{-1}-A^{-1}UT^{-1}V^{T}A^{-1})&= I\\
AA^{-1}-AA^{-1}UT^{-1}V^{T}A^{-1}\\
+UV^{T}A^{-1}-UV^{T}A^{-1}UT^{-1}V^{T}A^{-1}&= I\\
-UT^{-1}V^{T}A^{-1}+UV^{T}A^{-1}-UV^{T} A^{-1}UT^{-1}V^{T}A^{-1}&= 0\\
(U-UT^{-1}-UV^{T}A^{-1}UT^{-1})V^{T}A^{-1}&= 0\\
U-UT^{-1}-UV^{T}A^{-1}UT^{-1}&= 0
\end{align*}$$
$$\begin{align*}
U&= (U+UV^{T}A^{-1}U)T^{-1}\\
UT&= U+UV^{T}A^{-1}U\\
U(I+V^{T}A^{-1}U)&= U+UV^{T}A^{-1}U\\
U &= U
\end{align*}$$
Now we have shown both sides, that
$$\begin{align*}
(A^{-1}-A^{-1}UT^{-1}V^{T}A^{-1})(A+UV^{T})&= \\
(A+UV^{T})(A^{-1}-A^{-1}UT^{-1}V^{T}A^{-1})&=  I,
\end{align*}$$
which implies the Sherman-Morrison-Woodbury formula: 
$$(A+UV^{T})^{-1}=A^{-1}-A^{-1}UT^{-1}V^{T}A^{-1},$$
where $T=I+V^{T}A^{-1}U$.

If $A+UV^{T}$ is nonsingular, then $T$ must be nonsingular, since it is used in the above formula.

<div style="page-break-after: always;"></div>


![[Pasted image 20230915180432.png]]
From the list of errata:
	Page 95, question 2.13, parts 2 and 3: The intent is to suppose that you have already done Gaussian elimination on A to get its L and U factors, so that solving Ax=b is fast (costs just O(n^2)), and then to exploit this to solve By=c in O(n^2), rather than O(n^3), which is what Gaussian elimination on B would cost. (Matt Podolsky)

Suppose that we have the LU factorisation of $A$. We want to build a fast solver for $By=c,$ where $B=A+uv^{T}=LU+uv^{T}$.

$$\begin{align*}
(A+uv^{T})y&= c\\
y&= (A+uv^{T})^{-1}c
\end{align*}$$
We can use the Sherman-Morrison formula:
$$\begin{align*}
y&= \left(A^{-1}-\frac{A^{-1}uv^{T}A^{-1}}{1+v^{T}A^{-1}u}\right)c\\
y&= A^{-1}c-\frac{A^{-1}uv^{T}A^{-1}c}{1+v^{T}A^{-1}u}
\end{align*}$$
We can denote $Ad=c \text{ and }Ae=u$, then our solver can be built as
1. Solve $Ad=c$   ($\mathcal{O}(n^{2})$ operations)
2. Solve $Ae=u$   ($\mathcal{O}(n^{2})$ operations)
3. Compute $y=d-\frac{ev^{T}d}{1+v^{T}e}$ 

The third step is just several sequential $\mathcal{O}(n^{2})$ operations.

<div style="page-break-after: always;"></div>

# Solving $LX=B$
Where $L \in \mathbb{R}^{n \times n}$ is nonsingular and lower triangular, $B \in \mathbb{R}^{n \times n}$, and $X \in \mathbb{R}^{n \times n}$ is unknown.
```ad-question
Write down the simplest algorithm you can, and count the flops.

```

This is my idea:
for $j=1$ to $n$
	$x_{1j}= \frac{b_{1j}}{l_{11}}$
	for $i=2$ to $n$:
		$x_{ij}= \frac{b_{ij}- \sum_{k=1}^{i-1}l_{ik}x_{kj} }{l_{ii}}$

In the sum we have $i-1$ multiplications and $i-2$ additions. After the sum we have one additional addition and a division. So the line in the second for loop as $i-1+i-2+1+1=2i-1$ flops. The second for-loop has therefore $\sum_{i=2}^{n}2i-1=n^{2}-1$ flops. 

Accounting for the first for-loop and the division, he total number of flops is $$n(1+n^{2}-1)=n^{3}.$$
<div style="page-break-after: always;"></div>

```ad-question
Analogous to the blocked matrix-multiplication algorithm presented in class, write down a blocked version of this algorithm, and analyze the number of words moved; can you make it move as few words as matrix-multiply (in the Big-Oh sense)?

```
As the blocked matrix-multiply algorithm, divide L, X and B into $b \times b$ sized blocks.
```matlab
for j=1:n/b do
	for i=1:n/b do
		S = B[i, j]
		for k=1:i-1 do
			Read X[k,j] into cache
			Read L[i, k] into cache 
			S = S - L[i,k] * X[k,j]
		end for
		Read L[i, i] into cache
		Read B[i,j] into cache
		Solve L[i, i] * X[i,j] = S 
		Write X[i,j] into main memory
	end for
end for
```
Where line 11 solves the system with the algorithm described in the last question.

Number of words moved:
* Reading X and L: $$\frac{n}{b} \cdot \sum_{i=1}^{{\frac{n}{b}}-1}ib^{2}=nb \cdot \frac{\left(\frac{n}{b}-1\right) \frac{n}{b}}{2}=\frac{n^{2}( \frac{n}{b}-1)}{2}=\frac{n^{3}}{2b}- \frac{n^{2}}{2}$$
* Reading $L[i,i]$ and B: $\left(\frac{n}{b} \right)^{2} \cdot b^{2}=n^{2}$ words moved.
* Writing X: $\left(\frac{n}{b}\right)^{2} \cdot b^{2}=n^{2}$ words moved

Total words moved is
$$2 \cdot \left(\frac{n^{3}}{2b}- \frac{n^{2}}{2} \right)+3n^{2}= \frac{n^{3}}{b}+2n^{2}.$$
We can minimise this by maximising $b$. Calling the cache size for $M$, we cannot set $b$ higher than $2b^{2}=M \quad\implies\quad b=\sqrt{\frac{M}{2}}$. Then, in the Big-Oh sense, this algorithm moves
$$\mathcal{O}\left(\frac{n^{3}}{\sqrt{M}}\right)$$
words, which is the same as matrix multiply.

<div style="page-break-after: always;"></div>

```ad-question
Does it satisfy the same backward error analysis as the simple algorithm (as in Q. 1.11)?

```

The pseudocode above does the same operations as the following algorithm
for $j=1$ to $n$
	$x_{1j}= \frac{b_{1j}}{l_{11}}$
	for $i=2$ to $n$
		$x_{ij}= \frac{b_{ij}- \sum_{k=1}^{i-1}l_{ik}x_{kj} }{l_{ii}}$

The computed solution is
$$\begin{align*}
\hat x_{ij}&=  \text{fl}\left(\frac{b_{ij}-\sum_{k=1}^{i-1}l_{ik}x_{kj}}{l_{ii}}\right) \\
&= \frac{\left(b_{ij}-\sum_{k=1}^{i-1}l_{ik}x_{kj}(1+\delta _{ijk})\right)(1+\delta' _{ij})}{l_{ii}}(1+\delta _{ij})\\
&\text{where }\lvert \delta _{ijk} \rvert,\lvert \delta '_{ij} \rvert,\lvert \delta _{ij} \rvert<\epsilon  \\
&= \frac{b_{ij}-\sum_{k=1}^{i-1}\hat l_{ik}x_{kj} }{\hat l_{ii}},
\end{align*}$$
where
$$\begin{align*}
	\hat l_{ik}&= l_{ik}(1+\delta _{ijk})=l_{ik}+\delta l_{ik} \quad\text{for }\lvert \delta l_{ik} \rvert<n \epsilon \\
\hat l_{ii}&= \frac{l_{ii}}{(1+ \delta '_{ij})(1+ \delta _{ij})}=l_{ii}+\delta l_{ii} \quad\text{for }\lvert \delta l_{ii} \rvert<n \epsilon 
\end{align*}$$
Then,
$$(L+\delta L)\hat X=B,$$
which satisfies the same backward error as the simple algorithm.


<div style="page-break-after: always;"></div>

```ad-question
Analogous to the recursive matrix-multiplication algorithm presented in class, write down a recursive version of this algorithm, and analyze the number of words moved; can you make it move as few words as matrix-multiply (in the Big-Oh sense)?

```

We divide each matrix into four submatrices,
$$L=\begin{bmatrix}L_{11} & 0 \\ L_{21} & L_{22}\end{bmatrix},\quad X=\begin{bmatrix}X_{11} & X_{12} \\ X_{21} & X_{22}\end{bmatrix}, \quad B=\begin{bmatrix}B_{11} & B_{12} \\ B_{21} & B_{22}\end{bmatrix}.$$
```matlab
def solve(L, B, n):
	if n=1:
		return B / L
	else:
		X_11 = solve(L_11, B_11, n/2)
		X_12 = solve(L_11, B_12, n/2)
		X_21 = solve(L_22, B_21 - L_21 * X_11, n/2)
		X_22 = solve(L_22, B_22 - L_21 * X_12, n/2)
		return X
```
Here, * denotes matrix-multiply. The number of words moved is
$$W(n)=4 \cdot W\left(\frac{n}{2}\right)+11\left(\frac{n}{2}\right)^{2}$$
11 comes from that we do not need to store to upper right zero matrix of L. The base case is when all remaining submatrices fit in the cache, i.e. when
$$\begin{align*}
W(b)=11 \left(\frac{b}{2} \right)^{2}&\le  M\\
b &\le \sqrt{\frac{4}{11}M}
\end{align*}$$
We assume that $n$ can be written as $n=2^{m}$. The recurrence expression can then be rewritten as
$$\begin{align*}
w(m)&= 4\cdot w(m-1)+11 \cdot \left(\frac{2^{m}}{2}\right)^{2}\\
w(m)&= 4w(m-1)+ \frac{11}{4}2^{2m}
\end{align*}$$
Divide both sides by $4^{m}$ and call $v(m)=w(m)/4^{m}$.
$$\begin{align*}
v(m)&= \frac{w(m)}{4^{m}}=  \frac{4w(m-1)}{4^{m}}+ \frac{11}{4} \frac{2^{2m}}{4^{m}}\\
v(m)&= v(m-1)+ \frac{11}{4}
\end{align*}$$
Let the base case be $m_{0}=\text{ log}_{2}\sqrt{\frac{4}{11}M}$. Then,
$$v(m_{0})=\frac{w(m_{0})}{4^{m_{0}}}=\frac{M}{4^{\text{ log}_{2}\sqrt{4M/11}}}= \frac{11}{4}$$
$$v(m)=\sum_{m_{0}}^{m} \frac{11}{4}=\left(m-\text{ log}_{2}\sqrt{\frac{4}{11}M}\right) \frac{11}{4}$$
$$\begin{align*}
W(n)&= w(\text{log}_{2}n)=4^{\text{log}_{2}n}v(\text{log}_{2}n)\\
&=\frac{11}{4} n^{2}\left(\text{log}_{2}n-\text{log}_{2} \sqrt{\frac{4}{11}M}\right)\\
&= \frac{11}{4}n^{2}\text{log}_{2}\left(\frac{n}{\sqrt{4M/11}}\right),
\end{align*}$$
which surely must be wrong.