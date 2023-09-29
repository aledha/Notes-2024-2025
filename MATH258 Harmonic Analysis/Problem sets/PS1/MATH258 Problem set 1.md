How Alexander Hatle
![[Pasted image 20230917195556.png]]
Assume a function $f$ on $\mathbb{R}^{n}$ satisfies $\lvert f(x) \rvert \le \frac{C}{(1+\lvert x \rvert)^{n+\delta  }}$ and $\lvert \hat f(\xi  ) \rvert \le \frac{C}{(1+\lvert \xi  \rvert)^{n+\delta }}$ with constants $C,\delta >0$. Assume further that $f$ and $\hat f$ are both continous. Prove the Poisson summation formula
$$\begin{align*}
\sum_{k \in \mathbb Z^{n}} f(k)&= \sum_{m \in \mathbb Z^{n}}\hat f(m)\\
&= \sum_{m \in \mathbb Z^{n}} \int f(x) e^{-2\pi ix \cdot m } \text{ d}x
\end{align*}$$
Let $f(x)=f_{1}(x)+\dots +f_{s}(x)$ such that each $f_{i}$ is compactly supported in a subset $K_{i}$. Then

$$\sum_{m \in \mathbb Z^{n}}^{}\hat f(m)=\sum_{m \in \mathbb Z^{n}}^{}\int f(x) e^{-2\pi i x \cdot m}\text{ d}x$$
Since $f$ is bounded and continuous, the integrand is also bounded, and we can apply Fubini's theorem
$$\sum_{m \in \mathbb Z^{n}}^{}\hat f(m)=\int \sum_{m \in \mathbb Z^{n}}^{}f(x) e^{-2\pi ix \cdot m}\text{ d}x$$

$$\int_\mathbb{R}  \sum_{n=-\infty }^{\infty}\left\lvert2\pi ine^{2\pi inx}f(x-n)-e^{2\pi inx}f'(x-n)  \right\rvert\text{ d}x \le \int_\mathbb{R} \sum_{n=-\infty}^{\infty}2\pi \lvert n \rvert \frac{C}{(1+\lvert x -n\rvert)^{1+\delta }}$$


$$\int_\mathbb{R}  \sum_{n=-\infty }^{\infty}\left\lvert2\pi ine^{2\pi inx}f(x-n)  \right\rvert\text{ d}x \le \int_\mathbb{R} \sum_{n=-\infty}^{\infty}2\pi \lvert n \rvert \frac{C}{(1+\lvert x -n\rvert)^{1+\delta }}$$

$$\begin{align*}
\lvert 2\pi ine^{2\pi inx} \rvert&= \lvert 2\pi i n(\text{cos}(2\pi nx)+i \text{sin}(2 \pi n x)) \rvert= \lvert 2\pi i n \text{cos}(2\pi n x)-2\pi n\text{sin}(2\pi n x) \rvert\\
&= 2\pi n
\end{align*}$$

![[Pasted image 20230906123326.png]]

![[Pasted image 20230906123356.png]]

![[Pasted image 20230906123451.png]]

![[Pasted image 20230906123425.png]]