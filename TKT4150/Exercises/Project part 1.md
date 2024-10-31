Alexander Hatle
![[Pasted image 20241025154944.png|700]]
![[Pasted image 20241025154833.png|500]]
![[Pasted image 20241025153439.png|700]]
$$\Psi (I_{1},I_{4},J)=c_{1}(I_{1}-3)+2\frac{k_{1}}{k_{2}}(\exp(k_{2}(I_{4}-1)^{2})-1)-p(J-1)$$

$$\begin{aligned}
\mathbf S&= 2\frac{\partial \Psi }{\partial \mathbf C}\\
&= 2\left(\frac{\partial \Psi }{\partial I_{1}} \frac{\partial I_{1}}{\partial \mathbf C}+\frac{\partial \Psi }{\partial I_{4}} \frac{\partial I_{4}}{\partial \mathbf C}+\frac{\partial \Psi }{\partial J} \frac{\partial J}{\partial \mathbf C}\right).
\end{aligned}$$
We are already given $\frac{\partial I_{1}}{\partial \mathbf C},\frac{\partial J}{\partial \mathbf C}$, so let's calculate $\frac{\partial I_{4}}{\partial \mathbf C}$:
$$\begin{aligned}
I_{4}&= a_{0i}C_{ij}a_{0j}\\
\frac{\partial I_{4}}{\partial C_{kl}}&= a_{0i}\frac{\partial C_{ij}}{\partial C_{kl}}a_{0j}\\
&= a_{0i}\delta _{ik}\delta _{jl}a_{0j}\\
&= a_{0k} a_{0l}\\
&= \mathbf a_{0}\otimes \mathbf a_{0}.
\end{aligned}$$
Since the material is incompressible, $J=\det F=\lambda _{1}\lambda _{2}=1$, and $\lambda _{2}=\frac{1}{\lambda _{1}}$. Substituting:
$$\begin{aligned}
\mathbf S&= 2\left(\frac{\partial \Psi }{\partial I_{1}} \mathbf I+\frac{\partial \Psi }{\partial I_{4}} \mathbf a_{0}\otimes \mathbf a_{0}+\frac{\partial \Psi }{\partial J}\frac{1}{2}J \mathbf C^{-1}\right)\\
&= 2c_{1}\mathbf I+\left[8k_{1}(I_{4}-1)\cdot \exp(k_{2}(I_{4}-1)^{2}) \right]a_{0}\otimes a_{0}-pC^{-1}.
\end{aligned}$$
The stress matrix is
$$\begin{aligned}
\sigma &= \frac{1}{J}\mathbf F \mathbf S \mathbf F^{T}\\
&= \mathbf F \left(2c_{1}\mathbf I+\left[8k_{1}(I_{4}-1)\cdot \exp((k_{2}(I_{4}-1)^{2})) \right]\mathbf a_{0}\otimes \mathbf a_{0}-pC^{-1} \right)\mathbf F^{T}\\
&= 2c_{1}\mathbf b+\left[8k_{1}(I_{4}-1)\cdot \exp((k_{2}(I_{4}-1)^{2})) \right]\mathbf F \mathbf a_{0}\otimes \mathbf a_{0} \mathbf F^{T}-p \mathbf I\\
&=  2c_{1}\mathbf b+\left[8k_{1}(I_{4}-1)\cdot \exp(k_{2}(I_{4}-1)^{2}) \right]\mathbf a \otimes \mathbf a-p \mathbf I.
\end{aligned}\tag{1}$$
Setting up expressions for $\mathbf F, \mathbf b,\mathbf a \otimes \mathbf a$:
$$\begin{aligned}
\mathbf F&= \begin{bmatrix}\lambda _{1} & 0\\
0 & \lambda _{2}\end{bmatrix}\\
&= \begin{bmatrix}\lambda _{1} & 0\\
0 & \frac{1}{\lambda _{1}}\end{bmatrix}\\
\mathbf b &= \mathbf F \mathbf F^{T}\\
&= \begin{bmatrix}\lambda _{1}^{2} & 0\\
0 & \frac{1}{\lambda _{1}^{2}}\end{bmatrix}\\
\mathbf a \otimes \mathbf a&= \mathbf F \mathbf a_{0}\otimes \mathbf F \mathbf a_{0}\\
&= \begin{bmatrix}\lambda _{1} & 0\\
0 & \frac{1}{\lambda _{1}}\end{bmatrix}\begin{bmatrix}1\\
0\end{bmatrix}\otimes \begin{bmatrix}\lambda _{1} & 0\\
0 & \frac{1}{\lambda _{1}}\end{bmatrix}\begin{bmatrix}1\\
0\end{bmatrix}\\
&= \begin{bmatrix}\lambda _{1} \\
0\end{bmatrix}\otimes \begin{bmatrix}\lambda _{1}\\
0\end{bmatrix}\\
&= \begin{bmatrix}\lambda _{1}^{2} & 0\\
0 & 0\end{bmatrix}.
\end{aligned}$$
Substituting into (1):
$$\begin{aligned}
\begin{bmatrix}\sigma _{1} & 0\\
0 & \sigma _{2}\end{bmatrix}&= 2c_{1}\begin{bmatrix}\lambda _{1} ^{2} & 0\\
0 & \frac{1}{\lambda _{1}^{2}}\end{bmatrix}+\left[8k_{1}(I_{4}-1)\cdot \exp(k_{2}(I_{4}-1)^{2}) \right]\begin{bmatrix}\lambda _{1}^{2} & 0\\
0 & 0\end{bmatrix}-p\begin{bmatrix}1 & 0\\
0 & 1\end{bmatrix}.
\end{aligned}$$
Since we are loading the bar uniaxially, we set $\sigma _{2}=0$ to get
$$\begin{aligned}
0&= 2c_{1}\frac{1}{\lambda _{1}^{2}}-p\\
p&= \frac{2c_{1}}{\lambda _{1}^{2}}.
\end{aligned}$$
Then, the equation for $\sigma _{1}$ is
$$\begin{aligned}
\sigma _{1}&= 2c_{1}\lambda _{1}^{2}+8k_{1}(I_{4}-1)\cdot \exp(k_{2}(I_{4}-1)^{2})\lambda _{1}^{2}-\frac{2c_{1}}{\lambda _{1}^{2}}\\
&= \left[2c_{1}+8k_{1}(I_{4}-1)\exp(k_{2}(I_{4}-1)^{2}) \right]\lambda _{1}^{2}- \frac{2c_{1}}{\lambda _{1}^{2}}.
\end{aligned}$$
We find $I_{4}$ as
$$\begin{aligned}
I_{4}&= \mathbf a_{0}\mathbf C \mathbf a_{0}\\
&= \mathbf a_{0}\mathbf F^{T}\mathbf F \mathbf a_{0}\\
&= \begin{bmatrix}1\\
0\end{bmatrix}\begin{bmatrix}\lambda _{1} & 0\\
0 & \frac{1}{\lambda _{1}}\end{bmatrix}\begin{bmatrix}\lambda _{1} & 0\\
0 & \frac{1}{\lambda _{1}}\end{bmatrix}\begin{bmatrix}1\\
0\end{bmatrix}\\
&= \lambda _{1}^{2}
\end{aligned}$$
Since $\sigma _{1}= \frac{P}{A_{0}}$, we can set up the expression for $P$:
$$P=\left[2c_{1}+8k_{1}(\lambda _{1}^{2}-1)\exp(k_{2}(\lambda _{1}^{2}-1)^{2}) \right]A_{0}\lambda _{1}^{2}- \frac{2c_{1}A_{0}}{\lambda _{1}^{2}}.$$
![[Pasted image 20241025154856.png|700]]


![[Pasted image 20241025154922.png|700]]
![[Pasted image 20241025155005.png|500]]

![[Pasted image 20241025155029.png|700]]
![[Pasted image 20241025155044.png|700]]
![[Pasted image 20241025155058.png|700]]
Very similar to exercise 5.
$$\Psi  (I_{1},J,I_{4_{1}},I_{4_{2}})=\frac{c}{2}(I_{1}-3)+\frac{k_{1}}{2k_{2}}\sum_{i=1,2}\left(\exp(k_{2}(I_{4_{i}}-1)^{2}) \right)+p(J-1)$$
$$\mathbf \sigma =\frac{1}{J} \mathbf F \mathbf S \mathbf F^{T}$$
Let's first find $\mathbf S$:
$$\begin{aligned}
\mathbf S&=  2 \frac{\partial \Psi }{\partial C}\\
S_{ij}&=2 \frac{\partial \Psi }{\partial C_{ij}} \\
&= 2\left(\frac{\partial \Psi }{\partial J}\frac{\partial J}{\partial C_{ij}}+\frac{\partial \Psi }{\partial I_{1}}\frac{\partial I_{1}}{\partial C_{ij}}+\frac{\partial \Psi }{\partial I_{4_{1}}}\frac{\partial I_{4_{1}}}{\partial C_{ij}} +\frac{\partial \Psi }{\partial I_{4_{2}}}\frac{\partial I_{4_{2}}}{\partial C_{ij}} \right)
\end{aligned}$$
The terms are
$$\begin{aligned}
\frac{\partial \Psi }{\partial J}&= p\\
\frac{\partial J}{\partial C_{ij}}&= \frac{1}{2}J \mathbf C^{-1}\\
\frac{\partial \Psi }{\partial I_{1}}&= \frac{c}{2}\\
	\frac{\partial I_{1}}{\partial C_{ij}}&= \mathbf 1\\
\frac{\partial \Psi }{\partial I_{4_{1}}}&= k_{1}(I_{4_{1}}-1)\exp(k_{2}(I_{4_{1}}-1)^{2})\\
\frac{\partial I_{4_{1}}}{\partial C_{ij}}&=  m_{0k}\frac{\partial C_{kl}}{\partial C_{ij}} m_{0l}\\
&= m_{0k}\delta _{ik} \delta _{jl}m_{0l}\\
&= m_{0i}m_{0j}\\
&= \mathbf m_{0}\otimes \mathbf m_{0}\\
\frac{\partial \Psi }{\partial I_{4_{2}}}&= k_{1}(I_{4_{2}}-1)\exp(k_{2}(I_{4_{2}}-1)^{2})\\
\frac{\partial I_{4_{1}}}{\partial C_{ij}}&=   \mathbf m_{0}'\otimes \mathbf m_{0}'
\end{aligned}$$
Substituting into the equation for the second Piola-Kirchoff stress tensor:
$$\begin{aligned}
\mathbf S&= 2 \left(\frac{p}{2}J \mathbf C^{-1}+ \frac{c}{2}\mathbf I+  k_{1}(I_{4_{1}}-1)\exp(k_{2}(I_{4_{1}}-1)^{2}) \mathbf m_{0}\otimes \mathbf m_{0}+ k_{1}(I_{4_{2}}-1)\exp(k_{2}(I_{4_{2}}-1)^{2}) \mathbf m_{0}'\otimes \mathbf m_{0}'\right)\\
&= pJ \mathbf C^{-1}+ c\mathbf I+  2k_{1}(I_{4_{1}}-1)\exp(k_{2}(I_{4_{1}}-1)^{2}) \mathbf m_{0}\otimes \mathbf m_{0}+ 2k_{1}(I_{4_{2}}-1)\exp(k_{2}(I_{4_{2}}-1)^{2}) \mathbf m_{0}'\otimes \mathbf m_{0}',
\end{aligned}$$
allowing us to set the expression for the Cauchy stress tensor as
$$\begin{aligned}
\mathbf \sigma &= \frac{1}{J} \mathbf F\left( pJ \mathbf C^{-1}+ c\mathbf I+  2k_{1}(I_{4_{1}}-1)\exp(k_{2}(I_{4_{1}}-1)^{2}) \mathbf m_{0}\otimes \mathbf m_{0}+ 2k_{1}(I_{4_{2}}-1)\exp(k_{2}(I_{4_{2}}-1)^{2}) \mathbf m_{0}'\otimes \mathbf m_{0}'\right) \mathbf F^{T}\\
&= \frac{1}{J}\left(pJ \mathbf F (\mathbf F^{T}\mathbf F)^{-1}\mathbf F^{T}+ c\mathbf F \mathbf F^{T}+  2k_{1}(I_{4_{1}}-1)\exp(k_{2}(I_{4_{1}}-1)^{2}) \mathbf F\mathbf m_{0}\otimes \mathbf m_{0}\mathbf F^{T}+ 2k_{1}(I_{4_{2}}-1)\exp(k_{2}(I_{4_{2}}-1)^{2}) \mathbf F\mathbf m_{0}'\otimes \mathbf m_{0}'\mathbf F^{T} \right)\\
&= \frac{1}{J}\left(pJ \mathbf I+ c\mathbf b+  2k_{1}(I_{4_{1}}-1)\exp(k_{2}(I_{4_{1}}-1)^{2}) \mathbf m\otimes \mathbf m\mathbf + 2k_{1}(I_{4_{2}}-1)\exp(k_{2}(I_{4_{2}}-1)^{2}) \mathbf m'\otimes \mathbf m' \right).
\end{aligned}$$
Due to incompressibility, we have that $J=\det F= \lambda _{1}\lambda _{2}\lambda _{3}=1$ so
$$\mathbf \sigma =p \mathbf I+ c\mathbf b+  2k_{1}(I_{4_{1}}-1)\exp(k_{2}(I_{4_{1}}-1)^{2}) \mathbf m\otimes \mathbf m\mathbf + 2k_{1}(I_{4_{2}}-1)\exp(k_{2}(I_{4_{2}}-1)^{2}) \mathbf m'\otimes \mathbf m' ,\tag{2}$$
and since $\lambda _{3}=\frac{1}{\lambda _{1}\lambda _{2}}$, the deformation gradient tensor is
$$\begin{aligned}
\mathbf F&= \begin{bmatrix}\lambda _{1} & 0 & 0 \\ 0 & \lambda _{2} & 0 \\ 0 & 0 & \lambda _{3}\end{bmatrix}\\
&= \begin{bmatrix}\lambda _{1} & 0 & 0 \\ 0 & \lambda _{2} & 0 \\ 0 & 0 & \frac{1}{(\lambda _{1}\lambda _{2})^{2}}\end{bmatrix}.
\end{aligned}$$
The left Cauchy-Green tensor is
$$\begin{aligned}
\mathbf b &=  \mathbf F \mathbf F^{T}\\
&= \begin{bmatrix}\lambda _{1}^{2} & 0 & 0\\
0 & \lambda _{2}^{2} & 0\\
0 & 0 & \frac{1}{(\lambda _{1}\lambda _{2})^{2}}\end{bmatrix}.
\end{aligned}$$
The mean fiber directions are described by
$$\begin{aligned}
\mathbf m_{0}&= \begin{bmatrix}\cos \theta _{1}\\
\sin \theta _{1}\\
0\end{bmatrix}\\
\mathbf m_{0}'&= \begin{bmatrix}\cos \theta _{2}\\
-\sin \theta _{2}\\
0\end{bmatrix}.
\end{aligned}$$
Assuming $\theta _{1}=\theta _{2}=\theta$, we can find the deformed fiber directions $\mathbf m, \mathbf m'$:
$$\begin{aligned}
\mathbf m&= \mathbf F \mathbf m_{0}\\
&= \begin{bmatrix}\lambda _{1} & 0 & 0 \\ 0 & \lambda _{2} & 0 \\ 0 & 0 & \frac{1}{(\lambda _{1}\lambda _{2})^{2}}\end{bmatrix}\begin{bmatrix}\cos \theta \\
\sin \theta \\
0\end{bmatrix}\\
&= \begin{bmatrix}\lambda _{1}\cos \theta \\
\lambda _{2}\sin \theta \\
0\end{bmatrix}\\
\mathbf m'&= \begin{bmatrix}\lambda _{1}\cos \theta \\
-\lambda _{2}\sin \theta \\
0\end{bmatrix},
\end{aligned}$$
and the dyadic products become
$$\begin{aligned}
\mathbf m \otimes \mathbf m&= \begin{bmatrix}\lambda _{1}\cos \theta \\
\lambda _{2}\sin \theta \\
0\end{bmatrix} \otimes \begin{bmatrix}\lambda _{1}\cos \theta \\
\lambda _{2}\sin \theta \\
0\end{bmatrix}\\
&= \begin{bmatrix}\lambda _{1}^{2}\cos ^{2}\theta  & \lambda _{1}\lambda _{2}\sin \theta \cos \theta  & 0\\
\lambda _{1}\lambda _{2}\sin \theta \cos \theta  & \lambda _{2}\sin ^{2}\theta  & 0\\
0 & 0 & 0\end{bmatrix}\\
\mathbf m' \otimes \mathbf m'&= \begin{bmatrix}\lambda _{1}\cos \theta \\
-\lambda _{2}\sin \theta \\
0\end{bmatrix} \otimes \begin{bmatrix}\lambda _{1}\cos \theta \\
-\lambda _{2}\sin \theta \\
0\end{bmatrix}\\
&= \begin{bmatrix}\lambda _{1}^{2}\cos ^{2}\theta  & -\lambda _{1}\lambda _{2}\sin \theta \cos \theta  & 0\\
-\lambda _{1}\lambda _{2}\sin \theta \cos \theta  & \lambda _{2}\sin ^{2}\theta  & 0\\
0 & 0 & 0\end{bmatrix}.
\end{aligned}$$
Calculating $I_{4_{1}},I_{4_{2}}$:
$$\begin{aligned}
I_{4_{1}}&= \mathbf m_{0}\cdot \mathbf C \cdot \mathbf m_{0}\\
&= \mathbf m_{0}\cdot \mathbf F ^{T}\mathbf F \cdot \mathbf m_{0}\\
&= \begin{bmatrix}\lambda _{1}\cos \theta \\
\lambda _{2}\sin \theta \\
0\end{bmatrix}\cdot \begin{bmatrix}\lambda _{1}\cos \theta \\
\lambda _{2}\sin \theta \\
0\end{bmatrix}\\
&= \lambda _{1}\cos ^{2}\theta +\lambda _{2}\sin ^{2}\theta \\
I_{4_{2}}&= \mathbf m_{0}'\cdot \mathbf C \cdot \mathbf m_{0}'\\
&= \begin{bmatrix}\lambda _{1}\cos \theta \\
-\lambda _{2}\sin \theta \\
0\end{bmatrix}\cdot \begin{bmatrix}\lambda _{1}\cos \theta \\
-\lambda _{2}\sin \theta \\
0\end{bmatrix}\\
&= \lambda _{1}\cos ^{2}\theta +\lambda _{2}\sin ^{2}\theta 
\end{aligned}$$

Substituting all these values into (2):
$$\begin{aligned}
\mathbf \sigma &= p \mathbf I+ c\mathbf b+  2k_{1}(I_{4_{1}}-1)\exp(k_{2}(I_{4_{1}}-1)^{2}) \mathbf m\otimes \mathbf m\mathbf + 2k_{1}(I_{4_{2}}-1)\exp(k_{2}(I_{4_{2}}-1)^{2}) \mathbf m'\otimes \mathbf m' \\
\begin{bmatrix}\sigma _{11} & \sigma _{12} & \sigma _{13}\\
\sigma _{21} & \sigma _{22} & \sigma _{23}\\
\sigma _{31} & \sigma _{32} & \sigma _{33}\end{bmatrix}&= p\begin{bmatrix}1 & 0 & 0\\
0 & 1 & 0\\
0 & 0 & 1\end{bmatrix}+c\begin{bmatrix}\lambda _{1}^{2} & 0 & 0\\
0 & \lambda _{2}^{2} & 0\\
0 & 0 & \frac{1}{(\lambda _{1}\lambda _{2})^{2}}\end{bmatrix}\\
&+2k_{1}(\lambda _{1}\cos ^{2}\theta +\lambda _{2}\sin ^{2}\theta -1)\exp(k_{2}(\lambda _{1}\cos ^{2}\theta +\lambda _{2}\sin ^{2}\theta -1)^{2})\begin{bmatrix}\lambda _{1}^{2}\cos ^{2}\theta  & \lambda _{1}\lambda _{2}\sin \theta \cos \theta  & 0\\
\lambda _{1}\lambda _{2}\sin \theta \cos \theta  & \lambda _{2}\sin ^{2}\theta  & 0\\
0 & 0 & 0\end{bmatrix}\\
&+2k_{1}(\lambda _{1}\cos ^{2}\theta +\lambda _{2}\sin ^{2}\theta -1)\exp(k_{2}(\lambda _{1}\cos ^{2}\theta +\lambda _{2}\sin ^{2}\theta -1)^{2})
\begin{bmatrix}\lambda _{1}^{2}\cos ^{2}\theta  & -\lambda _{1}\lambda _{2}\sin \theta \cos \theta  & 0\\
-\lambda _{1}\lambda _{2}\sin \theta \cos \theta  & \lambda _{2}\sin ^{2}\theta  & 0\\
0 & 0 & 0\end{bmatrix}\\
\begin{bmatrix}\sigma _{11} & \sigma _{12} & \sigma _{13}\\
\sigma _{21} & \sigma _{22} & \sigma _{23}\\
\sigma _{31} & \sigma _{32} & \sigma _{33}\end{bmatrix}&=\begin{bmatrix}p+c\lambda _{1}^{2} & 0 & 0\\
0 & p+c\lambda _{2}^{2} & 0\\
0 & 0 & p+\frac{c}{(\lambda _{1}\lambda _{2})^{2}}\end{bmatrix}\\
&+2k_{1}(\lambda _{1}\cos ^{2}\theta +\lambda _{2}\sin ^{2}\theta -1)\exp(k_{2}(\lambda _{1}\cos ^{2}\theta +\lambda _{2}\sin ^{2}\theta -1)^{2})\begin{bmatrix}\lambda _{1}^{2}\cos ^{2}\theta  & 0  & 0\\
0  & \lambda _{2}\sin ^{2}\theta  & 0\\
0 & 0 & 0\end{bmatrix}.
\end{aligned}$$
Due to plane stress conditions, we set $\sigma _{33}=0$ in order to determine $p$:
$$\begin{aligned}
\sigma _{33}&= 0\\
p&= -\frac{c}{(\lambda _{1}\lambda _{2})^{2}},
\end{aligned}$$
giving us the final expressions for $\sigma _{11}$ and $\sigma _{22}$
$$\begin{aligned}
\sigma _{11} &=-\frac{c}{(\lambda _{1}\lambda _{2})^{2}}+c\lambda _{1}^{2}
+2k_{1}(\lambda _{1}\cos ^{2}\theta +\lambda _{2}\sin ^{2}\theta -1)\exp(k_{2}(\lambda _{1}\cos ^{2}\theta +\lambda _{2}\sin ^{2}\theta -1)^{2})\lambda _{1}^{2}\cos ^{2}\theta \\
\sigma _{22} &=-\frac{c}{(\lambda _{1}\lambda _{2})^{2}}+c\lambda _{2}^{2}
+2k_{1}(\lambda _{1}\cos ^{2}\theta +\lambda _{2}\sin ^{2}\theta -1)\exp(k_{2}(\lambda _{1}\cos ^{2}\theta +\lambda _{2}\sin ^{2}\theta -1)^{2})\lambda _{2}^{2}\sin ^{2}\theta.
\end{aligned}$$


![[Pasted image 20241025155118.png|700]]

![[Pasted image 20241025155145.png|700]]

![[Pasted image 20241025155246.png|700]]
