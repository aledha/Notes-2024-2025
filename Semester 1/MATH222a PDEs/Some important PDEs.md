Two simple, model PDEs
### 1 Laplace
$u: \mathbb{R}^{d}\to \mathbb{R}$
$\Delta u= \sum\limits_{i=1}^{d}\partial_{x^{i}}^{2}u$
$$\Delta u=0$$
* Elliptic PDE
	* Often represents an equilibrium

### 2 Wave eq
$u : \mathbb{R}_{t}\times \mathbb{R}_{x}^{d}\to \mathbb{R}$
$$-\partial_{t}^{2}u+\Delta u=0$$
* Hyperbolic PDE
	* Propagation of waves

### 3 Transport equation
$u: \mathbb{R}^{d}\to \mathbb{R}$,   $b: \mathbb{R}^{d}\to \mathbb{R}^{d}$ 
and $b = (b^{j})_{j=1,\dots ,d}$
$$b^{j}\partial_{j}u=0$$

### 4 Heat eq
$u: \mathbb{R}_{t}\times \mathbb{R}^{d} \to \mathbb{R}$
$$\partial_{t}u-\Delta u=0$$
* Parabolic PDE
	* Distribution of heat

### 5 Schrödinger equation
$u: \mathbb{R}_{t}\to \mathbb{R}_{x}^{d}\to \mathbb{C}$ 
$$i \partial_{t}u-\Delta u=0$$
* Dispersive PDE
	* Describes the wave function for a free particle
	* Wave on a pond