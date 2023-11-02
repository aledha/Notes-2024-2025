Alexander Hatle
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
<div style="page-break-after: always;"></div>

![[Pasted image 20231031150520.png|800]]
$$\begin{align*}
&\quad \begin{array}cm &n\end{array}\\
\begin{array}cm\\ n\end{array}&\begin{bmatrix}AB & 0 \\ B & 0\end{bmatrix}
\end{align*}$$
Definition of similar:
$A$ and $B$ are similar if there exists invertible $P$ such that $PAP^{-1}=B$.

In HW4, Q2.12, I showed that if $Y=\begin{bmatrix}I & Z \\ 0 & I\end{bmatrix}$, then $Y^{-1}=\begin{bmatrix}I & -Z  \\ 0 & I\end{bmatrix}$.
Let's try to apply this structure and see if we can choose a nice $Z$.
$$\begin{align*}
Y\begin{bmatrix}AB & 0 \\ B & 0\end{bmatrix}Y^{-1}&= \begin{bmatrix}I & Z\\
0 & I\end{bmatrix}\begin{bmatrix}AB & 0 \\ B & 0\end{bmatrix}\begin{bmatrix}I & -Z\\
0 & I\end{bmatrix}\\
&= \begin{bmatrix}AB+ZB & 0\\
B & 0\end{bmatrix}\begin{bmatrix}I & -Z \\
0 & I\end{bmatrix}\\
&= \begin{bmatrix}AB+ZB & (AB+ZB)(-Z)\\
B & B(-Z)\end{bmatrix}
\end{align*}$$
If we choose $Z=-A$, then
$$\begin{align*}
Y\begin{bmatrix}AB & 0 \\ B & 0\end{bmatrix}Y^{-1}&=\begin{bmatrix}AB-AB & (AB-AB)A\\
B & BA\end{bmatrix}\\
&= \begin{bmatrix}0 & 0\\
B & BA\end{bmatrix}
\end{align*}$$
Then 
$$\begin{bmatrix}AB & 0 \\ B & 0\end{bmatrix}\quad \text{and}\quad \begin{bmatrix}0 & 0 \\ B & BA\end{bmatrix}$$
are similar and share eigenvalues. 
In HW8, Q4.1, I showed that the set of eigenvalues of a block triangular matrix is the same as the union of the sets of eigenvalues of the diagonal entries. (This was shown for an upper block triangular matrix, but it is analogous to lower block triangular.)
Then  $$\begin{align*}
\lambda \left( \begin{bmatrix}AB & 0 \\ B & 0\end{bmatrix}\right)&=  \lambda \left( \begin{bmatrix}0 & 0\\
B & BA\end{bmatrix}\right)\\
\lambda (AB)\cup \lambda (0)&= \lambda (0) \cup \lambda (BA)
\end{align*}$$ i.e., $AB$ and $BA$ share nonzero eigenvalues.
<div style="page-break-after: always;"></div>

![[Pasted image 20231031150533.png|800]]

Let $\tilde x=\alpha x$ and $\tilde y=\beta y$ be scalar multiplies of the right and left eigenvectors, and let $\tilde P=\tilde x \tilde y^{*}/(\tilde y^{*}\tilde x)$.
Then
$$\begin{align*}
\tilde P&=  \frac{(\alpha x)(\beta y)^{*}}{(\beta y)^{*}(\alpha x)}\\
&= \frac{\alpha \overline{\beta }}{\overline{\beta }\alpha } \frac{xy^{*}}{y^{*}x}\\
&= P,
\end{align*}$$
and such each choice of scalar multiplies of $x$ and $y$ leads to the same spectral projection $P$, i.e., the spectral projection corresponding to $\lambda$ is uniquely defined.

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
The condition number of $\lambda$ is defined as $\frac{1}{\lvert y^{*}x \rvert}$, where $x$ and $y$ are normalised right and left eigenvectors of $\lambda$.
From HW2, we have that
$$\begin{align*}
\lVert P \rVert_{2}&=  \sqrt{\lambda _{\max }(P^{*}P)}
\end{align*}$$
Let's compute $P^{*}P$,
$$\begin{align*}
P^{*}P&= \left(\frac{xy^{*}}{y^{*}x} \right)^{*}\frac{xy^{*}}{y^{*}x}\\
&= \frac{1}{ (\overline{y^{*}x})(y^{*}x) }yx^{*}xy^{*}\\
&= \frac{1}{\lvert y^{*}x \rvert^{2}}yy^{*}.
\end{align*}$$
This matrix is rank 1 and has therefore a 0 eigenvalue with multiplicity $n-1$, and the only nonzero eigenvalue with corresponding eigenvector $y$ is
$$\begin{align*}
P^{*}Py&= \frac{1}{\lvert y^{*}x \rvert^{2}}yy^{*}y\\
&= \frac{1}{\lvert y^{*}x \rvert^{2}}y,
\end{align*}$$
The largest eigenvalue of $P^{*}P$ is $\frac{1}{\lvert y^{*}x \rvert^{2}}$, and such
$$\lVert P \rVert_{2}=\sqrt{\frac{1}{\lvert y^{*}x \rvert^{2}}}= \frac{1}{\lvert y^{*}x \rvert},$$
which is the condition number of $\lambda$.

<div style="page-break-after: always;"></div>

![[Pasted image 20231031150545.png|800]]
We can let $E=\mu I-A$, then
$$\begin{align*}
(A+E)x&= (A+\mu I-A)x\\
&= \mu x 
\end{align*}$$
And
$$\begin{align*}
\lVert r \rVert_{2}&= \lVert Ex \rVert_{2}\\
&= \lVert Ex \rVert_{F}\\
&\le \lVert E \rVert_{F}\lVert x \rVert_{2}	\\
&\le \lVert E \rVert_{F} 
\end{align*}$$
I couldn't figure out how to get equality though.