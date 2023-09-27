Alexander Hatle
![[Pasted image 20230917195556.png]]
Assume a function $f$ on $\mathbb{R}^{n}$ satisfies $\lvert f(x) \rvert \le \frac{C}{(1+\lvert x \rvert)^{n+\delta  }}$ and $\lvert \hat f(\xi  ) \rvert \le \frac{C}{(1+\lvert \xi  \rvert)^{n+\delta }}$ with constants $C,\delta >0$. Assume further that $f$ and $\hat f$ are both continous. Prove the Poisson summation formula
$$\begin{align*}
\sum_{k \in \mathbb Z^{n}} f(k)&= \sum_{m \in \mathbb Z^{n}}\hat f(m)\\
&= \sum_{m \in \mathbb Z^{n}} \int f(x) e^{-2\pi ix \cdot m } \text{ d}x
\end{align*}$$
Let $f(x)=f_{1}(x)+\dots +f_{s}(x)$ such that each $f_{i}$ is compactly supported in a subset $K_{i}$. Then


![[Pasted image 20230906123326.png]]

![[Pasted image 20230906123356.png]]

![[Pasted image 20230906123451.png]]

![[Pasted image 20230906123425.png]]