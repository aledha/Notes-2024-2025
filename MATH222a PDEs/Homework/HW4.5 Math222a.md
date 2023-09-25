![[Pasted image 20230924194640.png]]
For any $\phi \in C^{\infty}_{c}(\mathbb{R})$, $\phi (x)=\phi (0)+x \psi (x)$ 
Denote a cutoff $\chi  \in \mathbb{C}^{\infty}_{c}(\mathbb{R})$ such that $\chi =1$ on $\text{supp }\phi$.
$$\begin{align*}
\left\langle u \text{ , } \phi  \right\rangle&= \left\langle u \text{ , } \chi \phi (0)+ \chi x \psi \right\rangle\\
&= \left\langle u \text{ , } \chi \phi (0) \right\rangle + \left\langle u \text{ , } \chi x \psi  \right\rangle\\
&= \phi (0)\cdot \left\langle u \text{ , } \chi \right\rangle+\left\langle ux \text{ , } \chi \psi  \right\rangle\\
&= \phi (0) \cdot \left\langle u \text{ , } \chi  \right\rangle\\
&= \phi (0) \cdot c \qquad\text{for some }c \in \mathbb{R}\\
\left\langle u \text{ , } \phi  \right\rangle&= \left\langle c\delta _{0} \text{ , } \phi  \right\rangle
\end{align*}$$

![[Pasted image 20230924194646.png]]
$$\lim_{n \to \infty} \left\langle u_{n}(x-y) \text{ , } \phi (x,y) \right\rangle=\lim_{n \to \infty}\int \int u_{n}(x-y) \phi (x,y) \text{ d}x \text{ d}y$$
For each fixed $y$,
$$\lim_{n \to \infty}\int u_{n}(x-y)\phi (x,y) \text{ d}x=\int \delta _{0}(x-y)\phi (x,y)\text{ d}x=\phi (y,y)$$

$$\lim_{n \to \infty} \left\langle u_{n}(x-y) \text{ , } \phi (x,y) \right\rangle=\int \phi (y,y)\text{ d}y$$


![[Pasted image 20230924194652.png]]
$$\begin{align*}
\left\langle \partial_{x^{j}}^{2}\int G(x,y)f(y) \text{ d}y \text{ , } \phi(x)  \right\rangle&=  \left\langle \int G(x,y)f(y) \text{ d}y \text{ , } \partial_{x^{j}}^{2}\phi (x) \right\rangle\\
&= \int\left(\int G(x,y)f(y) \text{ d}y\right)\partial_{x^{j}}^{2}\phi (x) \text{ d}x\\
&= \int\int G(x,y)f(y) \partial_{x^{j}}^{2}\phi (x) \text{ d}y \text{ d}x\\
&= \left\langle \partial_{x^{j}}^{2}G(x,y) \text{ , } f(y)\phi (x) \right\rangle
\end{align*}$$
Summing,
$$\begin{align*}
\left\langle -\Delta  \int G(x,y)f(y) \text{ d}y \text{ , } \phi (x) \right\rangle&= \left\langle -\Delta  G(x,y) \text{ , } f(y)\phi (x) \right\rangle\\
&= \left\langle \delta _{0}(x-y) \text{ , } f(y)\phi (x) \right\rangle\\
&= \int\int \delta _{0}(x-y)f(y)\phi (x) \text{ d}x \text{ d}y\\
&= \int f(y)\phi (y) \text{ d}y\\
&= \left\langle f(x) \text{ , } \phi(x)  \right\rangle
\end{align*}$$
which was the first assertion.

$$\begin{align*}
	\left\langle \int G(x,y) \partial_{y^{j}}^{2}u(y) \text{ d}y \text{ , } \phi (x) \right\rangle&= \int\int G(x,y) \partial_{y^{j}}^{2}u(y)\phi (x) \text{ d}y \text{ d}x\\
	&= \left\langle G(x,y)\phi (x) \text{ , } \partial_{y^{j}}^{2}u(y)  \right\rangle\\
&=  \left\langle \partial_{y^{j}}^{2}G(x,y) \phi (x) \text{ , } u(y) \right\rangle\\
\left\langle \int G(x,y) (-\Delta )u(y) \text{ d}y \text{ , } \phi (x) \right\rangle&=\left\langle -\Delta G(x,y) \phi (x) \text{ , } u(y) \right\rangle\\
&=  \left\langle \delta _{0}(x-y)\phi (x) \text{ , } u(y) \right\rangle\\
&= \int\int \delta _{0}(x-y) \phi (x) u(y) \text{ d}x \text{ d}y\\
&= \int \phi (y) u(y) \text{ d}y\\
&= \left\langle u(x) \text{ , } \phi (x) \right\rangle
\end{align*}$$



![[Pasted image 20230924194700.png]]


![[Pasted image 20230924194707.png]]