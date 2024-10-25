Alexander Hatle
![[Pasted image 20241025154944.png|700]]
![[Pasted image 20241025154833.png|500]]
![[Pasted image 20241025153439.png|700]]

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


![[Pasted image 20241025154856.png|700]]

![[Pasted image 20241025154922.png|700]]
![[Pasted image 20241025155005.png|500]]

![[Pasted image 20241025155029.png|700]]
![[Pasted image 20241025155044.png|700]]
![[Pasted image 20241025155058.png|700]]


![[Pasted image 20241025155118.png|700]]

![[Pasted image 20241025155145.png|700]]

![[Pasted image 20241025155246.png|700]]
