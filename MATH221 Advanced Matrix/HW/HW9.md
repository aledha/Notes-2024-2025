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
With this in mind, let's take a look at the equation for $c_{m1}$,
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
Let's compute for $c_{mj}$,
$$ $$


![[Pasted image 20231031150506.png|800]]

![[Pasted image 20231031150520.png|800]]

![[Pasted image 20231031150533.png|800]]

![[Pasted image 20231031150545.png|800]]