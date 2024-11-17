![[Pasted image 20241025155403.png]]
Neo-Hooke:
$$\Psi =\frac{c}{2}(I_{1}-3)$$
Denote the initial internal and external radius as $A$ and $B$, respectively. Denote the internal and external radius after the pressure increase as $a$ and $b$, respectively.


The deformation tensor is 
$$
\mathbf F= \begin{bmatrix}\lambda _{z} & 0 & 0\\
0 & \lambda _{\theta } & 0\\
0 & 0 & \lambda _{r}\end{bmatrix}.
$$
and the left Cauchy-Green deformation tensor is
$$\begin{aligned}
\mathbf b&= \mathbf F \mathbf F^{T}\\
&= \begin{bmatrix}\lambda _{z}^{2} & 0 & 0\\
0 & \lambda _{\theta }^{2} & 0\\
0 & 0 & \lambda _{r}^{2}\end{bmatrix}.
\end{aligned}$$
The Cauchy stresses are 
$$\mathbf \sigma =\begin{bmatrix}\sigma _{z} & 0 & 0 \\ 0 & \sigma _{\theta } & 0 \\ 0 & 0 & \sigma _{r}\end{bmatrix}$$
Assume a Neo-Hooke material model:
$$\begin{aligned}
\mathbf \sigma &= \frac{1}{J}2c \mathbf b\\
\begin{bmatrix}\sigma _{z} & 0 & 0 \\ 0 & \sigma _{\theta } & 0 \\ 0 & 0 & \sigma _{r}\end{bmatrix}&= \frac{2c}{J}\begin{bmatrix}\lambda _{z}^{2} & 0 & 0\\
0 & \lambda _{\theta }^{2} & 0\\
0 & 0 & \lambda _{r}^{2}\end{bmatrix}.
\end{aligned}$$
We have that $J=\lambda _{z}\lambda _{\theta }\lambda _{r}$. Taking the equation for the circumferential direction:
$$\begin{aligned}
\sigma _{\theta }&=  \frac{2c}{\lambda _{z}\lambda _{\theta }\lambda _{r}}\lambda _{\theta }^{2}\\
c&= \frac{\lambda _{z}\lambda _{r}}{2\lambda _{\theta }}\sigma _{\theta }.
\end{aligned}$$
The cylinder is subjected to no stretching in the axial direction since the length of the segment is fixed, meaning that $\lambda _{z}=1$. The cylinder is however subjected to stretches is the circumferential and radial direction. The circumferential stretch is given by the proportion of the current circumference to the initial circumference:
$$\begin{aligned}
\lambda _{\theta }&= \frac{2\pi r}{2\pi r_{0}}\\
&= \frac{6 \text{ mm}}{5 \text{ mm}}\\
&= 1.2
\end{aligned}$$
The radial stretch is given by the proportion of the current thickness to the initial thickness:
$$\begin{aligned}
\lambda _{r}&= \frac{t}{t_{0}}\\
&= \frac{0.9\text{ mm}}{1 \text{ mm}}\\
&= 0.9
\end{aligned}$$

To determine the hoop stress in the cylinder $\sigma _{\theta }$, consider a half segment as shown in figure (). The force enacted by the pressure, $F_{p}$, and enacted by the hoop stress, $F_{\theta }$, are 
$$\begin{aligned}
F_{p}&= p \cdot (r-t)L,\\
F_{\theta }&= \sigma _{\theta }\cdot 2tL.
\end{aligned}$$
In actuality, the hoop stress varies across the thickness, but we will assume here that it is constant. Since the forces must be balanced in the 1-direction, we get
$$\begin{aligned}
\sigma _{\theta } \cdot 2tL&= p \cdot (r-t)L\\
\sigma _{\theta }&= \frac{p(r-t)}{2t}.
\end{aligned}$$
Substituting into the expression for $c$:
$$\begin{aligned}
c&= \frac{\lambda _{z}\lambda _{r}}{2\lambda _{\theta }}\sigma _{\theta }\\&= \frac{\lambda _{z}\lambda _{r}}{2\lambda _{\theta }}\frac{p(r-t)}{2t}
\end{aligned}$$
Finally, inserting known values:
$$\begin{aligned}
c &= \frac{1 \cdot 0.9}{2 \cdot 1.2}\cdot \frac{16 \text{ kPa} \cdot (6 \text{ mm}- 0.9 \text{ mm})}{2\cdot 0.9 \text{ mm}}\\
&= 17 \text{ kPa}
\end{aligned}$$



* pre-stretched
* anistropy, media and adventita
* thin-walled assumption not valid when $t/r>0.1$


![[Pasted image 20241114120218.png|700]]

![[Pasted image 20241025155412.png]]
![[Pasted image 20241025155425.png|500]]
