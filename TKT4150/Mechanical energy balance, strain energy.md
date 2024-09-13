Power = work per time on a volume V
$$P=\int_{P}\mathbf b \cdot \mathbf v \text{ d}V+\int_{A}\mathbf t \cdot \mathbf v dA \tag{1}$$

$$\int_{A}\mathbf t \cdot \mathbf v \text{ d}A=\int_{A}(\mathbf v \cdot \mathbf T)\mathbf n \text{ d}A=\int_{V}\text{div}(\mathbf v \cdot \mathbf T)\text{ d}V \tag{2}$$

$\mathbf v \cdot \mathbf T=v_{i}T_{ik}\mathbf{e}_{k}$,  
$$\begin{aligned}
\text{div}(v_{i}T_{ik}e_{k})&= \partial _{x_{q}}e_{q}\cdot (v_{i}T_{ik}e_{k})\\
&= v_{i,k}T_{ik}+v_{i}T_{ik,k}
\end{aligned}$$
Dummy index: $v_{i,k}T_{ik}= \frac{1}{2}(v_{i,k}T_{ik}+v_{k,i}T_{ki})$. 
Since the stress matrix is symmetric, we can rewrite this as 
$$\begin{aligned}
v_{i,k}T_{ik}&=  \frac{1}{2}(v_{i,k}T_{ik}+v_{k,i}\underbrace{T_{ik}}_\text{symm})\\
&= \frac{1}{2}(v_{i,k}+v_{k,i})T_{ik}\\
&= D_{ik}T_{ik}\\
&= \mathbf T :\mathbf D
\end{aligned}$$
hence, we obatin
$$\text{div}(\mathbf v \cdot \mathbf T)=\mathbf T:\mathbf D+\underbrace{\mathbf v \text{div T}}_{=v_{i}T_{ik,k}}\tag{3}$$
(2)+(3)-> (1)
$$\begin{aligned}
P&= \int_{V}\left[\mathbf T:\mathbf D+\mathbf v \cdot (\underbrace{\text{div}\mathbf T+\rho \mathbf b}_{=\rho \mathbf a=\rho \dot {\mathbf v}}) \right] \text{ d}V\\
&= \underbrace{\int_{V}\mathbf T:\mathbf D \text{ d}V}_{P_{d}, \text{ deformation power}}+ \underbrace{\int_{V}\rho \mathbf v \cdot \mathbf {\dot v} \text{ d}V}_{K, \text{ Kinetic energy}}
\end{aligned}$$
We define deformation power per volume: $\omega =\mathbf T:\mathbf D$.
Assume small deformations: $P_{d}$ 
$$\mathbf D \approx \dot {\mathbf E},\qquad P_{d}=\int_{V}\mathbf T:\dot {\mathbf E} \text{ d}V=\int_{V}\omega \text{ d}V$$
$$\begin{aligned}
w:&= \int_{t_{0}}\omega \text{ d}t=\int_{\mathbf E_{0}}\mathbf T:\text{ d}\mathbf E\\
&= \int_{E_{ij}}T_{ij}\text{ d}E_{ij}\\
w&= \text{is stress work per volume}
\end{aligned}$$

For a hyperelastic material in small deformations, $\omega$ or $w$ can be derived from a scalar-valued potential $\phi(\mathbf E)$ such that
$$\omega = \dot \phi =\partial _{\mathbf E}\phi :\dot {\mathbf E}=\partial _{E_{ij}}\phi \dot E_{ij}$$
$$w=\int_{t_{0}}^{t}\omega \text{ d}t=\int_{\mathbf E_{0}}^{\mathbf E} \frac{\partial \phi }{\partial \mathbf E}:\text{ d}\mathbf E=\left[\phi  \right]_{\mathbf E_{0}}^{\mathbf E}=\phi (\mathbf E)-\phi (\mathbf E_{0})$$
$\phi$ is called strain energy per volume.

### Example, uniaxial stress
![[IMG_0214.jpg|600]]

#### Strain Energy and the stress tensor
$$\omega =T_{ij}\dot E_{ij}$$
for small deformations. 
And for hyperelastic material
$$\omega =\frac{\partial \phi }{\partial E_{ij}}\dot E_{ij}$$
if $\phi$ only depends on $E_{ij}$ (and not on $\dot E_{ij}$), then $T_{ij}=\frac{\partial \phi }{\partial E_{ij}}$ and $\mathbf T=\mathbf T(\mathbf E)$.

### Example, Hooke's law
We have found earlier that for 
$$\mathbf T(\mathbf E)=\frac{\mu }{1+\nu }\left[\mathbf E+\frac{\nu }{1-2\nu }\text{trace}(\mathbf E) \mathbf I \right]$$
What $\phi$ corresponds to this?
Try (the correct expression)
$$\begin{aligned}
\phi &= \frac{1}{2}\frac{\mu }{1+\nu }\left(E_{ij}E_{ij}+\frac{\nu }{1-2\nu }E_{kk}E_{ll}\right)\\
&= \frac{1}{2}\frac{\mu }{1+\nu } \left[\mathbf E:\mathbf E+\frac{\nu }{1-2\nu }(\text{trace }\mathbf E)^{2} \right]
\end{aligned}$$
Computing the derivatives for each term
$$\begin{aligned}
\frac{\partial \mathbf E:\mathbf E}{\partial \mathbf E}&= \frac{\partial (E_{ij}\cdot E_{ij})}{\partial E_{mn}}\\
&= \frac{\partial E_{ij}}{\partial E_{mn}}E_{ij}+E_{ij}\frac{\partial E_{ij}}{\partial E_{mn}}\\
&= 2E_{mn}\\
&= 2\mathbf E
\end{aligned}
$$
$$\begin{aligned}
	\frac{\partial \text{trace }\mathbf E}{\partial \mathbf E}&= \frac{\partial E_{kk}}{\partial E_{ij}}\\
&= \delta _{ik}\delta _{kj}\\
&= \delta _{ij}\\
&= \mathbf I
\end{aligned}$$
$$\begin{aligned}
\implies\quad \frac{\partial \phi }{\partial \mathbf E}&= \frac{\mu }{1+\nu }\left[\mathbf E+\frac{\nu }{1-2\nu }(\text{tr}\mathbf E) \mathbf I \right]\\
&= \mathbf T(\mathbf E)
\end{aligned}$$

$\mu :$ youngs modulus
$\nu :$ poisson parameter