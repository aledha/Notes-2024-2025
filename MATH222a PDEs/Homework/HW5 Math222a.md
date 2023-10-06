By Alexander Hatle
![[Pasted image 20231001160039.png|800]]
Let's use the derivative estimate
$$\begin{align*}
\lvert D^{\alpha }u(x) \rvert &\le \frac{C_{k}}{r^{d+\lvert \alpha  \rvert}} \lVert u \rVert_{L^{1}(B_{x,r})}\\
&\le \frac{C_{k}}{r^{d+\lvert \alpha \rvert } }\int_{B_{x,r}} C(1+\lvert y \rvert^{2})^{\frac{q}{2}} \text{ d}y\\
	&\le  \frac{C'}{r^{d+\lvert \alpha \rvert }} r^{d}(1+r^{2})^\frac{q}{2}\\
&\le C' \cdot r^{q-\lvert \alpha  \rvert }+\text{lower order terms}.
\end{align*}$$
Suppose that $\lvert \alpha  \rvert=\lfloor q \rfloor+1$. Then we have that $\lvert D^{\alpha }u(x) \rvert \le C'r^{q-\lfloor q \rfloor -1}\to0$ as $r\to \infty$. 

Since this is zero, it implies that $u$ must be a polynomial of degree at most $\lfloor q \rfloor$. 

![[Pasted image 20231001160132.png|800]]

![[Pasted image 20231001160212.png|800]]


![[Pasted image 20231001160224.png|800]]

![[Pasted image 20231001160239.png|800]]

$$-\Delta v=f\le0$$
Lemma 4.9:
Let $\tilde E_{0}$ be a fundamental solution for $-\Delta$ at 0. Then 
$$\begin{align*}
v(x)&= \int_{B_{r}(x)}\tilde E_{0}(x-y)(-\Delta v)(y)\text{ d}y-\int_{\partial B_{r}(x)}\nu (y) \cdot D_{y} \tilde E_{0}(x-y)v(y) \text{ d}S(y)\\
&+\int_{\partial B_{r}(x)}\tilde E_{0}(x-y)\nu (y) \cdot Dv(y) \text{ d}S(y)
\end{align*}$$



$$\int_{B_{r}(x)}v \text{ d}y=\int_{B_{r}(x)}$$

![[Pasted image 20231005160105.png]]
![[Pasted image 20231001160346.png|800]]

![[Pasted image 20231001160423.png|800]]