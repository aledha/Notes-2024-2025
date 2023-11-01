Questions 4.6, 4.8, 4.11, 4.13

![[Pasted image 20231031150447.png|800]]
We let 
$$A= QTQ^{*},\quad B= UWU^{*}$$
be the Schur forms of $A$ and $B$. $T$ and $W$ are upper triangular. 
Then,
$$\begin{align*}
AX-XB&= C\\
QTQ^{*}X-XUWU^{*}&= C\\
TQ^{*}X-Q^{*}XUWU^{*}&= Q^{*}C\\
TQ^{*}XU-Q^{*}XUW&= Q^{*}CU\\
A'Y-YB'&= C'
\end{align*}$$
where $A'=T,\quad B'=W,\quad C'=Q^{*}CU$ and $Y=Q^{*}XU$.
$A'$ and $B'$ are upper triangular.

![[Pasted image 20231031150456.png|800]]
We let $u_{j}$ be the $j$-th column vector of $Y$ and $v_{j}$ be the $j$-th row vector. Let $a_{j}$ be the row vectors of $A'$ and $b_{j}$ be the column vectors of $B'$. 
$$\begin{align*}
\begin{bmatrix}a_{1}^{T} \\ \vdots  \\ a_{m}^{T}\end{bmatrix}\begin{bmatrix}u_{1} & \dots  & u_{n}\end{bmatrix}-\begin{bmatrix}v_{1}^{T} \\ \vdots  \\ v_{m}^{T}\end{bmatrix}\begin{bmatrix}b_{1} & \dots  & b_{n}\end{bmatrix}&= \begin{bmatrix}c_{11} & \dots  & c_{1n} \\ \vdots  &   & \vdots  \\ c_{m1} & \dots  & c_{mn} \end{bmatrix}\\
a_{i}^{T}u_{j}-v_{i}^{T}b_{j}&= c_{ij}
\end{align*} $$
Since $A'$ and $B'$ upper triangular, $a_{i}^{T}=[0  \dots  0 \quad a_{ii}\dots a_{im}]$ and $b_{j}^{T}=[  b_{1j}\dots b_{jj}\quad0  \dots  0]$.
With this in mind, let's take a look at the equation for $c_{m1}$, in order to compute $y_{m1}$
$$\begin{align*}
a_{m}^{T}u_{1}-v_{m}^{T}b_{1}&= c_{m1}\\
\begin{bmatrix}0 & \dots  & 0 & a_{mm}\end{bmatrix}\begin{bmatrix}y_{11}\\
 \vdots \\
y_{m1}\end{bmatrix}-\begin{bmatrix}y_{m1} & \dots  & y_{mn}\end{bmatrix}\begin{bmatrix}b_{11}\\ 0\\
\vdots \\
0\end{bmatrix}&= c_{m1}\\
(a_{mm}-b_{11})y_{m1}&= c_{m1}\\
y_{m1}&= \frac{c_{m1}}{a_{mm}-b_{11}}.
\end{align*}$$
Let's find an equation for $y_{mj}$, 
$$\begin{align*}
a_{m}^{T}u_{j}-v_{m}b_{j}&= c_{mj}\\
a_{mm}y_{mj}-\sum_{i=1}^{j}b_{1i}y_{mi}&= c_{mj}\\
y_{mj}&= \frac{1}{a_{mm}-b_{11}}\left(c_{mj}+\sum_{i=1}^{j-1}b_{1i}y_{mi} \right).
\end{align*}$$
Now, on to a general $y_{ij}$,

$$\begin{align*}
a^{T}_{i}u_{j}-v_{i}b_{j}&= c_{ij}\\
\sum_{k=i}^{m}a_{ik}y_{kj}-\sum_{k=1}^{j}y_{ik} b_{kj}&= c_{ij}\\
y_{ij}&= \frac{1}{a_{ii}-b_{jj}}\left(c_{ij}-\sum_{k=i+1}^{m}a_{ik}y_{kj}+\sum_{k=1}^{j-1}y_{ik}b_{kj} \right)
\end{align*}$$
We see that each computation of $y_{ij}$ requires all indices below ($y_{kj},\text{ }k>i$) and indices to the left ($y_{ik},\text{ }k<j$). 
We can therefore first compute the bottom left index $y_{m1}$, then the bottom row $y_{mk}$, then the rows above in the same fashion.

We can guarantee that the system of equations is nonsingular if $A$ and $B$ do not share any eigenvalues. This is because we have $\frac{1}{a_{ii}-b_{jj}}$ in the equation above and the diagonal entries of $A'$ and $B'$ are the eigenvalues of $A$ and $B$, respectively.

![[Pasted image 20231031150506.png|800]]
We have that, as $Q$ and $U$ are orthogonal,
$$\begin{align*}
Y&= Q^{*}XU\\
QY&= XU\\
X&= QYU^{*}.
\end{align*}$$

![[Pasted image 20231031150520.png|800]]
$$\begin{align*}
&\quad \begin{array}cm &n\end{array}\\
\begin{array}cm\\ n\end{array}&\begin{bmatrix}AB & 0 \\ B & 0\end{bmatrix}
\end{align*}$$
Let
$$A= QTQ^{*},\quad B= UWU^{*}$$

$$\begin{align*}
\begin{bmatrix}(AB)^{-1} & 0 \\ 0 & I\end{bmatrix}\begin{bmatrix}AB & 0 \\ B & 0\end{bmatrix}\begin{bmatrix}AB & 0 \\ 0 & I\end{bmatrix}&= \begin{bmatrix}I & 0\\
B & 0\end{bmatrix}\begin{bmatrix}AB & 0 \\ 0 & I\end{bmatrix}
\end{align*}$$
![[Pasted image 20231031150533.png|800]]

![[Pasted image 20231031213959.png|800]]
$$\begin{align*}
P^{2}&= \frac{1}{(y^{*}x)^{\cancel2}}x\cancel{y^{*}x}y^{*}\\
&= \frac{1}{y^{*}x}xy^{*}\\
&= P
\end{align*}$$

![[Pasted image 20231031214021.png|800]]
$$\begin{align*}
AP&= A \frac{xy^{*}}{y^{*}x}\\
&= (Ax) \frac{y^{*}}{y^{*}x}\\
&= \lambda  \frac{xy^{*}}{y^*x}\\
&= \lambda P\\
&= \frac{x(y^{*}\lambda )}{y^{*}x}\\
&= \frac{xy^{*}}{y^{*}x}A\\
&= PA
\end{align*}$$


![[Pasted image 20231031214032.png|800]]
$$\lVert P \rVert_{2}= \max_{\lVert x \rVert_{2}=1}\lVert Px \rVert$$

![[Pasted image 20231031150545.png|800]]
$r=Ax-\mu x$.

$$\begin{align*}
(A+E)x&= \mu x\\
Ex&= \mu x-Ax\\
Ex &= -r\\
	\lVert Ex \rVert_{F} &= \lVert r \rVert_{F}=\lVert r \rVert_{2}\\
	\lVert Ex \rVert_{F}&\le \lVert E \rVert \lVert x \rVert\\
\lVert Ex \rVert_{F}&\le \lVert E \rVert_{F}\\
\lVert r \rVert_{2}&\le \lVert E \rVert_{F}
\end{align*}$$