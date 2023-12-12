![[Pasted image 20231212114319.png]]


![[Pasted image 20231207143523.png|800]]
$$W^{1,2}(U)=\{u \in \mathcal{D}'(U): \quad D^{\alpha }u\in L^{2}(U)\quad\forall\quad \alpha ,\lvert \alpha  \rvert \le1 \}$$
First, let's show that $u \in L^{2}$.
$$\begin{align*}
\int_{B_{1}(0)}\left\lvert \text{log}\left(\text{log}\left(2+ \frac{1}{\lvert x \rvert} \right) \right) \right\rvert^{2}\text{ d}x&= \int_{0}^{1}\int_{0}^{2\pi }\text{log}^{2}\left(\text{log}\left(2+ \frac{1}{r} \right) \right)r \text{ d}\theta \text{ d}r\\
&= 2\pi \int_{0}^{1} r \cdot \text{log}^{2}\left(\text{log}\left(2+ \frac{1}{r} \right) \right) \text{ d}r
\end{align*}$$
as $r\to 0$, we get a singularity inside the log, but the linear term $r$ decreases faster than the nested logarithms. Therefore, the integral is finite


Writing the partial derivative
$$\begin{align*}
\partial_{x^{i}} u(x)&= \frac{1}{\text{log}\left(2+\frac{1}{\lvert x \rvert} \right)} \cdot \frac{1}{2+\frac{1}{\lvert x \rvert}}\cdot \partial _{x^{i}}\left(\frac{1}{ \sqrt{(x^{1})^{2}+(x^{2})^{2}}} \right)\\
&= \frac{1}{\text{log}\left(2+\frac{1}{\lvert x \rvert} \right)} \cdot \frac{1}{2+\frac{1}{\lvert x \rvert}}\cdot(-1/2)\cdot ((x^{1})^{2}+(x^{2})^{2})^{-3/2} \cdot 2x^{i}\\
&= -\frac{1}{\text{log}\left(2+\frac{1}{\lvert x \rvert} \right)} \cdot \frac{x^{i}}{\lvert x \rvert^{2}(2 \lvert x \rvert+1)}
\end{align*}$$
We need to check that
$$\int_{B_{1}(0)}\left\lvert \frac{1}{\text{log}\left(2+\frac{1}{\lvert x \rvert} \right)} \cdot \frac{x^{i}}{\lvert x \rvert^{2}(2 \lvert x \rvert+1)} \right\rvert^{2}\text{ d}x<\infty.$$
Let's say that $i=1$, and let's switch to polar coordinates,
$$\begin{align*}
\int_{0}^{1}\int_{0}^{2\pi }\frac{1}{\text{log}^{2}\left(2+ \frac{1}{r} \right)}\frac{\lvert r \text{cos}\theta \rvert^{2} }{r^{4}(2r+1)^{2}}r \text{ d}\theta \text{ d}r &\le 2\pi \int_{0}^{1}\frac{1}{r(2r+1)^{2}\cdot \text{log}^{2}\left(2+ \frac{1}{r} \right)}\text{ d}r\\
	&\le C \int_{0}^{1} \frac{1}{r\text{log}^{2}\left(2+\frac{1}{r} \right)}\text{ d}r\\
	&\le C' \int_{0}^{1}\frac{1}{r}\text{ d}r\\
&< \infty
\end{align*}$$
So $u \in  W^{1,2}(U)$ but clearly $\lim_{x \to 0}u(x)\to \infty$ so $u \notin L^{\infty}(U)$. 

<div style="page-break-after: always;"></div>

![[Pasted image 20231207143537.png|800]]
Assuming $u$ is Hölder of order $\alpha >1$, we can rewrite this as
$$\begin{align*}
\lvert u(x)-u(y) \rvert&\le  C \lvert x-y \rvert^{\alpha }\\
\frac{\lvert u(x)-u(y) \rvert}{\lvert x-y \rvert} &\le C \lvert x-y \rvert^{1-\alpha }.
\end{align*}$$
The directional derivative in direction $v$ with 
$$D_{v} u(x) =\lim_{h \to 0}\frac{u(x+hv)-u(x)}{h}$$
Let's call $y=x+hv$. Then, $h=\lvert y-x \rvert/\lvert v \rvert=\lvert y-x \rvert$ and
$$\begin{align*}
\lvert D_{v}u(x) \rvert &\le \lim_{y \to x}\frac{\lvert u(y)-u(x) \rvert}{\lvert y-x \rvert}\\
&\le \lim_{y \to x} C \lvert y-x \rvert^{1-\alpha }\\
&= 0
\end{align*}$$
since $\alpha > 1$. $x$ and $v$ were arbitrary, so the directional derivative in each direction in every points in $U$ is zero. Hence, $u=$const.