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
\end{aligned}$$
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
Substituting into the stress matrix equation:
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


![[Pasted image 20241025155118.png|700]]

![[Pasted image 20241025155145.png|700]]

![[Pasted image 20241025155246.png|700]]
