$$\mathcal{F}^{-1}= \frac{1}{(2\pi )^{d}}\mathcal{F}^{*}$$
by Plancherel,
$$\left\langle f \text{ , } g \right\rangle= \frac{1}{(2\pi )^{d}}\left\langle \mathcal{F}[f] \text{ , } \mathcal{F} [g]\right\rangle$$

## Properties
1. $({\partial _{x^{j}}u})^{\wedge}=i \xi _{j}\hat u$
2. $(x^{j}u)^{\wedge}=i \partial _{\xi ^{j}}\hat u$
3. Modulation: $(u(x-x_{0}))^{\wedge}=e^{-i \xi \cdot x_{0}}\hat u(\xi )$.
	1. $(e^{i \xi _{0}\cdot x}u)^{\wedge}=\hat u(\xi -\xi _{0})$ 

We often call $x$ the variable for the physical space, while $\xi$ is the variable for the frequency space (think 3b1b).
Can also be $x$ for time, $\xi$ for frequency.

## Convolution with FT
When $u,v \in \mathscr{S}(\mathbb{R}^{d})$ 
$$\begin{align*}
(u *v)^{\wedge}&= \hat u \cdot \hat v \tag{1}\\
(u \cdot v)^{\wedge}&= \frac{1}{(2\pi )^{d}}\hat u*\hat v \tag{2}
\end{align*}$$
```ad-summary
title: Proof
collapse: closed

$$\begin{align*}
u(x)v(x)&= \int \widehat{u \cdot v}(\xi )e^{i \xi x} \frac{\text{ d}\xi}{(2\pi )^{d}}\\
&= \int \hat u(\xi_{1})e^{i \xi _{1}x}\frac{\text{ d}\xi_{1}}{(2\pi )^{d}}\int \hat v(\xi_{2})e^{i \xi _{2}x}\frac{\text{ d}\xi_{2}}{(2\pi )^{d}}\\
&= \int\int \hat u(\xi_{1})\cdot \hat v(\xi _{2})e^{i( \xi _{1}+\xi _{2})x}\frac{\text{ d}\xi_{1}}{(2\pi )^{d}}\frac{\text{ d}\xi_{1}}{(2\pi )^{d}}
\end{align*} $$
let $\xi =\xi _{1}+\xi _{2}$
$$\begin{align*}
&=  \int\int \hat u(\xi -\xi _{2})v(\xi _{2})e^{i \xi \cdot x} \frac{\text{ d}\xi }{(2\pi )^{d}}\frac{\text{ d}\xi_{2} }{(2\pi )^{d}}\\
&= \int \underbrace{\left(\int \hat u(\xi -\xi _{2})\hat v\left(\xi _{2}\right)\frac{\text{ d}\xi_{2} }{(2\pi )^{d}}\right)}_{=\widehat{ u \cdot v}(\xi )}e^{i\xi x} \hat v(\xi _{2})\frac{\text{ d}\xi }{(2\pi )^{d}}
\end{align*}$$

```


If we have a problem of the form
$$\begin{align*}
P&=  \sum_{\alpha }^{}c_{\alpha }\partial _{x}^{\alpha }\\
Pu&= f\\
		\widehat{Pu}&= \sum_{\alpha }^{}c_{\alpha }(i \xi )^{\alpha }\hat u(\xi )=\hat f
\end{align*}$$
So the problem transforms into
$$\hat u(\xi )= \frac{1}{\sum_{\alpha }^{}c_{\alpha} (i\xi )^{\alpha }}\hat f(\xi )$$
and then take the inverse transform. 
Problem being when $p(\xi )=\sum_{\alpha }^{}c_{\alpha} (i \xi )^{\alpha }=0$. The $\xi$ that gives these zeroes are called the *characteristic set for* $P$
```ad-example
1. For  $-\Delta \quad\implies\quad p(\xi )=\lvert \xi  \rvert^{2}$ because $-\nabla \nabla \quad\implies\quad - i \xi \cdot (i \xi )$
	1. Characteristic set is $\{0 \}$

3. $\square=-\partial _{t}^{2}+\Delta \to \tau ^{2}-\lvert \xi  \rvert^{2}$
	1. Characteristic set is when $\lvert \tau  \rvert=\lvert \xi  \rvert$
```

```ad-Definition
title: Fourier multiplier
$$m(D)f(x)=\mathcal{F}^{-1}\left[m(\xi )\hat f(\xi ) \right]$$

$m(D)$ is the **Fourier multiplier**, while $m(\xi)$ is the symbol.

```
Corollarary
If $m \in L^{\infty}$ then 
$$\lVert m(D)f \rVert_{L^{2}}\le \lVert m \rVert_{L^{\infty}}\lVert f \rVert_{L^{2}}$$
($\because$ Plancheral)

In fact, any translation invariant operator $T$ that is bounded in $L^{2}$ is a *Fourier multiplier* with $m \in L^{\infty}$
	Translation invariant: $(Tf)(x-y)=T(f(x-y))$.

```ad-example
1. $(-\Delta +1)u=f \quad\text{for }f \in \mathscr{S}(\mathbb{R}^{d})$
$(\lvert \xi  \rvert^{2}+1)\hat u=\hat f$, then
$\hat u= \frac{1}{1+\lvert \xi  \rvert^{2}}\hat f$
$$\begin{align*}
u&= \mathcal{F}^{-1}\left(\frac{1}{1+\lvert \xi  \rvert^{2}} \hat f\right)\\
&= \frac{1}{1+\lvert D \rvert^{2}}
\end{align*}$$

2. $-\Delta u=f$
$$\begin{align*}
\lvert \xi  \rvert^{2}\hat u&= \hat f \tag{safe}\\
\hat u(\xi )&= \frac{1}{\lvert \xi  \rvert^{2}}\hat f \tag{danger}
\end{align*}$$
This is "somewhat okay" when $d \ge 3$ and $f \in \mathscr{S}$. (this is because this becomes a locally integrable function)
Using fundamental solution
$$\begin{align*}
-\Delta E_{0}&= \delta _{0}\\
	\lvert \xi  \rvert^{2}\hat E_{0}&= 1\\
\hat E_{0}&= \frac{1}{\lvert \xi  \rvert^{2}}
\end{align*}$$
by HW problem
```



3. $(\partial _{t}-\Delta )u=f$
$$\begin{align*}
(\partial _{t}+\lvert \xi   \rvert^{2})\hat u(t,\xi )&= \hat f(t,\xi )\\
\hat u(0,\xi )&= \hat g(\xi )
\end{align*}$$
Fund. solution
$$\begin{cases}
(\partial _{t}-\Delta )E_{+}=0\quad\text{for }t>0 \\
E_{+}(t=0)=\delta _{0}
\end{cases}$$