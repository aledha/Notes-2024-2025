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
&= \begin{bmatrix}V & U\end{bmatrix}\begin{bmatrix}0 & \Sigma^{T} U^{T}\\
\Sigma V^{T}  & 0\end{bmatrix}\\
&= \begin{bmatrix}V & U\end{bmatrix} \begin{bmatrix}0 & \Sigma ^{T}\\
\Sigma  & 0\end{bmatrix}\begin{bmatrix}V^{T} & U^{T}\end{bmatrix}
\end{align*}$$

In lecture, we discussed how to solve the ridge regression problem using both a version of the normal equations, and the SVD. In practice, one may want to solve the same ridge regression problem for several values of the parameter lambda, to choose the best one. The SVD makes it quite cheap to do this, but requires an expensive SVD first. The normal equations require an additional O(n^3) work for each lambda, for Cholesky, which can be much cheaper than initially forming A^T$*$A for O(m$*$n^2) if m >> n, but it is not backward stable. Show how to use QR to solve ridge regression for an additional cost of O(n^3) per lambda. Hint: use Givens rotations to update R.