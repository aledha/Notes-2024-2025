Prev: [[Mechanical energy balance, strain energy]]
We consider large deformations and use $\dot {\mathbf E}=\mathbf F^{T}\cdot \mathbf D \cdot \mathbf F$. This can be rewritten to
$$\mathbf F^{-T}\cdot \dot {\mathbf E}\cdot \mathbf F^{-1}=\mathbf D \tag{*}$$
Deformation power:
$$\int_{V} \mathbf T:\mathbf D\text{ d}V$$
must be invariant, i.e., this scalar has the same value irrespective of coordinate system and stress and strain measures used.
What stress is energy conjugate to $\dot {\mathbf E}$?

Deformation power in current configuration = deformation power related to reference configuration:
$$\int_{V}\mathbf T:\mathbf D \text{ d}V=\int_{V_{0}}\mathbf S:\dot {\mathbf E} \text{ d}V_{0},$$
where $\mathbf S$ is a new stress measure. 
$$\text{ d}V=J \text{ d}V_{0}, \qquad J=\det(\mathbf F).$$
Using this, we get that we are integrating over the same volume:
$$\begin{aligned}
\int_{V_{0}}\mathbf T:\mathbf D J\text{ d}V_{0}&= \int_{V_{0}}\mathbf S:\dot {\mathbf E} \text{ d}V_{0},\\
\mathbf T:\mathbf D J\text{ d}V_{0}&= \mathbf S:\dot {\mathbf E} \text{ d}V_{0}\\
\mathbf T:\mathbf D J&= \mathbf S:\dot {\mathbf E}\\
\mathbf T:(\mathbf {\underbrace{\mathbf F^{-T}\dot E}_{(*)}F^{-1} })J&= \mathbf S:\dot {\mathbf E}\\
 \mathbf S:\dot {\mathbf E}&= J(\mathbf {\mathbf F^{-1}TF^{-T}}):\dot {\mathbf E}
\end{aligned}$$
after some manipulations, we obtain 
$$\mathbf S=J \mathbf {F^{-1}TF^{-T}},$$
named 2nd Piola-Kirchoff Stress.

The components of 2PK stress:
$$\begin{aligned}
\mathbf F^{-1}\cdot \mathbf T \cdot \mathbf F^{-T}&= F_{ij}^{-1}e_{i}\otimes e_{j}T_{qr} e_{q}\otimes e_{r} \cdot \underbrace{F^{-1}_{nm}e_{m}\otimes e_{n}}_{F^{T}}\\
&= F_{ij}^{-1}\cdot T_{jm}  \cdot F^{-1}_{nm}\cdot e_{i}\otimes e_{n}
\end{aligned}$$
Since $F_{ij}=\frac{\partial x_{i}}{\partial X_{j}}\quad\implies\quad F_{ij}^{-1}=\frac{\partial X_{i}}{\partial x_{j}}$, and
$$\begin{aligned}
S_{in} e_{i}\otimes e_{n}&= J \frac{\partial X_{i}}{\partial x_{j}}T_{jm} \frac{\partial X_{n}}{\partial x_{m}} \cdot e_{i}\otimes e_{n}\,.
\end{aligned}$$

Can we express $\mathbf S$ from a strain energy potential $\psi (\mathbf E)$?
$$\begin{aligned}
\mathbf T:\mathbf D \text{ d}V&= \dot \psi \text{ d}V=\frac{\partial \psi }{\partial \mathbf E}:\mathbf {\dot E}\text{ d}V_{0}\\
&= \mathbf S:\dot {\mathbf E}\text{ d}V_{0}\\
\mathbf S&= \frac{\partial \psi }{\partial \mathbf E}
\end{aligned}$$
For a hyperelastic material, we can find 2PK stresses from derivation of a strain energy potential $\psi (\dot {\mathbf E})$.

Play around with different $\psi$.

### Example: Biaxial Loading of a Hyperelastic Tissue
![[IMG_0240.jpg|600]]
In the experiment: measure forces $K_{1},K_{2}$ and lengths $L_{1},L_2,h$.
We can calculate:
- Cauchy stress $T_{11}= \frac{K_{1} }{L_{2}h}, \qquad T_{22}=\frac{K_{2}}{L_{1}h}$
- Stretches: $\lambda_{1}=\frac{L_{1}}{L_{1,0}}$, $\lambda_{2}=\frac{L_{2}}{L_{2,0}}$, $\lambda_{3}=\frac{L_{3}}{L_{3,0}}$
- Engineering strain $\epsilon _{1}=\frac{L_{1}-L_{1,0}}{L_{1,0}}=\lambda _{1}-1$,  $\epsilon _{2}=\lambda _{2}-1$.

Motion and deformation can be expressed as 
$$\begin{aligned}
x_{1}&= \frac{X_{1}}{L_{1,0}}\cdot L_{1}=\lambda _{1}X_{1}\\
x_{2}&= \frac{X_{2}}{L_{2,0}}\cdot L_{2}=\lambda _{2}X_{2}\\
x_{3}&= \frac{X_{3}}{L_{3,0}}\cdot L_{3}=\lambda _{3}X_{3}
\end{aligned}$$

$$\begin{aligned}
\left[F_{ij} \right]&= \left[\frac{\partial x_{i}}{\partial X_{j}} \right]\\
&= \begin{bmatrix}\lambda _{1} & 0 & 0\\
0 & \lambda _{2} & 0\\
0 & 0 & \lambda _{3}\end{bmatrix}\\
\left[F_{ij} \right]^{-1}&= \begin{bmatrix}\lambda _{1}^{-1} & 0 & 0\\
0 & \lambda _{2}^{-1} & 0\\
0 & 0 & \lambda _{3}^{-1}\end{bmatrix}\\
J &= \det(F)\\
&= \lambda _{1}\lambda _{2}\lambda _{3}
\end{aligned}$$
Now we can find the Green strains:
$$\begin{aligned}
E_{ij}&= \frac{1}{2}\left(\frac{\partial x_{m}}{\partial X_{i}}\frac{\partial x_{m}}{\partial X_{j}} - \delta _{ij}\right)\\
E_{11}&= \frac{1}{2}(\lambda _{1}^{2}-1)\\
E_{22}&= \frac{1}{2}(\lambda _{2}^{2}-1)
\end{aligned}$$
We can also find 2. Pioala-Kirchoff stresses:
$$\begin{aligned}
S&= JF^{-1}\cdot T \cdot F^{-T}\\
&= J \begin{bmatrix}\lambda _{1}^{-1} & 0 & 0\\
0 & \lambda _{2}^{-1} & 0\\
0 & 0 & \lambda _{3}^{-1}\end{bmatrix}\begin{bmatrix}T_{11} & 0 & 0\\
0 & T_{22} & 0\\
0 & 0 & T_{33}\end{bmatrix}\begin{bmatrix}\lambda _{1}^{-1} & 0 & 0\\
0 & \lambda _{2}^{-1} & 0\\
0 & 0 & \lambda _{3}^{-1}\end{bmatrix}\\
	S_{11}&= J \frac{1}{\lambda ^{2}_{1}}T_{11}=\frac{\lambda _{2}\lambda _{3}}{\lambda _{1}}T_{11}\\
S_{22}&= \frac{\lambda _{1}\lambda _{3}}{\lambda _{2}}T_{22}
\end{aligned}$$
If we assume that tissue is incompressible, then $J=\lambda _{1}\lambda _{2}\lambda _{3}=1$ (volume is constant). We can then set $\lambda _{3}=\frac{1}{\lambda _{1}\lambda _{2}}$. Then
$$\begin{aligned}
S_{11}&= \frac{1}{\lambda _{1}^{2}}T_{11}\\
	S_{22}&= \frac{1}{\lambda _{2}^{2}}T_{22}.
\end{aligned}$$
Fung proposed the following strain energy potential
$$\begin{aligned}
	\psi &= \frac{1}{2}\left(\alpha _{1}E_{11}^{2}+\alpha _{2}E_{22}^{2}+ \alpha _{3}E_{12}^{2}+\alpha _{3}E^{2}_{21}+2\alpha _{4}E_{11}E_{22} \right)+ \frac{1}{2}C \exp(Q),
\end{aligned}$$
where
$$Q=a_{1}E_{11}^{2}+a_{2}E_{22}^{2}+a_{3}E_{12}^{2}+a_{3}E_{21}^{2}+2a_{4}E_{11}E_{22}+bE_{11}^{3}+b_{2}E_{22}^{3}+b_{3}E_{11}^{2}E_{22}+b_{4}E_{11}E_{22}^{2}$$
this gives a linear curve, then abruptly exponential. There are 13 material parameters here ($\alpha _{i},b_{i},a_{i},C$), not feasible. But if there's only $E_{11}$ and $E_{22}$ it could be feasible.
$$S_{11}= \frac{\partial \psi }{\partial E_{11}}$$
