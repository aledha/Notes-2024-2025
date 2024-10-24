Alexander Hatle
![[Pasted image 20241016132920.png|800]]
![[Pasted image 20241023132240.png|800]]
![[Pasted image 20241016132932.png|800]]

$$\begin{aligned}
\mathbf S&= 2\frac{\partial \Psi }{\partial \mathbf C}\\
&= 2\left(\frac{\partial \Psi }{\partial I_{1}} \frac{\partial I_{1}}{\partial \mathbf C}+\frac{\partial \Psi }{\partial J} \frac{\partial J}{\partial \mathbf C}\right)\\
&= 2\left(c_{1}\mathbf I-p \frac{1}{2}J \mathbf C^{-1} \right)
\end{aligned}$$
![[Pasted image 20241016132939.png|800]]
$$\begin{aligned}
\mathbf F&= \frac{\partial \mathbf x}{\partial \mathbf X}\\
&= \begin{bmatrix}\lambda _{1} & 0 & 0\\
0 & \lambda _{2} & 0\\
0 & 0 & \lambda _{3}\end{bmatrix}
\end{aligned}$$
Due to incompressibility, we have that $\det F=\lambda _{1}\lambda _{2}\lambda _{3}=1$, giving $\lambda _{3}=\lambda _{1}\lambda _{2}$. Then,
$$\mathbf F= \begin{bmatrix}\lambda _{1} & 0 & 0\\
0 & \lambda _{2} & 0\\
0 & 0 & \frac{1}{\lambda _{1}\lambda _{2}}\end{bmatrix}$$
The right Cauchy-Green tensor
$$\begin{aligned}
\mathbf C &= \mathbf F ^{T}\mathbf F\\
&= \begin{bmatrix}\lambda _{1}^{2} & 0 & 0\\
0 & \lambda _{2}^{2} & 0\\
0 & 0 & \frac{1}{(\lambda _{1}\lambda _{2})^{2}}\end{bmatrix}
\end{aligned}$$
And the left Cauchy-Green tensor
$$\begin{aligned}
\mathbf b &=  \mathbf F \mathbf F^{T}\\
&= \begin{bmatrix}\lambda _{1}^{2} & 0 & 0\\
0 & \lambda _{2}^{2} & 0\\
0 & 0 & \frac{1}{(\lambda _{1}\lambda _{2})^{2}}\end{bmatrix}
\end{aligned}$$

![[Pasted image 20241016132945.png|800]]
$$\begin{aligned}
\sigma &= \frac{1}{J}\mathbf F \mathbf S \mathbf F^{T}\\
&= \mathbf F(2c_{1}\mathbf I-p \mathbf C^{-1})\mathbf F^{T}\\
&= 2c_{1}\mathbf F \mathbf F^{T}-p \mathbf F(\mathbf F^{T}\mathbf F)^{-1}\mathbf F^{T}\\
&= 2c_{1}\mathbf b-p \mathbf I
\end{aligned}$$
![[Pasted image 20241016132953.png|800]]
Due to plane stress conditions, we set $\sigma _{3}=0$, giving that
$$\begin{aligned}
2c_{1}\frac{1}{(\lambda _{1}\lambda _{2})^{2}}-p&= 0\\
p&= \frac{2c_{1}}{(\lambda _{1}\lambda _{2})^{2}}
\end{aligned}$$
![[Pasted image 20241016133005.png|800]]
$$\Psi (I_{1},I_{4},J)=c_{1}(I_{1}-3)+2\frac{k_{1}}{k_{2}}(\exp(k_{2}(I_{4}-1)^{2})-1)-p(J-1)$$

$$\begin{aligned}
\mathbf S&= 2\frac{\partial \Psi }{\partial \mathbf C}\\
&= 2\left(\frac{\partial \Psi }{\partial I_{1}} \frac{\partial I_{1}}{\partial \mathbf C}+\frac{\partial \Psi }{\partial I_{4}} \frac{\partial I_{4}}{\partial \mathbf C}+\frac{\partial \Psi }{\partial J} \frac{\partial J}{\partial \mathbf C}\right)
\end{aligned}$$
$$\begin{aligned}
I_{4}&= a_{0i}C_{ij}a_{0j}\\
\frac{\partial I_{4}}{\partial C_{kk}}&= a_{0i}\frac{\partial C_{ij}}{\partial C_{kk}}a_{0j}\\
&= a_{0i}\delta _{ik}\delta _{jl}a_{0j}\\
&= a_{0k} a_{0l}\\
&= \mathbf a_{0}\otimes \mathbf a_{0}
\end{aligned}$$
$$\mathbf S=2c_{1}\mathbf I+\left[8k_{1}(I_{4}-1)\cdot \exp((k_{2}(I_{4}-1)^{2})) \right]a_{0}\otimes a_{0}-pC^{-1}$$

$$\begin{aligned}
\sigma &= \frac{1}{J}\mathbf F \mathbf S \mathbf F^{T}\\
&= 2c_{1}\mathbf b+\left[ \right]a_{0}\otimes a_{0}-p \mathbf I\\
&=  2c_{1}\mathbf b+\left[ \right]\mathbf F \mathbf a_{0}-p \mathbf I
\end{aligned}$$

dyadic prod $\otimes$
![[Pasted image 20241016133012.png|800]]

![[Pasted image 20241016133018.png|800]]