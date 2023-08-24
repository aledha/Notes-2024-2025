$\Omega \in \mathbb{C}, \quad n \in C^{1}(\Omega )$ 
We can define a differential as follows
$\text{ d}u= \partial_{x}u \text{ d}x+ \partial_{y}dy$
$\partial_{z}u = \frac{1}{2}(\partial_{x}-i \partial_{y})u$
$\partial_{\overline{z}}u = \frac{1}{2}(\partial_{x}+i \partial_{y})u$
$dz = \text{ d}x+ i \text{ d}y$
$d \overline{z}= \text{ d}x- i \text{ d}y$

For a $u \in A(\Omega )$ 
$u$ is analytic (holomorphic) in $\Omega \quad\Leftrightarrow\quad \partial_{\overline{z}}u=0$ in $\Omega$
$\implies\quad \text{ d}u=\partial_{z}u dz$

Some observations:
* $dz\to \text{ d}u$ is a rotation and dilation
	$\partial_{z}u=e^{i \mathcal{O} }\lvert \partial_{z}u \rvert$
	if $P_{z}u≠0$ then u is **conformal**
* We can think of $u:\mathbb{R}^{2}\to \mathbb{R}^{2}$, so we can compute the Jacobian
	$u=f+ig$ the map is $(x,y)\to (f,g)$
	Then the Jacobian is $J= det\begin{bmatrix}f_{x} & f_{y} \\ g_{x} & g_{y}\end{bmatrix}= \lvert f_{x}g_{y}-f_{y}g_{x} \rvert$
	Cauchy-Riemann equations:
$$\begin{align*}
\partial_{\overline{z}}u =0 \quad\Leftrightarrow\quad (\partial_{x}+i \partial_{y})(f+ig)&= 0\\
(f_{x}-g_{y})+i(f_{y}+g_{x})&= 0\\
f_{x}=g_{y} \quad f_{y}=-g_{x}
\end{align*}$$
	then the Jacobian is
$$J= f_{x}^{2}+g_{x}^{2}= \lvert \partial_{z}u \rvert^{2}$$

## Jordan curve
If we take some reagion $\omega$ and a boundary $\gamma =\partial_{}\omega$,
then the boundary is a Jordan curve if
$t\to z(t), \qquad t=[a,b], \quad z(a)=z(b)$ and
for any $t_{1},t_{2}$ such that $a<t_{1}<t_{2}<b$ and $z(t_{1})=z(t_{2}) \quad\implies\quad t_{1}= t_{2}$
#insert omega gamma

Greens formula:
	$\int_{\omega }\text{d}\alpha =\int_{\gamma. }\alpha$    where $\alpha =a \text{ d}x+ b \text{ d}y$    and $\text{d } \alpha =(b_{x}-a_{y})\text{ d}x \text{ d}y$


Using greens,
$v \in C^{1}(\overline{\omega }) \quad \alpha =v dz \qquad$
$$\begin{align*}
d \alpha &=  v \text{ d}x+i v \text{ d}y\\
&= v_{y}\text{ d}y \text{ d}x+ i v_{x}\text{ d}x \text{ d}y\\
&= i(v_{x}+i v_{y}) \text{ d}x \text{ d}y\\
&= 2i \partial_{\overline{z}}v \text{ d}x \text{ d}y
\end{align*}$$
The other way:
$d \overline{z} dz= (\text{ d}x-i \text{ d}y)(\text{ d}x+i \text{ d}y)=i \text{ d}x \text{ d}y-i \text{ d}y \text{ d}x = 2i \text{ d}x \text{ d}y$
#review
$d \alpha =\partial_{\overline{z}}v d \overline{z}dz$


So
$\alpha = vdz , \quad d \alpha = 2i \partial_{\overline{z}}v \text{ d}x A \text{ d}y$
$$\int_{\partial}\alpha = \int_{\omega }d \alpha \quad\implies\quad \int_{\gamma v}dz = 2i \int_{\omega }\partial_{\overline{z}}v \text{ d}xdy \tag{*}$$

### Cauchy-Greens formula
for $u \in C^{1}(\Omega ), \quad \omega \in \Omega , \quad \partial_{}w = \gamma$
$\mathcal{s} \in \Omega$
$$u(\xi )= \frac{1}{2 \pi i} \int_{\gamma } \frac{u(z)}{z-\xi }dz + \frac{1}{\pi} \int_{\omega} \frac{\partial_{\overline{z}}u}{z-\xi} \text{ d}x\text{ d}y$$
if u holomorfic $\partial_{\overline{z}}u =0$ then the second term vanishes
#### Proof

Apply (*) with $v(z)=\frac{u(z)}{z- \xi}$ and $\tilde{\omega }= \omega \backslash D(\xi , \epsilon )$ for $0<\epsilon <<1$
#insert doughnut
$\partial_{\overline{z}}v=\partial_{\overline{z}} \left(\frac{1}{z-\xi }\right)u(z) + \frac{1}{z-\xi }\partial_{\overline{z}}u(z)$

$$\int_{\gamma } \frac{u(z)}{z-\xi }- \int_{\partial D(\xi ,\epsilon)} \frac{u(z)dz}{z-\xi }= 2i\int_{\omega \backslash D(\xi ,\epsilon )} \frac{\partial_{\overline{z}}u}{z-\xi }\text{ d}x \text{ d}y$$
$$\int_{\gamma }\frac{u(z)}{z-\xi }dz- 2\pi iu(\xi )= 2i\int_{\omega } \frac{\partial_{\overline{z}}u}{z- \xi }\text{ d}xdy $$
since the second term is $\int_{0}^{2\pi }u(\xi +\epsilon e^{i \theta })i d \theta$
third term
$z\to \frac{1}{z -\xi }\in L^{1}(\mathbb{C}) \qquad z= \xi + \Gamma e^{i \theta }$
$$\frac{1}{| z-\xi  |}= \frac{1}{\gamma} \int_{| z-\xi  |<R}=\int_{r<R} \frac{1}{\gamma } \gamma dr d \theta$$

$\mu$ a measure on $\mathbb{C}$ if $supp \mu \subset \mathbb{C}$ 