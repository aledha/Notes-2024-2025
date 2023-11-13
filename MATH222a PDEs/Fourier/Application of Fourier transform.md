* We will mainly focus on the Schrödinger equation
* Wave equation if we have time


```ad-Definition
title: Free Schrodinger equation
For $\psi :\mathbb{R}_{t}\times \mathbb{R}^{d}_{x}\to \mathbb C$

$$\begin{align*}
i \partial _{t}\psi + \Delta \psi &= 0 \qquad\text{in }(0,\infty)_{t}\times \mathbb{R}^{d}_{x}\\
\psi (t=0)&= \psi _{0} \qquad\text{on }t=0
\end{align*}$$

```

Let's take the spatial Fourier transform,
$$\hat \psi =\mathcal{F}_{x}\left[\psi  \right](t,\xi )$$
then, by [[Properties of Fourier transform]], we have that $\widehat{\partial _{t}\psi }=-i \lvert \xi  \rvert^{2}\hat \psi$.
$$\begin{align*}
i \partial _{t}\hat \psi -\lvert \xi  \rvert^{2}\hat \psi &= 0\\
\hat \psi (t=0)&= \hat \psi _{0}
\end{align*}$$

$$\hat \psi (t,\xi )=e^{-i t \lvert \xi  \rvert^{2}}\hat \psi _{0}(\xi )\tag{*}$$
From $(*)$ what do we learn?

1. $L^{2}$ based properties. By Plancherel,
	$$\begin{align*}
\lVert \psi (t,x) \rVert_{L^{2}_{x}}&=  \sqrt{\frac{1}{(2\pi )^{d}}}\lVert \hat \psi (t,\xi ) \rVert_{L^{2}_{\xi }}\\
&= \sqrt{\frac{1}{(2\pi )^{d}}} \lVert e^{-i t\lvert \xi  \rvert^{2} } \hat \psi _{0} \rVert_{L^{2}_{\xi }}
\end{align*}$$

Proposition (conservation of total probability)
$\psi \in C_{t}(\mathbb{R}_{t},L^{2}(\mathbb{R}^{d}))$,
$$\int \lvert \psi (t,x) \rvert^{2}\text{ d}x =\int \lvert \psi _{0}(x) \rvert^{2}\text{ d}x$$
In fact, it's easy to prove existance and uniqueness for $\psi _{0}\in L^{2}$.


2. Harder to get, pointwise properties
$$\psi (t,x)=\mathcal{F}^{-1}\left[e^{-i t \lvert \xi  \rvert^{2}}\hat \psi _{0}(\xi ) \right]$$
Instead of this general problem, we reduce it to computing the *forward fundamental solution*.

**Recall** (Duharels principle)
	(Homogeneous problems = initial value problems)
$$\begin{align*}
(i \partial _{t}+\Delta )E&= 0\\
E(t=0)&= \delta _{0}
\end{align*}$$
$$E_{+}(t,x)=\mathbb 1_{(0,\infty) }E(t,x)$$
Transforms into
$$\begin{align*}
(i \partial _{t}-\lvert \xi  \rvert^{2})\hat E&= 0\\
\hat E(t=0)&= 1
\end{align*}$$
And the inverse transform  fund. solution becomes
$$E(t,x)=\mathcal{F}^{-1}\left[e^{-i t \lvert \xi  \rvert^{2}} \right]$$
We will use linear change of variables to transform into a Gaussian
```ad-abstract
title: Lemma ($\mathcal{F}$ and linear change of variables)
For $L:\mathbb{R}^{d}\to \mathbb{R}^{d}$
$$\mathcal{F}\left[f(Lx) \right](\xi )= \frac{1}{\lvert \text{ det}L \rvert}\mathcal{F}[f]((L^{-1})^{*}\xi )$$

```
Assume that $f \in \mathscr S$ 
$$\mathcal{F}[f(Lx)](\xi )=\int f(Lx)e^{-i \xi \cdot x}\text{ d}x$$
Let $Lx=y,\qquad \text{ det}L \text{ d}x=\text{ d}y$
$$\mathcal{F}[f(Lx)](\xi )=\frac{1}{\lvert \text{ det}L \rvert}\int f(y)e^{-i \xi \cdot L^{-1}y}\text{ d}x$$
since $\xi \cdot L^{-1}y=(L^{-1})^{*}\xi \cdot y$,
$$\begin{align*}
\mathcal{F}[f(Lx)](\xi )&= \frac{1}{\lvert \text{ det}L \rvert}\int f(y)e^{-i L^{-1}\xi \cdot y}\text{ d}x\\
&= \frac{1}{\lvert \text{ det}L \rvert} \hat f ((L^{-1})^{*}\xi )
\end{align*}$$
end proof

We want to choose $L$ such that
$$\begin{align*}
- \frac{1}{2}\lvert (L^{-1})^{*}\xi  \rvert^{2}&= - it \lvert \xi  \rvert^{2}\\
- \frac{1}{2}\lvert (L^{-1})^{*}\xi  \rvert^{2}&= - at \lvert \xi  \rvert^{2}\tag{???}
\end{align*}$$

Messy.... results in for $a >0$
$$\mathcal{F} \left[\frac{1}{\sqrt{4\pi at}^{d}}e^{-\frac{1}{4at}\lvert x \rvert^{2}}  \right]=e^{-at \lvert \xi  \rvert^{2}}$$
Now we want to find an analytic extension for complex $a$ (we want it to be $i$)
Turns out we can just exchange a for i
$$E_{+}(t,x)=\frac{1}{\sqrt{4\pi it}^{d}}e^{-\frac{1}{4it}\lvert x \rvert^{2}}  =\mathcal{F}^{-1}[e^{-it \lvert \xi  \rvert^{2}}]$$
(principal square root)

Next time: wave equation