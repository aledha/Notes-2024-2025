![[Pasted image 20231009094318.png|800]]


![[Pasted image 20231009120333.png|800]]
![[Pasted image 20231009094350.png|800]]
From this formulation, we can equivalently write up the equations
$$\begin{align*}
r+Ax&= b\\
A^{T}r&= 0
\end{align*}$$
Since $Ax-b=-r$,
$$A^{T}(Ax-b)=0$$


![[Pasted image 20231009094407.png|800]]

![[Pasted image 20231009094421.png|800]]

![[Pasted image 20231009094446.png|800]]

![[Pasted image 20231009094510.png|800]]

![[Pasted image 20231009094533.png|800]]

![[Pasted image 20231009094546.png|800]]
$$P=(I-2u_{b}u_{b}^{T})\cdots(I-2u_{2}u_{2}^{T})(I-2u_{1}u_{1}^{T})$$

$$P=I-UTU^{T}=I-\begin{bmatrix}u_{1}, \dots, u_{b}\end{bmatrix}\begin{bmatrix}t_{11} & 0 & 0 \\ \vdots & \ddots & 0 \\ t_{b1} & \dots & t_{bb}\end{bmatrix}\begin{bmatrix}u_{1} \\ \vdots \\ u_{b}\end{bmatrix}$$




$$\begin{align*}
P&= I\\
	&-2u_{b}u_{b}^{T}-\dots-2u_{1}u_{1}^{T}\\
&+2
\end{align*}$$