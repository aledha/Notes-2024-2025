
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
![[Pasted image 20230924180451.png]]
![[Pasted image 20230924180501.png]]




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
Hence, the distributional derivative agrees with
$$u(x)=\mathbb 1_{(0,1)}(x)-\delta _{1}(x),$$
on $\mathbb{R}\backslash \{1 \}$.

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
\left\langle \partial_{x}\lvert x \rvert^{-\alpha } \text{ , } \varphi  \right\rangle&=- \int_{-\infty}^{\infty}\alpha \lvert x \rvert^{-\alpha -1}\varphi (x)\text{ d}x\
\end{align*}$$
So the dist. derivative agrees with $-\alpha \lvert x \rvert^{-\alpha -1}$ in the open set $(-\infty,1)\cup(1,\infty)$.

**Professor meant to ask about $0<\alpha <1$**
![[Pasted image 20230924181843.png]]
![[Pasted image 20230924181852.png]]


![[Pasted image 20230918170102.png]]
$$\begin{align*}
\left\langle Du \text{ , } \varphi  \right\rangle&= \int \partial_{x^{1}}\frac{x^{1}}{(x^{1})^{2}+(x^{2})^{2}}\varphi (x^{1},x^{2})\text{ d}A\\
& +\int\partial_{x^{2}} \frac{x^{2}}{(x^{1})^{2}+(x^{2})^{2}}\varphi (x^{1},x^{2})\text{ d}x^{1}\text{ d}A\\
&= \int_{0}^{2\pi }\int_{0}^{\infty} \partial_{r \text{cos}\theta } \frac{r \text{ cos}\theta }{r^{2}} r \varphi (r,\theta )\text{ d}r \text{ d}\theta \\

\end{align*}$$

```ad-note
title: Solution
![[Pasted image 20230924182348.png]]
![[Pasted image 20230924182358.png]]

```
$$\partial_{x^{1}}\frac{x^{1}}{(x^{1})^{2}+(x^{2})^{2}}+ \partial_{x^{2}}\frac{x^{2}}{(x^{1})^{2}+(x^{2})^{2}}$$
$$=\frac{1}{(x^{1})^{2}+(x^{2})^{2}}- \frac{2(x^{1})^{2}}{((x^{1})^{2}+(x^{2})^{2})^{2}}+\frac{1}{(x^{1})^{2}+(x^{2})^{2}}- \frac{2(x^{2})^{2}}{((x^{1})^{2}+(x^{2})^{2})^{2}}$$
$$\frac{2((x^{1})^{2}+(x^{2})^{2} -(x^{1})^{2}-(x^{2})^{2})}{((x^{1})^{2}+(x^{2})^{2})^{2}}=0$$


![[Pasted image 20230918170109.png]]
$$\begin{align*}
\left\langle \text{p.v.} \frac{\mathbb 1_{(0,\infty)} }{x}\text{ , } \varphi  \right\rangle&= -\int_{-\infty}^{\infty} \mathbb 1_{(0,\infty)}\text{log}\lvert x \rvert\varphi  '(x) \text{ d}x\\
&= -\int_{0}^{\infty} \text{log}x \cdot (\varphi(x)-\varphi (0))' \text{ d}x\\
&= -\left[\text{log}x (\varphi (x)-\varphi (0)) \right]_{0}^{\infty}+\int_{0}^{\infty} \frac{1}{x}(\varphi (x)-\varphi (0)) \text{ d}x
\end{align*}$$
```ad-note
title: Solution
collapse: closed
![[Pasted image 20230924183338.png]]
![[Pasted image 20230924183350.png]]

```





![[Pasted image 20230918170115.png]]
```ad-note
title: Solution
collapse: closed
![[Pasted image 20230924183855.png]]
![[Pasted image 20230924183910.png]]
![[Pasted image 20230924183918.png]]
![[Pasted image 20230924183928.png]]

```


![[Pasted image 20230918170122.png]]
```ad-note
title: Solution
collapse: closed
![[Pasted image 20230924192740.png]]
![[Pasted image 20230924192746.png]]

```


![[Pasted image 20230918170128.png]]
```ad-note
title: Solution
collapse: closed
![[Pasted image 20230924193632.png]]

```


![[Pasted image 20230918170133.png]]
```ad-note
title: Solution
collapse: closed
![[Pasted image 20230924193752.png]]
![[Pasted image 20230924193802.png]]

```



![[Pasted image 20230918170138.png]]

```ad-note
title: Solution
collapse: closed
![[Pasted image 20230924194153.png]]
![[Pasted image 20230924194200.png]]

```
