![[Pasted image 20230912152454.png]]
Note that $f$ is convex, and therefore $-f$ is concave and that $\lim_{\lvert v \rvert \to \infty} \frac{f(v)}{\lvert v \rvert}=\lim_{\lvert v \rvert \to \infty} \frac{1}{q} \lvert v \rvert^{q-1}\to +\infty \quad\text{for }q>1$, so the Legendre transform exists if $q>1$.
Definition of the Legendre transform:
$$\begin{align*}
f^{*}(p)&=  \sup_{v \in \mathbb{R}}\left\{ p \cdot v-f(v) \right\}\\
	&= \sup_{v \in \mathbb{R}} \left\{ p \cdot v - \frac{1}{q}\lvert v \rvert^{q} \right\}
\end{align*}$$
Note that, if $p \le 0$, then $f^{*}(p)=0$.

Let's compute what $f^{*}(p)$ is for $p>0$.
We see immediately that $v \ge 0$, since any negative $v$ would result in both terms being $<0$. Then we can remove the absolute value,
$$f^{*}(p)= \sup_{v \in \mathbb{R}}\left\{ p \cdot v - \frac{1}{q}v^{q} \right\}.$$
We can differentiate with respect to $v$ to find the critical point
$$\frac{\text{d}}{\text{d}v}\left(pv- \frac{1}{q}v^{q}\right)=p-v^{q-1}=0 \quad\implies\quad v= p^{\frac{1}{q-1}}$$
Thus, our transformed function is
$$\begin{align*}
f^{*}(p)&= pp^{\frac{1}{q-1}}- \frac{1}{q} (p^{\frac{1}{q-1}})^{q}\\
&= p^{\frac{q}{q-1}}- \frac{1}{q}p^{\frac{q}{q-1}}\\
&= \frac{q-1}{q}p^{\frac{q}{q-1}}\\
f^{*}(p)&= \frac{1}{\alpha }p^{\alpha },
\end{align*}$$
where $\alpha = \frac{q}{q-1}$. Covering all the cases, our final result is
$$f^{*}(p)=\begin{cases}
\frac{1}{\alpha }p^{\alpha } & \quad\text{for }p>0, \\
0 & \quad\text{else}.
\end{cases}$$
With the restriction that $q>1 \quad\implies\quad \alpha \in (0,\infty)$.


![[Pasted image 20230912152500.png]]
First, note that 
$$H(p)= \frac{1}{2}\sum_{i,j=1}^{d}a^{ij}p_{i}p_{j}+ \sum_{i=1}^{d}b^{i}p_{i}= \frac{1}{2}p^{T}Ap+ p^{T}b$$


$$H^{*}(v)= \sup_{p \in \mathbb{R}^{d}}\left\{ v \cdot p - H(p) \right\}$$

$$(Ap)_{i}=\sum_{j=1}^{d}a_{ij}p_{j}$$


![[Pasted image 20230912152506.png]]

![[Pasted image 20230912152515.png]]

![[Pasted image 20230912152525.png]]

![[Pasted image 20230912152533.png]]

