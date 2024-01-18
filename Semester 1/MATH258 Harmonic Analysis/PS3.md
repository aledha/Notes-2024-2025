By Alexander Hatle

![[Pasted image 20231129160825.png|800]]
This follows Damian Dąbrowski's proof of lemma 4.12 in their paper "Singular Integral Operators", which can be found [here](https://www.damiandabrowski.eu/sios/SIOs-notes-19-11-2023.pdf).

Let $T=T_{1}-T_{2}$.
Let $E \subset \mathbb{R}^{n}$ with $\lvert E \rvert<\infty$, then notice that
$$T(\mathbb 1_{E})(x)=0 \quad\text{for }x \notin E$$
since the kernel of $T$ is $0$ away from the diagonal. Therefore, 
$$T (\mathbb 1_{E})=\mathbb 1_{E}T(\mathbb 1_{E}).$$

Let $F \subset \mathbb{R}^{n}$ with $\lvert F \rvert<\infty$, then using the linearity of $T$ and the formula above,
$$\begin{align*}
\mathbb 1_{F}T(\mathbb 1_{E})&= \mathbb 1_{E \cap F}T(\mathbb 1_{E})\\
\mathbb 1_{F}T(\mathbb 1_{E})&= \mathbb 1_{E\cap F}(T(\mathbb 1_{E \cap F})+T(\mathbb 1_{E \backslash F}))\\
\mathbb 1_{F}T(\mathbb 1_{E})&= 1_{E \cap F}T(\mathbb 1_{E\cap F})+\mathbb 1_{F\cap E}\mathbb 1_{E \backslash F}T(\mathbb 1_{E \backslash F})\\
\mathbb 1_{F}T(\mathbb 1_{E})&= 1_{E \cap F}T(\mathbb 1_{E\cap F}).\tag{*}
\end{align*}$$

Let $\{Q \}_{Q \in \mathcal{Q}}$ be the family of unit cubes tiling $\mathbb{R}^{n}$, and let $T(\mathbb 1_{Q})=a_{Q}$. Notice that $\text{supp }a_{Q}\subset Q$.
![[Pasted image 20231209145949.png|600]]
$$\begin{align*}
\lvert a_{Q}(x) \rvert&= \left\lvert \lim_{r \to 0^{+}} \frac{1}{\lvert B_{r} \rvert}\int_{B_{r}(0)}a_{Q}(x-y)\text{ d}y \right\rvert\\
&=  \lim_{r \to 0^{+}} \frac{1}{\lvert B_{r} \rvert}\left\lvert\int_{B_{r}(x)}a_{Q}(y)\text{ d}y \right\rvert\\
&=  \lim_{r \to 0^{+}} \frac{1}{\lvert B_{r}(x) \rvert}\left\lvert\int_{B_{r}(x)}(T(\mathbb 1_{Q}))(y)\text{ d}y \right\rvert\\
&=  \lim_{r \to 0^{+}} \frac{1}{\lvert B_{r}(x) \rvert}\left\lvert\int_{B_{r}(x)} \mathbb 1_{B_{r}(x)}(T(\mathbb 1_{Q}))(y)\text{ d}y \right\rvert\\
&\stackrel{(*)}{=}\lim_{r \to 0^{+}} \frac{1}{\lvert B_{r}(x) \rvert}\left\lvert\int_{B_{r}(x)} \mathbb 1_{Q\cap B_{r}(x)}T(\mathbb 1_{Q\cap B_{r}(x)})\text{ d}y \right\rvert\\
	&\le \lim_{r \to 0^{+}} \frac{1}{\lvert B_{r}(x) \rvert} \lVert \mathbb 1_{Q\cap B_{r}(x)} \rVert_{2}\cdot \lVert T(\mathbb 1_{Q\cap B_{r}(x)}) \rVert_{2} 
\end{align*}$$
since $T$ is $L^{2}$ bounded, we get that $a_{Q}$ is bounded for a. e. $x \in \mathbb{R}^{n}$.
$$\begin{align*}
\lvert a_{Q}(x) \rvert &\le \lim_{r \to 0^{+}} \frac{1}{\lvert B_{r}(x) \rvert} \lVert \mathbb 1_{Q\cap B_{r}(x)} \rVert_{2}^{2}\\
&\le  \lim_{r \to 0^{+}} \frac{\lvert Q\cap B_{r}(x) \rvert}{\lvert B_{r}(x) \rvert}\\
&\le C.
\end{align*}$$
Then, since $\text{supp }a_{Q} \subset Q$,
$$\begin{align*}
a&= \sum_{Q \in \mathcal{Q}}^{}a_{Q}\\
	\lvert a(x) \rvert &\le C \quad\implies\quad a \in L^{\infty}(\mathbb{R}^{n})
\end{align*}$$
and for any $E \in \mathbb{R}^{n}$ with $\lvert E \rvert<\infty$
$$\begin{align*}
T(\mathbb 1_{E})&= \sum_{Q \in \mathcal{Q}}^{}T(\mathbb 1_{E\cap Q})\\
&\stackrel{(*)}{=}\sum_{Q \in \mathcal{Q}}^{}\mathbb 1_{E}T(\mathbb 1_{Q})\\
&= \mathbb 1_{E}\cdot a.
\end{align*}$$
We can approximate $f$ as a sequence of simple functions 
$$f_{n}=\sum_{i=1}^{n}c_{i} \mathbb 1_{E_{i}}\quad \stackrel{n\to \infty}{\to}f,$$
where $\{E_{i} \}_{1\le i \le n}$ partitions $\mathbb{R}^{n}$. It is clear that 
$$T(f_{n})=\sum_{i=1}^{n}c_{i}a_{E_{i}}=af_{n},$$
and when $n\to \infty$, $T(f)= af$.

---
<div style="page-break-after: always;"></div>

![[Pasted image 20231129160844.png|800]]
This follows Professor Srinivasa Varadhan's proof of Lemma 8.3 in their lecture notes, which can be found [here](https://math.nyu.edu/~varadhan/harmonic/lecture6.pdf).
![[Pasted image 20231203174858.png|600]]
$$f \in BMO(\mathbb{R}^{n})\quad\Leftrightarrow\quad M^{\#}f \in L^{\infty}$$
We let $Q_{2^{k}}$ be the cubes centered at zero with side lengths $2^{k}$ for $k \in \mathbb{N}$.
We can estimate $\mathbb{R}^{n}$ by summing over the cubes:
$$\int_{\mathbb{R}^{n}}\frac{f(x)}{1+\lvert x \rvert^{n+\epsilon }} \text{ d}x \le \left(\int_{Q_{2^{0}}}+\sum_{k=1}^{\infty}\int_{Q_{2^{k}}} \right)\frac{f(x)}{1+\lvert x \rvert^{n+\epsilon }}\text{ d}x$$
We can then write
$$\begin{align*}
\int_{Q_{2^{k}}} \frac{\lvert f(x) \rvert}{1+\lvert x \rvert^{n+\epsilon }}\text{ d}x &\le \frac{1}{1+(2^{k})^{n+\epsilon }}\int_{Q_{2^{k}}}\lvert f(x) \rvert\text{ d}x\\
&\le \frac{1}{1+(2^{k})^{n+\epsilon }}\int_{Q_{2^{k}}}\lvert f(x)-a_{2^{k}} \rvert \text{ d}x + \frac{1}{1+2^{k(1+\epsilon/n  )}}a_{2^{k}}
\end{align*}$$
where $a_{2^{k}}\le f_{Q_{2^{k}} }=\frac{1}{2^{nk}}\int_{Q_{2^{k}}} f \text{ d}x$. Then,
$$\begin{align*}
\int_{\mathbb{R}^{n}}\frac{f(x)}{1+\lvert x \rvert^{n+\epsilon }}\text{ d}x &\le \int_{Q_{2^{0}}}\lvert f(x) \rvert \text{ d}x + \sum_{k=1}^{\infty}\frac{\lvert Q_{2^{k}} \rvert}{1+(2^{k})^{n+\epsilon }}\lVert f \rVert_{*}+\sum_{k=1}^{\infty}\frac{1}{1+2^{k(1+\epsilon/n )}}a_{2^{k}}\\
&\le \int_{Q_{2^{0}}}\lvert f(x) \rvert \text{ d}x + \sum_{k=1}^{\infty}\frac{2^{kn}}{1+(2^{k})^{n+\epsilon }}\lVert f \rVert_{*}+\sum_{k=1}^{\infty}\frac{1}{1+2^{k(1+\epsilon/n )}}a_{2^{k}}
\end{align*}$$
The second term is bounded since the fraction is less than 1 and $f \in BMO(\mathbb{R}^{n})$. We can estimate $a_{2^{k}}$ by 
$$\begin{align*}
	\lvert a_{2^{i+1}}-a_{2^{i}} \rvert &= \frac{1}{2^{i n}}\int_{Q_{2^{i}}}\lvert f(x)-a_{2^{i+1}} \rvert \text{ d}x \le2^{n}\lVert f \rVert_{*}
\end{align*}$$
And such,
$$\begin{align*}
a_{2^{k}}&= a_{2^{0}}+\sum_{i=0}^{k-1}a_{2^{i+1}}-a_{2^{i}}\\
		\lvert a_{2^{k}} \rvert&\le \lvert a_{2^{0}} \rvert + \sum_{i=1}^{k-1}2^{n}\lVert f \rVert_{*}\\
	&\le \lvert a_{2^{0}} \rvert+ k(k-1)2^{n-1}\lVert f \rVert_{*}
\end{align*}$$

Our resulting inequality is
$$\begin{align*}
\int_{\mathbb{R}^{n}}\frac{f(x)}{1+\lvert x \rvert^{n+\epsilon }}\text{ d}x &\le  \int_{Q_{2^{0}}}\lvert f(x) \rvert \text{ d}x + \sum_{k=1}^{\infty}\frac{2^{kn}}{1+(2^{k})^{n+\epsilon }}\lVert f \rVert_{*}+\sum_{k=1}^{\infty}\frac{1}{1+2^{k(1+\epsilon/n )}}\left(\lvert a_{2^{0}} \rvert+ k(k-1)2^{n-1}\lVert f \rVert_{*} \right)\\
&< \infty
\end{align*}$$

---
<div style="page-break-after: always;"></div>

![[Pasted image 20231129160854.png|800]]
Inspired by Fourier Analysis Solution Manual by Grafakos, exercise 6.2.7.
$m$ is a multiplier $\quad\Leftrightarrow\quad$ the operator $T_{m}$ defined by $(T_{m}f)^{\wedge}=m \hat f$ is bounded
$$m(\xi )=\sum_{j=-\infty }^{\infty}a_{j}\psi (2^{-j}\xi )$$
Notice that this sum has finitely many nonzero terms since $\psi$ is compactly supported and is not supported at the origin. Let $0<R_{1}<R_{2}$ such that $\text{supp }\psi \subset \{\xi :R_{1}<\lvert \xi  \rvert <R_{2} \}$. Differentiation by multiindex $\alpha$ gives
$$\begin{align*}
\partial ^{\alpha }(m(\xi ))&= \partial ^{\alpha}\left(\sum_{j=-\infty }^{\infty}a_{j}\psi (2^{-j}\xi )\right) \\
	&= \sum_{j=-\infty }^{\infty}a_{j}2^{-j \lvert \alpha  \rvert} (\partial ^{\alpha } \psi )(2^{-j}\xi ).
\end{align*}$$
Evaluation this at $\xi =\xi _{0}$ ,
$$(\partial ^{\alpha }m)(\xi_{0} )=\sum_{j=\infty }^{\infty}a_{j}2^{-j \lvert \alpha  \rvert}(\partial ^{\alpha }\psi )(2^{-j}\xi _{0})$$
The terms are nonzero when index $j$ satisfies that $R_{1}<\lvert 2^{-j}\xi _{0} \rvert<R_{2}$, or equivalently $\frac{\lvert \xi _{0} \rvert}{R_{2}}<2^{j}<\frac{\lvert \xi _{0} \rvert}{R_{1}}$  or $\text{log} \frac{\lvert \xi _{0} \rvert}{R_{2}}<j<\text{log} \frac{\lvert \xi _{0} \rvert}{R_{1}}$ 
$$\begin{align*}
\lvert (\partial ^{\alpha }m)(\xi_{0} ) \rvert &\le  (\sup_{k}\lvert a_{k} \rvert) \cdot \lVert \partial ^{\alpha }\psi  \rVert_{L^{\infty}}\cdot \sum_{j=-\infty }^{\infty}2^{-j \lvert \alpha  \rvert}\\
&\le (\sup_{k}\lvert a_{k} \rvert) \cdot \lVert \partial ^{\alpha }\psi  \rVert_{L^{\infty}}\cdot \left(\frac{\lvert \xi _{0} \rvert}{R_{1}} \right)^{-\lvert \alpha  \rvert} \cdot \left(\text{log}\frac{\lvert \xi _{0} \rvert}{R_{1}}-\text{log}\frac{\lvert \xi _{0} \rvert}{R_{2}}  \right)\\
&\le (\sup_{k}\lvert a_{k} \rvert) \cdot \lVert \partial ^{\alpha }\psi  \rVert_{L^{\infty}}\cdot \left(\frac{\lvert \xi _{0} \rvert}{R_{1}} \right)^{-\lvert \alpha  \rvert} \cdot \left(1+\text{log}\frac{R_{2}}{R_{1}} \right)\\
\lvert (\partial ^{\alpha }m)(\xi_{0} )	&\le C_{\alpha } \lvert \xi _{0} \rvert^{-\lvert \alpha  \rvert}
\end{align*}$$
where we can apply Hörmander's theorem (Corollary 8.11 in Duoandikoetxea), and obtain that $m$ is a multiplier on $L^{p} \quad\forall\quad 1<p<\infty$.

---
<div style="page-break-after: always;"></div>

![[Pasted image 20231129160907.png|800]]
This is inspired by Fourier Analysis Solution Manual by Grafakos, exercise 6.2.4.
For every multiindex $\alpha$ we can write
$$\begin{align*}
\partial ^{\alpha }(e^{im(\xi )})&= e^{im(\xi )}\sum_{\stackrel{l_{j}\ge0, \beta ^{j}\le \alpha }{l_{1}\beta ^{1}+\dots +l_{k}\beta ^{k}=\alpha }}c_{\beta^{1},\dots ,\beta ^{k} } (\partial ^{\beta ^{1}}m(\xi ))^{l_{1}} \cdots (\partial ^{\beta ^{k}}m(\xi ))^{l_{k}},
\end{align*}$$
where $\beta ^{j}$ are multiindices.
Using the assumption, we can bound this by
$$\begin{align*}
\lvert \partial ^{\alpha }(e^{im(\xi )}) \rvert&\le  \left\lvert e^{im(\xi )}\sum_{\stackrel{l_{j}\ge0, \beta ^{j}\le \alpha }{l_{1}\beta ^{1}+\dots +l_{k}\beta ^{k}=\alpha }}c_{\beta^{1},\dots ,\beta ^{k} }(\lvert \xi  \rvert^{-\lvert \beta ^{1} \rvert})^{l_{1}}\cdots (\lvert \xi  \rvert^{-\lvert \beta ^{k} \rvert})^{l_{k}} \right\rvert\\
&\le C'\left\lvert \sum_{\stackrel{l_{j}\ge0, \beta ^{j}\le \alpha }{l_{1}\beta ^{1}+\dots +l_{k}\beta ^{k}=\alpha }}\lvert \xi  \rvert^{-\lvert \beta ^{1} \rvert l_{1}-\dots -\lvert \beta ^{k} \rvert l_{k}} \right\rvert\\
&\le C_{\alpha }'\lvert \xi  \rvert^{-\lvert \alpha  \rvert},
\end{align*}$$
where we can again apply Hörmander's theorem (Corollary 8.11 in Duoandikoetxea), and get that $e^{im(\xi )}$ is a multiplier on $L^{P}$ for $1<p<\infty$.