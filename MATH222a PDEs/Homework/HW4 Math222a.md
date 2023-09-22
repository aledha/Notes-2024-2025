![[Pasted image 20230918170036.png]]
![[Pasted image 20230921155232.png|600]]
Let 
$$\left\langle u_{n} \text{ , } \varphi  \right\rangle=\sum_{j=0}^{n}\partial_{x}^{j}\varphi (j),$$
which is a distribution since it is bounded: For any compact $K \subset  \mathbb{R}$, there exists $N$ and $C$ such that for all $\varphi \in C^{\infty}_{c}(\mathbb{R})$ with $\text{supp }\varphi \subseteq K$, we have
$$\begin{align*}
\lvert \left\langle u_{n} \text{ , } \varphi  \right\rangle \rvert &\le C \sum_{\lvert \alpha  \rvert \le N}^{}\sup_{x \in K}\lvert D^{\alpha } \varphi (x)\rvert\\
	\left\lvert \sum_{j=0}^{n}\partial_{x}^{j}\varphi (j) \right\rvert &\le C \sum_{\lvert \alpha  \rvert \le N}^{}\sup_{x \in K}\lvert D^{\alpha } \varphi (x)\rvert
\end{align*}$$
which is obviously true for $C=1$ and $N=n$.

Since $\phi \in C^{\infty}_{c}$, $\left\langle u_{n} \text{ , } \varphi  \right\rangle$ must converge. Then (by theorem 3.16) there exists a a distribution $u$ such that
$$\begin{align*}
\left\langle u \text{ , } \varphi  \right\rangle&= \lim_{n \to \infty}\left\langle u_{n} \text{ , } \varphi  \right\rangle\\
		&= \sum_{j=0}^{\infty}\partial_{x}^{j}\varphi (j),
\end{align*}$$
which is the what we started with. $u$ is a distribution.

![[Pasted image 20230918170043.png]]

![[Pasted image 20230921155733.png|600]]

![[Pasted image 20230918170027.png]]

![[Pasted image 20230921161518.png|600]]
For all $\varphi \in C^{\infty}_{c}(\mathbb{R}),$ we have
$$\begin{align*}
\left\langle \partial_{x}(x \mathbb 1_{(0,1)}(x)) \text{ , } \varphi  \right\rangle&= -\left\langle x \mathbb 1_{(0,1)}(x) \text{ , } \partial_{x} \varphi \right\rangle\\
\int_\mathbb{R}\partial_{x}(x \mathbb 1_{(0,1)}(x)) \varphi(x) \text{ d}x  &= -\int_{\mathbb{R}} x \mathbb 1_{(0,1)}(x)\partial_{x}\varphi (x) \text{ d}x\\
	&= -\int_{0}^{1}x \partial_{x}\varphi (x) \text{ d}x\\
&= - \left[x \varphi (x) \right]_{0}^{1}+\int_{0}^{1}\varphi (x) \text{ d}x\\
&= \int_{0}^{1}\varphi (x) \text{ d}x-\varphi  (1)\\
&= \int_\mathbb{R} \varphi (x)(\mathbb 1_{(0,1)}(x)-\delta _{1}(x)) \text{ d}x\\
&= \left\langle \mathbb 1_{(0,1)}-\delta _{1} \text{ , } \varphi  \right\rangle
\end{align*}$$
Hence, the distributional derivative is
$$u(x)=\mathbb 1_{(0,1)}(x)-\delta _{1}(x),$$
which is locally integrable and defined on $\mathbb{R}$.

![[Pasted image 20230918170053.png]]
For all $\varphi \in C^{\infty}_{c}(\mathbb{R}),$ we have
$$\begin{align*}
\left\langle \partial_{x}\lvert x \rvert^{-\alpha } \text{ , } \varphi  \right\rangle&= -\int_\mathbb{R} \lvert x \rvert^{-\alpha }\partial_{x}\varphi (x) \text{ d}x\\
&= -\left(\int_{0}^{\infty} x^{-\alpha }\partial_{x}\varphi (x)\text{ d}x-\int_{-\infty}^{0}x^{-\alpha }\partial_{x} \varphi (x) \text{ d}x \right)\\
&= -\bigg(\left[x^{-\alpha }\varphi (x) \right]_{0}^{\infty}-\int_{0}^{\infty}-\alpha x^{-\alpha -1}\varphi (x) \text{ d}x \\
&\phantom{=-\bigg() } -\left[x^{-\alpha }\varphi (x) \right]_{-\infty}^{0}+\int_{-\infty}^{0}-\alpha x^{-\alpha -1}\varphi (x)\text{ d}x \bigg)
\end{align*}$$
Since $-1<\alpha <0$,  $\lim_{x \to 0}x^{-\alpha }=0$. This, in combination with the fact that $\lim_{x \to \pm \infty}\varphi(x)=0$, our expression becomes
$$\begin{align*}
\left\langle \partial_{x}\lvert x \rvert^{-\alpha } \text{ , } \varphi  \right\rangle&=- \left(\int_{0}^{\infty}\alpha x^{-\alpha -1}\varphi (x)\text{ d}x-\int_{-\infty}^{0}\alpha x^{-\alpha -1}\varphi (x)\text{ d}x \right)\\

\end{align*}$$
These integrals contain the singularity $x^{-\alpha -1}$, so we must write this as
$$\begin{align*}
\left\langle \partial_{x}\lvert x \rvert^{-\alpha } \text{ , } \varphi  \right\rangle&=- \left(\int_{\epsilon }^{\infty}\alpha x^{-\alpha -1}\varphi (x)\text{ d}x-\int_{-\infty}^{0}\alpha x^{-\alpha -1}\varphi (x)\text{ d}x \right)\\

\end{align*}$$


$$\begin{align*}
&= \int_\mathbb{R}-\alpha \lvert x \rvert^{-\alpha -1}\varphi (x) \text{ d}x \\
&= \left\langle -\alpha \lvert \cdot  \rvert^{-\alpha -1} \text{ , } \varphi  \right\rangle
\end{align*}$$
![[Pasted image 20230918170102.png]]

![[Pasted image 20230918170109.png]]

![[Pasted image 20230918170115.png]]

![[Pasted image 20230918170122.png]]

![[Pasted image 20230918170128.png]]


![[Pasted image 20230918170133.png]]

![[Pasted image 20230918170138.png]]