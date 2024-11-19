![[Pasted image 20241025155403.png]]

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
Again, taking the circumferential direction in the equation for the Neo-Hookean relation, and using that the length is fixed ($\lambda _z=1$):
$$\begin{aligned}
\sigma _{\theta }&=  \frac{2c}{\lambda _{z}\lambda _{\theta }\lambda _{r}}\lambda _{\theta }^{2}\\
&= \frac{2c \lambda _\theta }{ \lambda _r}
\end{aligned}$$
If we approximate the balloon to be a cylinder with fixed lengths, we can reuse the equilibrium condition 
$$\begin{aligned}
\sigma _\theta \cdot 2tL&= p(r-t)L\\
p&= \frac{2t}{r-t}\sigma _\theta,
\end{aligned}$$
where $t$ and $r$ are the current thickness and radius. Substituting the equation for $\sigma _\theta$,
$$p=\frac{4ct}{r-t}\cdot \frac{\lambda _\theta }{\lambda _r}$$
We have the relation between the current thickness and radius as $t(r)=3.45\text{ mm}-0.15r$. Since we wish to use the pressure to increase the radius from $r_0$ to $R$, we can set up the following stretch ratios
$$\begin{aligned}
\lambda _\theta &= \frac{R}{r_0 },\\
\lambda _r &= \frac{t(R)}{t(r_0)}.
\end{aligned}$$
Substituting these back into the equation, 
$$\begin{aligned}
p&= \frac{4c \cdot t(R)}{R-t(R)}\cdot \frac{\frac{R}{r_0}}{\frac{t(R)}{t(r_0)}}\\
&= \frac{4cR \cdot  t(r_0)}{(R-t(R))r_0}\\
&= \frac{4cR \cdot (3.45 \text{ mm} -0.15r_0)}{(R-3.45 \text{ mm}+0.15R)r_0},
\end{aligned}$$
and inserting the known values of $R=5 \text{ mm}, r_0=\frac{R}{1.66}=3 \text{ mm}$ and the previously calculated $c=17 \text{ kPa}$:
$$\begin{aligned}
p&= \frac{4 \cdot 17 \text{ kPa}\cdot 5 \text{ mm} \cdot (3.45 \text{ mm}-0.15 \cdot 3\text{ mm})}{(5 \text{ mm}-3.45 \text{ mm}+0.15 \cdot 5 \text{ mm})\cdot 3 \text{ mm}}\\
&= 147.8 \text{ kPa}
\end{aligned}$$
