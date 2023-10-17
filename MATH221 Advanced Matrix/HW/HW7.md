Questions 3.11, 3.12, 3.13, 3.14

![[Pasted image 20231015233438.png|800]]
Let 
$$A=\begin{bmatrix}U_{1} & U_{2}\end{bmatrix}\begin{bmatrix}\Sigma _{1} & 0 \\ 0 & 0\end{bmatrix}\begin{bmatrix}V_{1}  &  V_{2}\end{bmatrix}^{T}$$
$A^{+}=V_{1} \Sigma_{1} ^{-1}U_{1}^{T}$ 
$$\lVert A X -I\rVert= \left\lVert \begin{bmatrix}U_{1} & U_{2}\end{bmatrix}\begin{bmatrix}\Sigma _{1} & 0 \\ 0 & 0\end{bmatrix}\begin{bmatrix}V_{1}  &  V_{2} \end{bmatrix} \right\rVert$$

![[Pasted image 20231015233458.png|800]]


![[Pasted image 20231015233512.png|800]]
Let 
$$A=\begin{bmatrix}U_{1} & U_{2}\end{bmatrix}\begin{bmatrix}\Sigma _{1} & 0 \\ 0 & \Sigma _{2}\end{bmatrix}\begin{bmatrix}V_{1} \\ V_{2}\end{bmatrix}$$
$A^{+}=V \Sigma ^{-1}U^{T}$

$$AA^{+}A=U \Sigma V^{T}V \Sigma ^{-1}U^{T}U \Sigma V^{T}=U \Sigma V^{T}=A$$
$$A^{+}AA^{+}=V \Sigma^{-1} U^{T}U \Sigma V^{T}V \Sigma ^{-1}U^{T}$$

![[Pasted image 20231015233530.png|800]]

$$\begin{align*}
H&= \begin{bmatrix}0 & A^{T} \\ A & 0\end{bmatrix}=\begin{bmatrix}0 & V \Sigma^{T } U^{T} \\ U \Sigma V^{T} & 0\end{bmatrix}\\
&= \begin{bmatrix}V  & 0\\
0& U\end{bmatrix}\begin{bmatrix}0 & \Sigma^{T} U^{T}\\
\Sigma V^{T}  & 0\end{bmatrix}\\
&= \begin{bmatrix}V &0\\
0 &  U\end{bmatrix} \begin{bmatrix}0 & \Sigma ^{T}\\
\Sigma  & 0\end{bmatrix}\begin{bmatrix}V^{T} &0\\
0 &  U^{T}\end{bmatrix}\\
&= :C \tilde \Sigma C^{T}
\end{align*}$$
Note that $C$ is unitary, 
$$\begin{bmatrix}V & 0 \\ 0 & U\end{bmatrix}\begin{bmatrix}V^{T} & 0 \\ 0 & U^{T}\end{bmatrix}=\begin{bmatrix}I & 0 \\ 0 & I\end{bmatrix}.$$

If $C^{T}v$ is an eigenvector of $\tilde \Sigma$, then $Hv=C \tilde \Sigma (C^{T}v)=C \lambda C^{T}v=\lambda v$.
Thus, $H$ and $\tilde \Sigma$ have the same eigenvalues, while if $v$ is a an eigenvector of $H$, then $C^{T}v$ is an eigenvector of $\tilde \Sigma$.
Let's find these eigenvectors and eigenvalues.
$$\begin{bmatrix}& &     &  \sigma _{1} &   &  \\&  &   &  & \ddots \\ & &   &   &   &  \sigma _{n} \\   \sigma _{1} \\ & \ddots\\ &   &  \sigma _{n}\end{bmatrix}\begin{bmatrix}p_{1} \\ \vdots \\ p_{n} \\ q_{1} \\ \vdots \\ q_{n}\end{bmatrix}=\begin{bmatrix}\sigma _{1}q_{1} \\ \vdots \\ \sigma _{n}q_{n} \\ \sigma _{1}p_{1} \\ \vdots \\ \sigma _{n}p_{n}\end{bmatrix}$$
We see that we get an eigenvector if we choose $p,q$ such it's nonzero for all indices except for exactly one $q_{j}=\pm p_{j}$.
The $2n$ unit eigenvectors are of the form $\frac{1}{\sqrt{2}}\begin{bmatrix}e_{j} \\ \pm e_{j}\end{bmatrix}$, where $e_{j}$ denotes the $j$th canonical basis vector. The corresponding eigenvalue is $\pm \sigma _{j}$. 

Therefore, the $2n$ eigenvectors of $H$ are 
$$\begin{align*}
C \frac{1}{\sqrt{2}}\begin{bmatrix}e_{j} \\ \pm e_{j}\end{bmatrix}&=  \frac{1}{\sqrt{2}}\begin{bmatrix}V & 0 \\ 0 & U\end{bmatrix}\begin{bmatrix}e_{j} \\ \pm e_{j}\end{bmatrix}\\
&= \frac{1}{\sqrt{2}}\begin{bmatrix}v_{j}\\
\pm u_{j}\end{bmatrix},
\end{align*}$$
with corresponding eigenvalues $\sigma _{j}$.

For rectangular $A \in \mathbb{R}^{m\times n}$, we have that 


```ad-question
In lecture, we discussed how to solve the ridge regression problem using both a version of the normal equations, and the SVD. In practice, one may want to solve the same ridge regression problem for several values of the parameter lambda, to choose the best one. The SVD makes it quite cheap to do this, but requires an expensive SVD first. The normal equations require an additional O(n^3) work for each lambda, for Cholesky, which can be much cheaper than initially forming A^T$*$A for O(m$*$n^2) if m >> n, but it is not backward stable. Show how to use QR to solve ridge regression for an additional cost of O(n^3) per lambda. Hint: use Givens rotations to update R. 

```
