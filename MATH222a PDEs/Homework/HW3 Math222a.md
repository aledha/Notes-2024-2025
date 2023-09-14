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
Since $A$ is positive definite, the first term is convex. The second term is also convex.
Another result of $A$ being positive definite is that 
$$\lim_{\lVert p \rVert \to \infty} \frac{1}{2 \lVert p \rVert} p^{T}Ap \to \infty,$$
because the quadratic is always positive. Therefore
$$\lim_{\lVert p \rVert \to \infty} \frac{H(p)}{\lVert p \rVert}\to \infty,$$
since the quadratic term will dominate the linear term.

Now that we know that the transform exists, let's compute it.
$$\begin{align*}
H^{*}(v)&=  \sup_{p \in \mathbb{R}^{d}}\left\{ p^{T}v - H(p) \right\}\\
	&= \sup_{p \in \mathbb{R}^{d}} \left\{ p^{T}(v-b)- \frac{1}{2}p^{T}Ap \right\}
\end{align*}$$
Differentiating with respect to $p$ and setting the expression equal to zero,
$$D_{p}\left(p^{T}(v-b)- \frac{1}{2}p^{T}Ap \right)=v-b- \frac{1}{2}(A+A^{T})p=0 \quad \stackrel{A \text{ sym.}}{\implies}\quad p=A^{-1}(v-b)^.$$
Putting this back into our expression,
$$\begin{align*}
H^{*}(v)&= (v-b)^{T}A^{-T}(v-b)- \frac{1}{2}(v-b)^{T}A^{-T}AA^{-1}(v-b)\\
H^{*}(v)&= (v-b)^{T}A^{-1}(v-b) - \frac{1}{2}(v-b)^{T}A^{-1}(v-b)\\
H^{*}(v)&= \frac{1}{2} (v-b)^{T}A^{-1}(v-b)
\end{align*}$$

![[Pasted image 20230912152506.png]]
#ask what does it mean that $p \in \partial_{}f(v)$ and $v \in f^{*}(p)$? 


![[Pasted image 20230912152515.png]]



![[Pasted image 20230912152525.png]]
#ask  am I supposed to show that the $y \in \mathbb{R}^{d}$ that minimises the expression has to be in $B_{Rt}(x)$?

![[Pasted image 20230912152533.png]]
