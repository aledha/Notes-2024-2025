Alexander Hatle
![[Pasted image 20241016132920.png|800]]
![[Pasted image 20241023132240.png|800]]
![[Pasted image 20241016132932.png|800]]
Using the chain rule,
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
![[Pasted image 20241024105106.png|600]]
$$\begin{bmatrix}\sigma _{1} \\   & \sigma _{2}  \\  &   & \sigma _{3}\end{bmatrix}=2c_{1}\begin{bmatrix}\lambda _{1}^{2} & 0 & 0\\
0 & \lambda _{2}^{2} & 0\\
0 & 0 & \frac{1}{(\lambda _{1}\lambda _{2})^{2}}\end{bmatrix}-p\begin{bmatrix}1  & 0 & 0\\ 0  & 1 & 0 \\0  & 0  & 1\end{bmatrix}$$
Due to plane stress conditions, we set $\sigma _{3}=0$, giving that
$$\begin{aligned}
2c_{1}\frac{1}{(\lambda _{1}\lambda _{2})^{2}}-p&= 0\\
p&= \frac{2c_{1}}{(\lambda _{1}\lambda _{2})^{2}}
\end{aligned}$$
![[Pasted image 20241024105057.png|800]]
![[Pasted image 20241016133005.png|800]]
$$\Psi (I_{1},I_{4},J)=c_{1}(I_{1}-3)+2\frac{k_{1}}{k_{2}}(\exp(k_{2}(I_{4}-1)^{2})-1)-p(J-1)$$

$$\begin{aligned}
\mathbf S&= 2\frac{\partial \Psi }{\partial \mathbf C}\\
&= 2\left(\frac{\partial \Psi }{\partial I_{1}} \frac{\partial I_{1}}{\partial \mathbf C}+\frac{\partial \Psi }{\partial I_{4}} \frac{\partial I_{4}}{\partial \mathbf C}+\frac{\partial \Psi }{\partial J} \frac{\partial J}{\partial \mathbf C}\right)
\end{aligned}$$
We are already given $\frac{\partial I_{1}}{\partial \mathbf C},\frac{\partial J}{\partial \mathbf C}$, so let's calculate $\frac{\partial I_{4}}{\partial \mathbf C}$:
$$\begin{aligned}
I_{4}&= a_{0i}C_{ij}a_{0j}\\
\frac{\partial I_{4}}{\partial C_{kl}}&= a_{0i}\frac{\partial C_{ij}}{\partial C_{kl}}a_{0j}\\
&= a_{0i}\delta _{ik}\delta _{jl}a_{0j}\\
&= a_{0k} a_{0l}\\
&= \mathbf a_{0}\otimes \mathbf a_{0}
\end{aligned}$$
Substituting
$$\begin{aligned}
\mathbf S&= 2\left(\frac{\partial \Psi }{\partial I_{1}} \mathbf I+\frac{\partial \Psi }{\partial I_{4}} \mathbf a_{0}\otimes \mathbf a_{0}+\frac{\partial \Psi }{\partial J}\frac{1}{2}J \mathbf C^{-1}\right)\\
&= 2c_{1}\mathbf I+\left[8k_{1}(I_{4}-1)\cdot \exp(k_{2}(I_{4}-1)^{2}) \right]a_{0}\otimes a_{0}-pC^{-1}
\end{aligned}$$

$$\begin{aligned}
\sigma &= \frac{1}{J}\mathbf F \mathbf S \mathbf F^{T}\\
&= \mathbf F \left(2c_{1}\mathbf I+\left[8k_{1}(I_{4}-1)\cdot \exp((k_{2}(I_{4}-1)^{2})) \right]\mathbf a_{0}\otimes \mathbf a_{0}-pC^{-1} \right)\mathbf F^{T}\\
&= 2c_{1}\mathbf b+\left[8k_{1}(I_{4}-1)\cdot \exp((k_{2}(I_{4}-1)^{2})) \right]\mathbf F \mathbf a_{0}\otimes \mathbf a_{0} \mathbf F^{T}-p \mathbf I\\
&=  2c_{1}\mathbf b+\left[8k_{1}(I_{4}-1)\cdot \exp(k_{2}(I_{4}-1)^{2}) \right]\mathbf a \otimes \mathbf a-p \mathbf I
\end{aligned}$$

Let's find what $\mathbf a \otimes \mathbf a$ is:
$$\begin{aligned}
\mathbf a \otimes \mathbf a&= \mathbf F \mathbf a_{0}\otimes \mathbf F \mathbf a_{0}\\
&= \begin{bmatrix}\lambda _{1} & 0 & 0\\
0 & \lambda _{2} & 0\\
0 & 0 & \frac{1}{\lambda _{1}\lambda _{2}}\end{bmatrix}\begin{bmatrix}\cos \theta \\
\sin \theta \\
0\end{bmatrix}\otimes \begin{bmatrix}\lambda _{1} & 0 & 0\\
0 & \lambda _{2} & 0\\
0 & 0 & \frac{1}{\lambda _{1}\lambda _{2}}\end{bmatrix}\begin{bmatrix}\cos \theta \\
\sin \theta \\
0\end{bmatrix}\\
&= \begin{bmatrix}\lambda _{1}\cos \theta \\
\lambda _{2}\sin \theta \\
0\end{bmatrix}\otimes \begin{bmatrix}\lambda _{1}\cos \theta \\
\lambda _{2}\sin \theta \\
0\end{bmatrix}\\
&= \begin{bmatrix}\lambda _{1}^{2}\cos ^{2}\theta  & \lambda _{1}\lambda _{2}\sin \theta \cos \theta  & 0\\
\lambda _{1}\lambda _{2}\sin \theta \cos \theta  & \lambda _{2}^{2}\sin ^{2}\theta  & 0\\
0 & 0 & 0\end{bmatrix}
\end{aligned}$$
Then the Cauchy stress tensor
$$\begin{bmatrix}\sigma _{1} \\   & \sigma _{2}  \\  &   & \sigma _{3}\end{bmatrix}=2c_{1}\begin{bmatrix}\lambda _{1}^{2} & 0 & 0\\
0 & \lambda _{2}^{2} & 0\\
0 & 0 & \frac{1}{(\lambda _{1}\lambda _{2})^{2}}\end{bmatrix}+\left[8k_{1}(I_{4}-1)\cdot \exp(k_{2}(I_{4}-1)^{2})\right]\begin{bmatrix}\lambda _{1}^{2}\cos ^{2}\theta  & \lambda _{1}\lambda _{2}\sin \theta \cos \theta  & 0\\
\lambda _{1}\lambda _{2}\sin \theta \cos \theta  & \lambda _{2}^{2}\sin ^{2}\theta  & 0\\
0 & 0 & 0\end{bmatrix}-p\begin{bmatrix}1  & 0 & 0\\ 0  & 1 & 0 \\0  & 0  & 1\end{bmatrix}$$
Again, due to plane stress conditions, we set $\sigma _{3}=0$ to get
$$\begin{aligned}
0&= 2c_{1}\frac{1}{(\lambda _{1}\lambda _{2})^{2}}+0-p\\
p&= \frac{2c_{1}}{(\lambda _{1}\lambda _{2})^{2}}.
\end{aligned}$$

![[Pasted image 20241016133012.png|800]]
To have the directions as the principal stress directions, the Cauchy stress tensor has to be diagonal, i.e., the off-diagonal components in $\mathbf a \otimes \mathbf a$ have to be zero:
$$\begin{aligned}
\lambda _{1}\lambda _{2}\sin \theta \cos \theta &= 0\\
\sin \theta \cos \theta &= 0,
\end{aligned}$$
which gives the solutions $\theta =\{0 \degree, 90 \degree \}$.

![[Pasted image 20241016133018.png|800]]

$$\begin{aligned}
\lambda _{1}\lambda _{2}\lambda _{3}&= 1\\
\lambda \lambda _{2}^{2}&= 1\\
\lambda _{2}= \lambda _{3}&= \frac{1}{\sqrt{\lambda }}
\end{aligned}$$
and $\frac{1}{(\lambda _{1}\lambda _{2})^{2}}=\frac{\lambda }{\lambda ^{2}}=\frac{1}{\lambda }$. The Lagrange multiplier simplifies to
$$\begin{aligned}
p&=  \frac{2c_{1}}{(\lambda _{1}\lambda _{2})^{2}}\\
&= \frac{2c_{1}}{\lambda }
\end{aligned}$$

Then the Cauchy stress tensor becomes
$$\begin{bmatrix}\sigma _{1} \\   & \sigma _{2}  \\  &   & \sigma _{3}\end{bmatrix}=2c_{1}\begin{bmatrix}\lambda^{2} & 0 & 0\\
0 & \frac{1}{\lambda } & 0\\
0 & 0 & \frac{1}{\lambda}\end{bmatrix}+\left[8k_{1}(I_{4}-1)\cdot \exp(k_{2}(I_{4}-1)^{2}) \right]\begin{bmatrix}\lambda^{2}  & 0  & 0\\
0  & 0  & 0\\
0 & 0 & 0\end{bmatrix}-\frac{2c_{1}}{\lambda }\begin{bmatrix}1  & 0 & 0\\ 0  & 1 & 0 \\0  & 0  & 1\end{bmatrix}$$
$\sigma _{2}$ is
$$\begin{aligned}
\sigma _{2}&= \frac{2c_{1}}{\lambda}-\frac{2c_{1}}{\lambda }\\
&= 0.
\end{aligned}$$
$I_{4}$ is
$$\begin{aligned}
I_{4}&= \mathbf a_{0}^{T}\mathbf C \mathbf a_{0}\\
&= \begin{bmatrix}\cos \theta  & \sin \theta  & 0\end{bmatrix}\begin{bmatrix}\lambda^{2} & 0 & 0\\
0 & \frac{1}{\lambda } & 0\\
0 & 0 & \frac{1}{\lambda}\end{bmatrix}\begin{bmatrix}\cos \theta \\
\sin \theta \\
0\end{bmatrix}\\
&= \begin{bmatrix}1  & 0  & 0\end{bmatrix}\begin{bmatrix}\lambda^{2} & 0 & 0\\
0 & \frac{1}{\lambda } & 0\\
0 & 0 & \frac{1}{\lambda}\end{bmatrix}\begin{bmatrix}1 \\
0 \\
0\end{bmatrix}\\
&= \lambda ^{2}
\end{aligned}$$

Now we can find an expression for $\sigma _{1}$:
$$\begin{aligned}
\sigma _{1}&= 2c_{1}\lambda ^{2}+\left[8k_{1}(I_{4}-1)\cdot \exp((k_{2}(I_{4}-1)^{2})) \right]\lambda ^{2}-\frac{2c_{1}}{\lambda }\\
&= 2c_{1}\lambda ^{2}+\left[8k_{1}(\lambda ^{2}-1)\cdot \exp(k_{2}(\lambda ^{2}-1)^{2}) \right]\lambda ^{2}-\frac{2c_{1}}{\lambda }\\
&= \left[2c_{1}+8k_{1}(\lambda ^{2}-1)\exp(k_{2}(\lambda ^{2}-1)^{2}) \right]\lambda ^{2}-\frac{2c_{1}}{\lambda }\\
&= \left[0.02+0.8(\lambda ^{2}-1)\exp(10(\lambda ^{2}-1)^{2}) \right]\lambda ^{2}-\frac{0.02}{\lambda }
\end{aligned}$$
![[Pasted image 20241024120303.png|600]]

