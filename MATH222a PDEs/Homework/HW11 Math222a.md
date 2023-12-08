![[Pasted image 20231207143513.png|800]]

![[Pasted image 20231207153913.png|600]]
![[Pasted image 20231207153950.png|600]]

![[Pasted image 20231207143523.png|800]]

![[Pasted image 20231207143530.png|800]]
As per the hint,
$$\int_{U}\lvert Du \rvert^{p}\text{ d}x = \sum_{i}^{}\int_{U}u_{x_{i}}u_{x_{i}}\lvert Du \rvert^{p-2}\text{ d}x$$


![[Pasted image 20231207143537.png|800]]

$$\begin{align*}
\frac{\lvert u(x)-u(y) \rvert}{\lvert x-y \rvert^{\alpha }}&\le  C\\
\frac{\lvert u(x)-u(y) \rvert}{\lvert x-y \rvert} &\le C \lvert x-y \rvert^{1-\alpha }
\end{align*}$$

$$D_{v} u(x) =\lim_{h \to 0}\frac{u(x+hv)-u(x)}{h}$$
Let's call $y=x+hv$. Then, $h=\lvert y-x \rvert/\lvert v \rvert=\lvert y-x \rvert$ and
$$\begin{align*}
\lvert D_{v}u(x) \rvert &\le \lim_{y \to x}\frac{\lvert u(y)-u(x) \rvert}{\lvert y-x \rvert}\\
&\le \lim_{y \to x} C \lvert y-x \rvert^{1-\alpha }\\
&= 0
\end{align*}$$
since $\alpha > 1$. $x$ and $v$ where arbitrary, so the directional derivative in each direction in every points in $U$ is zero. Hence, $u=$const.