Alexander Hatle
![[Pasted image 20241016132411.png|800]]

![[Pasted image 20241016132423.png|800]]
$$\begin{aligned}
I_{4}&= \mathbf m_{0}^{T}\mathbf C\mathbf m_{0}\\
&=  \mathbf m_{0}^{T}(\mathbf F^{T}\mathbf F)\mathbf m_{0}\\
&= (\mathbf F \mathbf m_{0})^{T}\cdot (\mathbf F \mathbf m_{0})\\
&= \lVert \mathbf F \mathbf m_{0} \rVert_{2}^{2}\\
I_{6}&= \lVert \mathbf F \mathbf m_{0}' \rVert_{2}^{2}
\end{aligned}$$
So $I_{4}$ is, in a sense, the length of the deformation gradient tensor applied to the preferred direction of the family of collagen fibres.
If one applies $\mathbf F$ to $\mathbf m_{0}$ and gets a large vector then $I_{4}$ is large. This is analogous to having large local deformations in the direction of collagen fibres, which physically would demand more energy than if the deformations were perpendicular to the collagen fibres.
Similarly for $I_6$.

![[Pasted image 20241016132430.png|800]]
$$\Psi  (I_{1},J,I_{4},I_{6})=\frac{c}{2}(I_{1}-3)+\frac{k_{1}}{2k_{2}}\sum_{i=4,6}\left(\exp(k_{2}(I_{i}-1)^{2}) \right)+p(J-1)$$
$$\mathbf \sigma =\frac{1}{J} \mathbf F \mathbf S \mathbf F^{T}$$
Let's first find $\mathbf S$:
$$\begin{aligned}
\mathbf S&=  2 \frac{\partial \Psi }{\partial C}\\
S_{ij}&=2 \frac{\partial \Psi }{\partial C_{ij}} \\
&= 2\left(\frac{\partial \Psi }{\partial J}\frac{\partial J}{\partial C_{ij}}+\frac{\partial \Psi }{\partial I_{1}}\frac{\partial I_{1}}{\partial C_{ij}}+\frac{\partial \Psi }{\partial I_{4}}\frac{\partial I_{4}}{\partial C_{ij}} +\frac{\partial \Psi }{\partial I_{6}}\frac{\partial I_{6}}{\partial C_{ij}} \right)
\end{aligned}$$
The terms are
$$\begin{aligned}
\frac{\partial \Psi }{\partial J}&= p\\
\frac{\partial J}{\partial C_{ij}}&= \frac{1}{2}J \mathbf C^{-1}\\
\frac{\partial \Psi }{\partial I_{1}}&= \frac{c}{2}\\
	\frac{\partial I_{1}}{\partial C_{ij}}&= \mathbf 1\\
\frac{\partial \Psi }{\partial I_{4}}&= k_{1}(I_{4}-1)\exp(k_{2}(I_{4}-1)^{2})\\
\frac{\partial I_{4}}{\partial C_{ij}}&=  m_{0k}\frac{\partial C_{kl}}{\partial C_{ij}} m_{0l}\\
&= m_{0k}\delta _{ik} \delta _{jl}m_{0l}\\
&= m_{0i}m_{0j}\\
&= \mathbf m_{0}\otimes \mathbf m_{0}\\
\frac{\partial \Psi }{\partial I_{6}}&= k_{1}(I_{6}-1)\exp(k_{2}(I_{6}-1)^{2})\\
\frac{\partial I_{4}}{\partial C_{ij}}&=   \mathbf m_{0}'\otimes \mathbf m_{0}'
\end{aligned}$$
$$\begin{aligned}
\mathbf S&= 2 \left(\frac{p}{2}J \mathbf C^{-1}+ \frac{c}{2}\mathbf I+  k_{1}(I_{4}-1)\exp(k_{2}(I_{4}-1)^{2}) \mathbf m_{0}\otimes \mathbf m_{0}+ k_{1}(I_{6}-1)\exp(k_{2}(I_{6}-1)^{2}) \mathbf m_{0}'\otimes \mathbf m_{0}'\right)\\
&= pJ \mathbf C^{-1}+ c\mathbf I+  2k_{1}(I_{4}-1)\exp(k_{2}(I_{4}-1)^{2}) \mathbf m_{0}\otimes \mathbf m_{0}+ 2k_{1}(I_{6}-1)\exp(k_{2}(I_{6}-1)^{2}) \mathbf m_{0}'\otimes \mathbf m_{0}'\\
\mathbf \sigma &= \frac{1}{J} \mathbf F\left( pJ \mathbf C^{-1}+ c\mathbf I+  2k_{1}(I_{4}-1)\exp(k_{2}(I_{4}-1)^{2}) \mathbf m_{0}\otimes \mathbf m_{0}+ 2k_{1}(I_{6}-1)\exp(k_{2}(I_{6}-1)^{2}) \mathbf m_{0}'\otimes \mathbf m_{0}'\right) \mathbf F^{T}\\
&= \frac{1}{J}\left(pJ \mathbf F (\mathbf F^{T}\mathbf F)^{-1}\mathbf F^{T}+ c\mathbf F \mathbf F^{T}+  2k_{1}(I_{4}-1)\exp(k_{2}(I_{4}-1)^{2}) \mathbf F\mathbf m_{0}\otimes \mathbf m_{0}\mathbf F^{T}+ 2k_{1}(I_{6}-1)\exp(k_{2}(I_{6}-1)^{2}) \mathbf F\mathbf m_{0}'\otimes \mathbf m_{0}'\mathbf F^{T} \right)\\
&= \frac{1}{J}\left(pJ \mathbf I+ c\mathbf B+  2k_{1}(I_{4}-1)\exp(k_{2}(I_{4}-1)^{2}) \mathbf m\otimes \mathbf m\mathbf + 2k_{1}(I_{6}-1)\exp(k_{2}(I_{6}-1)^{2}) \mathbf m'\otimes \mathbf m' \right)
\end{aligned}$$



![[Pasted image 20241016132439.png|800]]
When the collagen fibres begin to stretch, they don't offer much resistance since they are uncoiling. When they get stretched more and more, they offer more resistance. Exponential functions describes this pretty well, as they don't grow very fast in the beginning.

![[Pasted image 20241016132448.png|800]]
$\kappa =0$ corresponds to no dispersion, while $\kappa=\frac{1}{3}$ corresponds to an isotropic distribution.

---
![[Pasted image 20241016132512.png|800]]

![[Pasted image 20241016132522.png|800]]
The directions have to be symmetric around the z-axis. If one direction is $10\degree$ from the z-axis, while the other is $20\degree$ from the z-axis, then the cylinder would deform in a non-symmetric way.
![[Pasted image 20241016132529.png|800]]
$$\begin{aligned}
\lambda _{z}&= \frac{l}{L}\\
\lambda &= \frac{r}{R}
\end{aligned}$$
![[Pasted image 20241016132539.png|800]]
Incompressibility gives that the volume should stay constant throughout the deformation. 
$$\begin{aligned}
2\pi L(B^{2}-A^{2})&= 2\pi l(b^{2}-a^{2})\\
\lambda _{z}^{-1}(B^{2}-A^{2})&= b^{2}-a^{2}
\end{aligned}$$
Also, the volume of the cylindrical tube with radius between $a$ and $r$ should equal the volume of the cylindrical tube with radius between $A$ and $R$:
$$\begin{aligned}
2\pi L(R^{2}-A^{2})&= 2\pi l(r^{2}-a^{2})\\
r^{2}&= a^{2}+\lambda _{z}^{-1}(R^{2}-A^{2})
\end{aligned}$$

![[Pasted image 20241016132547.png|800]]
$$\begin{aligned}
\lambda _{a}^{2}\lambda _{z}-1&= \frac{a^{2}}{A^{2}}\lambda _{z}-1\\
&= \frac{r^{2}-\lambda _{z}^{-1}(R^{2}-A^{2})}{A^{2}}\lambda _{z}-1\\
&= \frac{r^{2}}{A^{2}}\lambda _{z}-\frac{R^{2}-A^{2}}{A^{2}}-1\\
&= \frac{R^{2}}{A^{2}}\frac{r^{2}}{R^{2}}\lambda _{z}-\frac{R^{2}}{A^{2}}\\
&= \frac{R^{2}}{A^{2}}(\lambda ^{2}\lambda _{z}-1)
\end{aligned}$$
$\lambda _a$ is how much the inner radius has stretched during the deformation.

![[Pasted image 20241016132553.png|800]]
The sign of $(\lambda ^{2}\lambda _{z}-1)$ is the same sign as $\lambda _{a}^{2}\lambda _{z}-1$, as per the previous question. Since the tube is inflated ($P>0$), the inner radius must stretch to accommodate the pressure, meaning that $\lambda _{a}>1$. Since also $\lambda _{z}\ge1$,
$$\lambda _{a}^{2}\lambda _{z}-1 >0,$$
i.e., the sign is positive.

![[Pasted image 20241016132600.png|800]]
The internal pressure exerts the force 
$$P \cdot \pi a^{2},$$
which acts outwards of the tube.
Along one radius line, the stress force is
$$dN=2\pi \sigma _{zz} r,$$
which we can integrate to find the total stress force:
$$N=\int_{a}^{b}2\pi \sigma _{zz}r \text{ d}r,$$
which acts towards the tube.
Now we can find $F$ from setting the equilibrium condition
$$\begin{aligned}
F-N+P \cdot \pi a^{2}&= 0\\
F&= N-P \pi a^{2}
\end{aligned}$$

![[Pasted image 20241016132608.png|800]]
$$\mathbf F=\begin{bmatrix}\lambda _{z} & 0 & 0 \\ 0 & \lambda  & 0 \\ 0 & 0 & \lambda_{r}\end{bmatrix}$$
Since the $\mathbf m_{0}$ have no components in the radial direction, and they are displaced from the circumferential direction with the angle $\phi$,
$$\mathbf m_{0}=\begin{bmatrix}\sin \phi  \\ \cos \phi  \\ 0\end{bmatrix}$$
$$\begin{aligned}
\lambda (\mathbf m_{0})&=  \mathbf m_{0} \mathbf C \mathbf m_{0}\\
&= \lambda _{z}\sin ^{2}\phi +\lambda \cos ^{2}\phi 
\end{aligned}$$