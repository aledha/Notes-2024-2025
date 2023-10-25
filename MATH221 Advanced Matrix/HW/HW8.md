Questions 4.1, 4.2, 4.3, 4.4, 4.5

![[Pasted image 20231020151030.png|800]]

$$A=\begin{bmatrix}A_{11} & A_{12} & \dots & A_{1b} \\ 0 & A_{22} & \dots & A_{2b} \\ 0 & 0  &  \ddots & \vdots \\0  & 0  &  0 &  A_{bb}\end{bmatrix},\tag{4.1}$$
where each $A_{ii}$ is square.

We have that $\text{ det}\begin{bmatrix}A & B \\ C & D\end{bmatrix}=\text{ det}(A)\text{ det}(D-CA^{-1}B)$ 
apply schur form to each block and then the whole matrix.

Splitting up $A$ in the following way,
$$A=\left[ \begin{array}{c|cc}A_{11} & A_{12} & \dots & A_{1b} \\ \hline0 & A_{22} & \dots & A_{2b} \\ \vdots & 0  &  \ddots & \vdots \\ 0 & 0  &0   &  A_{bb}\end{array}\right],$$
we can use that 
$$\begin{align*}
\text{ det}A&= \text{ det}A_{11}\cdot \text{ det}\left(\begin{bmatrix}A_{22} & \dots & A_{2b} \\  & \ddots & \vdots \\  &   & A_{bb} \end{bmatrix}- \begin{bmatrix}0 \\ \vdots \\ 0\end{bmatrix}A_{11}^{-1}\begin{bmatrix}A_{12} & \dots  & A_{1b}\end{bmatrix} \right)\\
&= \text{ det}A_{11}\cdot \text{ det}\left(\left[\begin{array}{c|cc}A_{22} & \dots & A_{2b} \\ \hline & \ddots & \vdots \\  &   & A_{bb} \end{array} \right] \right).
\end{align*}$$
Partitioning the second matrix as shown and recursing the same logic yields that
$$\text{ det}A=\prod_{i=1}^{b}\text{ det}A_{ii}$$
As $A-\lambda I$ retains the upper triangular block matrix structure, it follows that
$$\text{ det}(A-\lambda I)=\prod_{i=1}^{b}\text{ det}(A_{ii}-\lambda I),$$
where each $I$ has the same dimensions as $A_{ii}$ (which is square by assumption).

Denote the set of eigenvalues of $A_{ii}$ as $\lambda (A_{ii})$. Each of these eigenvalues solves the corresponding characteristic equation $\text{ det}(A_{ii}-\lambda I)=0$, meaning that they also solve the characteristic equation of $A$,
$$\text{ det}(A-\lambda I)=\prod_{i=1}^{b}\text{ det}(A_{ii}-\lambda I),$$
i.e. that they are also eigenvalues of $A$.

As each eigenvalue of each block $A_{ii}$ is also an eigenvalue of $A$, 
$$\bigcup_{i=1}^{b}\lambda (A_{ii}) \subseteq \lambda (A).$$
If $\lambda$ is a solution to the characteristic equation $\text{ det}(A-\lambda I)=0$, then, for at least one $i$, it must also solve $\text{ det}(A_{ii}-\lambda I)$ . As a consequence, $A$ does not have any other eigenvalues than those of $A_{ii}$, and that we have the equality
$$\lambda (A)=\bigcup_{i=1}^{b}\lambda (A_{ii}).$$

![[Pasted image 20231020151117.png|800]]
Let $A$ be upper triangular and partitioned as
$$A=\left[\begin{array} {c|cc}A_{11} & A_{12} \\ \hline0 & A_{22}\end{array} \right]$$
where $A_{11}$ is a scalar, and $A_{12}\in \mathbb{R}^{1\times (n-1)}, \quad A_{22}\in \mathbb{R}^{(n-1)\times(n-1)}$.
$$\begin{align*}
A^{*}A&= \begin{bmatrix}A_{11}^{*} & 0\\
A_{12}^{*} & A_{22}^{*}\end{bmatrix}\begin{bmatrix}A_{11} & A_{12}\\
0 & A_{22}\end{bmatrix}\\
&= \begin{bmatrix}A_{11}^{*}A_{11} & A_{11}^{*}A_{12}\\
A_{12}^{*}A_{11} & A_{12}^{*}A_{12}+A_{22}^{*}A_{22}\end{bmatrix}
\end{align*}$$
while
$$\begin{align*}
AA^{*}&= \begin{bmatrix}A_{11} & A_{12} \\ 0 & A_{22}\end{bmatrix}\begin{bmatrix}A_{11}^{*} & 0 \\ A_{12}^{*} & A_{22}^{*}\end{bmatrix}\\
&= \begin{bmatrix}A_{11}A_{11}^{*}+A_{12}A_{12}^{*} & A_{12}A_{22}^{*}\\
A_{22}A_{12}^{*} & A_{22}A_{22}^{*}\end{bmatrix}
\end{align*}$$

Since $A$ is normal, these two expressions must be equal, and each block must be equal to each other. Inpecting the first entry,
$$A_{11}A^{*}_{11}+A_{12}A_{12}^{*}=A_{11}^{*}A_{11},$$
meaning that $A_{12}A_{12}^{*}=0 \quad\implies\quad A_{12}=0$ and
$$A=\begin{bmatrix}A_{11} & 0 \\ 0 & A_{22}\end{bmatrix}.$$
Continuing the same line of logic on $A_{22}$ yields that  if $A$ is triangular and normal, it must be diagonal.

Part 2:
Supposing that $A$ is normal, we can show that Schur form is also normal,
$$\begin{align*}
TT^{*}&= Q^{*}AQQ^{*}A^{*}Q\\
&= Q^{*}AA^{*}Q\\
&= Q^{*}A^{*} AQ\\
&= Q^{*}A^{*}QQ^{*}AQ\\
&= T^{*}T
\end{align*}$$
Since $T$ is both normal and upper triangular, $T$ is also diagonal. Then the eigenvectors of $T$ are the basis unit vectors and form an orthonormal set.
$$\begin{align*}
Te_{i}&= \lambda _{i}e_{i}\\
Q^{*}AQe_{i}&= \lambda _{i}e_{i}\\
Ax_{i}&= Q \lambda _{i} Q^{*}x_{i}\\
Ax_{i}&= \lambda _{i}x_{i},
\end{align*}$$
where the eigenvectors of $A$, $x_{i}=Qe_{i}$, also form an orthonormal basis, since $Q$ is orthogonal.

![[Pasted image 20231020151127.png|800]]
$$\begin{align*}
Ax&= \lambda x\\
y^{T}A&= \mu y^{T}
\end{align*}$$
$$\begin{align*}
y^{T}Ax&= \lambda y^{T}x\\
(y^{T}A-\lambda y^{T})x&= 0\\
(\mu y^{T}-\lambda y^{T})x&= 0\\
(\mu -\lambda )y^{T}x&= 0
\end{align*}$$
Either $\mu -\lambda =0$ (i.e. the eigenvalues are distinct) or $y^{T}x=0$ and $x$ and $y$ are orthogonal.

![[Pasted image 20231020151136.png|800]]
$$\begin{align*}
f(A)&= \sum_{i=-\infty}^{\infty}a_{i}A^{i}\\
&=\dots+a_{-1}A^{-1}+ a_{0}A^{0}+a_{1}A^{1}+ \dots
\end{align*}$$
Let's compute some powers of the Schur form and see what we get,
$$\begin{align*}
(Q^{*}AQ)^{2}&= Q^{*}A^{2}Q\\
(Q^{*}AQ)^{3}&= Q^{*}A^{3}Q\\
(Q^{*}AQ)^{-1}&= Q^{*}A^{-1}Q\\
(Q^{*}AQ)^{-2}&= (Q^{*}A^{-1}Q)^{2}=Q^{*}A^{-2}Q.
\end{align*}$$
It is evident that we can write $f(T)$ as
$$\begin{align*}
f(T)&= \sum_{i=-\infty}^{\infty}a_{i}(Q^{*}AQ)^{i}\\
	&= \sum_{i=-\infty}^{\infty}a_{i}Q^{*}A^{i}Q\\
	&= Q^{*}\left(\sum_{i=-\infty}^{\infty}a_{i}A^{i} \right)Q\\
f(T)&= Q^{*}f(A)Q\\
Qf(T)Q^{*}&= f(A)
\end{align*}$$
which is what we wanted to prove.
![[Pasted image 20231020151143.png|800]]
$$\begin{align*}
(f(T))_{ii}&= \left(\sum_{j=-\infty}^{\infty}a_{j}T^{j}\right)_{ii}\\
&= \dots +(a_{-1}T^{-1})_{ii}+(a_{0}T^{0})_{ii}+ (a_{1}T^{1})_{ii}+\dots \\

\end{align*}$$
We can write $T=D(X+I)$, where $D$ is diagonal and $X$ is strictly upper triangular. Then,
$$\begin{align*}
T&= D(X+I)\\
T^{k}&= D^{k}(X+I)^{k}\\
&= D^{k}(\text{strictly upper triangular matrices} +I^{k}),\tag{1}
\end{align*}$$
where I have used that $X^{k}$ is strictly upper triangular (HW1). We see that the diagonal of $T^{k}$ is its diagonal elements to the $k$-th power, $D^{k}$.
Further, the inverse of $T$ is
$$T^{-1}=D^{-1}(X+I)^{-1}=D^{-1}(I-X+X^{2}+\dots+(-1)^{n}X^{n}).$$
We see that it's diagonal entries is $D^{-1}$, as the rest of the matrices are strictly upper triangular.
Generalising to an arbitrary inverse power,
$$T^{-k}=(T^{-1})^{k},$$
we observe that we could apply the same logic as in $(1)$, and get that the diagonal entries of $T^{-k}$ are the diagonal entries of $T^{-1}$ raised to the $k$-th power. In conclusion,
$$(T^{k})_{ii}=(T_{ii})^{k}$$
for all integers $k$, and therefore
$$\begin{align*}
(f(T))_{ii}&= \dots +(a_{-1}T^{-1})_{ii}+(a_{0}T^{0})_{ii}+ (a_{1}T^{1})_{ii}+\dots \\
(f(T))_{ii}&= \dots +a_{-1}(T_{ii})^{-1}+a_{0}(T_{ii})^{0}+ a_{1}(T_{ii})^{1}+\dots \\
(f(T))_{ii}&= f(T_{ii}),
\end{align*}$$
and since $f$ is defined at the eigenvalues of $A$, which appear in the diagonal of $T$, this is well-defined.
![[Pasted image 20231020151150.png|800]]
$$\begin{align*}
Tf(T)&= T \sum_{i=-\infty}^{\infty}a_{i}T^{i}\\
	&= \sum_{i=-\infty}^{\infty}a_{i}T^{i+1}\\
	&= \sum_{i=-\infty}^{\infty}a_{i}T^{i}T\\
&= f(T)T
\end{align*}$$

![[Pasted image 20231020151157.png|800]]
Errata: Page 188, Question 4.4, Part 4: "earlier subdiagonals" should be "earlier superdiagonals". (Yulong Dong)
We note from 4.3.2 that $f(T)$ is also upper triangular. So far, we know the diagonal elements,
$$\begin{align*}
Tf(T)&= f(T)T\\
\begin{bmatrix}T_{11} & \dots  & T_{1n}\\
0 & \ddots & \vdots \\
0 & 0 & T_{nn}\end{bmatrix}\begin{bmatrix}f(T_{11}) & * & *\\
0 & \ddots  & *\\
0 & 0 & f(T_{nn})\end{bmatrix}&= \begin{bmatrix}f(T_{11}) & * & *\\
0 & \ddots  & *\\
0 & 0 & f(T_{nn})\end{bmatrix}\begin{bmatrix}T_{11} & \dots  & T_{1n}\\
0 & \ddots & \vdots \\
0 & 0 & T_{nn}\end{bmatrix}
\end{align*}$$
The equality must holde index-wise,
$$(Tf(T))_{i,j}=\sum_{k=1}^{n}T_{i,k}(f(T))_{k,j}=\sum_{k=1}^{n}(f(T))_{ik}T_{kj}=(f(T)T)_{ij}$$
As both matrices are upper triangular, $T_{ij}=0$ and $f(T)_{ij}=0$ for $i>j$, and this equality becomes
$$\sum_{k=i}^{j}T_{ik}(f(T))_{kj}=\sum_{k=i}^{j}(f(T))_{ik}T_{kj}.$$
For notational simplicity, let $F_{ij}=(f(T))_{ij}$.
First, we can let $j=i+1$, and
$$\begin{align*}
T_{i,i}F_{i,i+1}+T_{i,i+1}F_{i+1,i+1}&= F_{i,i}T_{i,i+1}+F_{i,i+1}T_{i+1,i+1}\\
F_{i,i+1}&= T_{i,i+1}\frac{F_{ii}-F_{i+1,i+1}}{T_{i,i}-T_{i+1,i+1}}
\end{align*}$$
Note that the divisor is non-zero as the diagonal elements of $T$ are the eigenvalues of $A$, and the eigenvalues are distinct by assumption. 
The first superdiagonal of $F$ is well-defined and can be calculated from the diagonal. 
In the sum above, we can let $j=i+2$ and
$$T_{ii}$$



![[Pasted image 20231020151205.png|800]]
