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
Lemma 4.9:
Let $\tilde E_{0}$ be a fundamental solution for $-\Delta$ at 0. Then 
$$\begin{align*}
v(x)&= \int_{B_{r}(x)}\tilde E_{0}(x-y)(-\Delta v)(y)\text{ d}y-\int_{\partial B_{r}(x)}\nu (y) \cdot D_{y} \tilde E_{0}(x-y)v(y) \text{ d}S(y)\\
&+\int_{\partial B_{r}(x)}\tilde E_{0}(x-y)\nu (y) \cdot Dv(y) \text{ d}S(y)
\end{align*}$$
We can decide that $\tilde E_{0}(y)=E_{0}(\lvert y \rvert)-E_{0}(r)$, meaning that $\tilde E_{0}$ vanishes on the sphere $\partial B_{r}(x)$, and that the third term will vanish. The difference between this proof and the proof for mean-value property is that the first term,
$$\int_{B_{r}(x)} (E_{0}(\lvert x-y \rvert) -E_{0}(r))(-\Delta v)(y) \text{ d}y,$$
does not vanish.
The fundamental solution is
![[Pasted image 20231005214154.png]]
Since $\lvert x-y \rvert \le r$, we have that in the $d=2$ case
$$- \frac{1}{2\pi }\text{log} \lvert x-y \rvert \ge - \frac{1}{2\pi }\text{log}r,$$
and that in the $d \ge 3$ case
$$ \frac{1}{d(d-2)\alpha (d)} \frac{1}{\lvert x-y \rvert^{d-2}}\ge \frac{1}{d(d-2)\alpha (d)}\frac{1}{r^{d-2}}.$$
Thus $E_{0}(\lvert x-y \rvert)\ge E_{0}(r)$, and $E_{0}(\lvert x-y \rvert)-E_{0}(r)$ is positive. This, in combination with that $-\Delta v \le 0$, makes the the first integral negative. Then,
$$\begin{align*}
v(x) &\le -\int_{\partial B_{r}(x)}\nu (y) \cdot D_{y} \tilde E_{0}(x-y)v(y) \text{ d}S(y)\\
		&\le -\int_{\partial B_{r}(x)}\frac{y-x}{r} \cdot \left(-\frac{x-y}{r}E'_{0}(r) \right)v(y) \text{ d}S(y)\\
&\le \int_{\partial B_{r}(x)}-E_{0}'(r)v(y) \text{ d}S(y)
\end{align*}$$
Since $E'_{0}(r)= -\frac{1}{\lvert \partial B_{r}(x) \rvert}$, we have
$$v(x) \le \frac{1}{\lvert \partial B_{r}(x) \rvert}\int_{\partial B_{r}(x)}v(y)\text{ d}S(y).$$
Using this inequality,
$$\int_{B_{r}(x)}v(y) \text{ d}y=\int_{0}^{r}\int_{\partial B_{r'}(x)} v(y) \text{ d}S(y) \text{ d}r'\ge v(x)\int_{0}^{r}\int_{\partial B_{r'}(x)} \text{ d}S(y),$$
and our final result is
$$v(x) \le \frac{1}{\lvert B_{r}(x) \rvert}\int_{B_{r}(x)}v(y) \text{ d}y.$$
![[Pasted image 20231001160346.png|800]]
This proof is very similar to the one in the lecture notes, the only difference is replacing the equality in the mean-value property with the inequality we just proved.

Suppose that $v$ attains a maximum at a point $x_{0}\in U$, i.e. $v(x_{0})=\max_{\overline{U}}v$. 
Then,
$$V=\{x \in U:v(x)=\max_{\overline{U}}v \}$$
is nonempty closed subset of $U$. 

Using the inequality we proved in the last problem, and for any $x_{0}\in V$ (i.e. $v(x_{0})=\max_{\overline{U}}v$), we have
$$\begin{align*}
v(x_{0}) &\le \frac{1}{\lvert B_{r}(x_{0}) \rvert} \int_{B_{r}(x)}v(y) \text{ d}y\\
0 &\le \frac{1}{\lvert  B_{r}(x_{0}) \rvert} \int_{B_{r}(x)}(v-\max_{\overline{U}}v) \text{ d}y.
\end{align*}$$
Clearly, $v-\max_{\overline{U}}v\le 0$. As the integral must be nonnegative, it follows that $v=\max_{\overline{U}}v$ in $B_{r}(x)$, meaning that $B_{r}(x)\subset V$.

![[Pasted image 20231001160423.png|800]]