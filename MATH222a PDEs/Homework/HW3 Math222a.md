![[Pasted image 20230912152454.png]]
Note that $f$ is convex, and therefore $-f$ is concave and that $\lim_{\lvert v \rvert \to \infty} \frac{f(v)}{\lvert v \rvert}=\lim_{\lvert v \rvert \to \infty} \frac{1}{q} \lvert v \rvert^{q-1}\to +\infty \quad\text{for }q>1$, so the Legendre transform exists if $q>1$.
Definition of the Legendre transform:
$$\begin{align*}
f^{*}(p)&=  \sup_{v \in \mathbb{R}}\left\{ p \cdot v-f(v) \right\}\\
	&= \sup_{v \in \mathbb{R}} \left\{ p \cdot v - \frac{1}{q}\lvert v \rvert^{q} \right\}
\end{align*}$$
Note that if $p \le 0$, then $f^{*}(p)=0$.

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
where $\alpha = \frac{q}{q-1}$. If $q>1$, our final result is 
$$f^{*}(p)=\begin{cases}
\frac{1}{\alpha }p^{\alpha } & \quad\text{for }p>0, \\
0 & \quad\text{else}.
\end{cases}$$

![[Pasted image 20230912152500.png]]
First, note that 
$$H(p)= \frac{1}{2}\sum_{i,j=1}^{d}a^{ij}p_{i}p_{j}+ \sum_{i=1}^{d}b^{i}p_{i}= \frac{1}{2}p^{T}Ap+ p^{T}b$$
Since $A$ is positive definite, the first term is convex. The second term is also convex.
Another result of $A$ being positive definite is that 
$$\lim_{\lVert p \rVert \to \infty} \frac{1}{2 \lVert p \rVert} p^{T}Ap \to \infty,$$
because the quadratic is always positive. Therefore
$$\lim_{\lVert p \rVert \to \infty} \frac{H(p)}{\lVert p \rVert}\to \infty,$$
since the quadratic term will dominate the linear term.

Now that we know that the transform is well-defined, let's compute it.
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
H^{*}(v)&= \frac{1}{2} (v-b)^{T}A^{-1}(v-b).
\end{align*}$$
![[Pasted image 20230912152506.png]]
I assume that it is supposed to say $v \in \partial_{}f^{*}(p)$, not $v \in f^{*}(p)$.
We want to show that
$$p \in \partial_{}f(v) \quad\Leftrightarrow\quad f(w)\ge p \cdot (w-v)+f(v) \quad\forall\quad w \in \mathbb{R}\tag{1}$$
if and only if
$$v \in \partial_{}f^{*}(p) \quad\Leftrightarrow\quad f^{*}(w)\ge v \cdot (w-p)+f^{*}(p) \quad\forall\quad w \in \mathbb{R}\tag{2}$$

if and only if
$$pv=f(v)+f^{*}(p).\tag{3}$$

We will start by showing $(3)\quad\Leftrightarrow\quad (1)$.
Use the definition of the Legendre transform 
$$\begin{align*}
f^{*}(p)&= \sup_{v \in \mathbb{R}}\{p \cdot v -f(v) \}\\
\Leftrightarrow\quad f^{*}(p) &\ge p \cdot w-f(w) \quad\forall\quad w \in \mathbb{R}. 
\end{align*}$$
Assume $(3)$, i.e.,
$$\begin{align*}
pv &= f(v)+f^{*}(p)\\
\Leftrightarrow\quad pv &\ge f(v)+pw-f(w) \quad\forall\quad w \in \mathbb{R}\\
\Leftrightarrow\quad f(w) &\ge p \cdot (w-v)+f(v) \quad\forall\quad w \in \mathbb{R}\\
	\quad\Leftrightarrow\quad p &\in \partial_{}f(v).
\end{align*}$$
We have now showed that $(3)\quad\Leftrightarrow\quad (1)$.

Now we only need to show $(3) \quad\Leftrightarrow\quad (2)$.
Similarly, we will use the definition of the Legendre transform,
$$\begin{align*}
f(v)&= \sup_{p \in \mathbb{R}} \{p \cdot v -f^{*}(p) \}\\
\quad\Leftrightarrow\quad f(v)&\ge w \cdot v-f^{*}(w)\quad\forall\quad w \in \mathbb{R} 
\end{align*}$$
Assume $(3)$,
$$\begin{align*}
pv &= f(v)+f^{*}(p)\\
\quad\Leftrightarrow\quad pv &\ge wv-f^{*}(w)+f^{*}(p) \quad\forall\quad w \in \mathbb{R}\\
\quad\Leftrightarrow\quad f^{*}(w) &\ge v(w-p)+f^{*}(p)\\
\quad\Leftrightarrow\quad v &\in \partial_{}f^{*}(p)
\end{align*}$$
So $(1)\quad\Leftrightarrow\quad (2)\quad\Leftrightarrow\quad (3)\qquad \square$.

![[Pasted image 20230912152515.png]]
Problem 3.(c) from HW#02 states that
$$f \text{ differantiable on }\mathbb{R}\quad\Leftrightarrow\quad \partial_{}f(x) \text{ consists of exactly one element}\quad\forall\quad x \in \mathbb{R}.$$
Problem 1.(c) in this HW states that
$$p \in \partial_{}f(v) \quad\Leftrightarrow\quad pv=f(v)+f^{*}(p).$$
In other words, we need to show that $p$ is the only element in $\partial_{}f(v)\quad\forall\quad v \in \mathbb{R}.$ 

Since $f$ is convex and $\lim_{\lvert v \rvert \to \infty} \frac{f(v)}{\lvert v \rvert}=+\infty$, the Legendre transform is well-defined, as well as the transform of $f^{*}(p)$,
$$(f^{*}(p))^{*}=f(v)=\sup_{p \in \mathbb{R}}\{pv-f^{*}(p) \}.$$
Let's analyse the function (of $p$) inside the curly brackets. It consists of a linear term $vp$, which is both convex and concave. If we assume that $f^{*}$ is **strictly** convex, then $-f^{*}$ is strictly concave. A concave function plus a strictly concave function results in a strictly concave function.

A strictly concave function has either one unique maximiser or no maximisers. We already know that the transform is well-defined, so the function in the brackets must have a maximiser.

$f^{*}$ is strictly convex if and only if there exists exactly one $p \in \mathbb{R}$ such that
$$f(v)=pv-f^{*}(p),$$
for every $v \in \mathbb{R}$ (since $v$ was arbitrary). This is the case if and only if there exists exactly one $p \in \partial_{}f(v)\quad\forall\quad v \in \mathbb{R}$. This is the case if and only if $f$ is differentiable on $\mathbb{R}$.  

![[Pasted image 20230912152525.png]]
First, we denote
$$f(y):= tL \left(\frac{x-y}{t} \right)+g(y)$$
Suppose that $y^{*}$ minimises $f$. Then,
$$D_{y}f(y^{*})=0.$$
Computing the value of $D_{y}f$,
$$D_{y}f(y)=t \cdot \left(- \frac{1}{t}\right)DL \left(\frac{x-y}{t} \right)+ Dg(y)$$
$$DL \left(\frac{x-y^{*}}{t} \right)=Dg(y^{*})$$
Since $L(v)=   v \cdot p- H(p) \quad\implies\quad DL(v)=p \text{ and }DH(p)=v$ 

Calling $Dg(y^{*})=p$ and $\frac{x-y^{*}}{t}=v$, we get
$$\begin{align*}
\frac{x-y^{*}}{t}&= DH(Dg(y^{*}))\\
\lvert x-y^{*} \rvert&= t \lvert DH(Dg(y^{*})) \rvert\\
\lvert x-y^{*} \rvert &\le tR, 
\end{align*}$$
where $R=\sup_{y \in \mathbb{R}^{d}}\lvert DH(Dg(y)) \rvert$. 

As per the claim, any $y$ that minimises the equation above must be an element of the ball with radius $Rt$ centered at $x$, i.e. $y \in B_{Rt}(x)\quad  \square$.

![[Pasted image 20230912152533.png]]
The Hamiltonian is $H(p)=\lvert p \rvert^{2}$. Then, the Legendre transform is
$$\begin{align*}
L(v)&=  \sup_{p \in \mathbb{R}^{d}}\{v \cdot p -H(p) \}\\
&= \sup_{p \in \mathbb{R}^{d}} \{v \cdot p-\lvert p \rvert^{2} \}
\end{align*}$$
Differentiation with respect to $p$,
$$D_{p}(v \cdot p- \lvert p \rvert^{2})=v -2p=0 \quad\implies\quad p = \frac{1}{2}v.$$
Putting this back,
$$\begin{align*}
L(v)&=  v \cdot \frac{1}{2}v- \left\lvert \frac{1}{2}v \right\rvert^{2}\\
&= \frac{\lvert v \rvert^{2}}{4}
\end{align*}$$
The Hopf-Lax formula reads
$$\begin{align*}
u(t,x)&= \min_{y \in \mathbb{R}^{d}}\left\{ tL\left( \frac{x-y}{t}\right)+g(y) \right\}\\
		&= \min_{y \in \mathbb{R}^{d}}\left\{ t \frac{\lvert x-y \rvert^{2}}{4 \lvert t \rvert^{2}} + g(y)\right\}\\
	&= \min_{y \in \mathbb{R}^{d}} \left\{ \frac{\lvert x-y \rvert^{2}}{4t}+g(y) \right\}
\end{align*}$$
Here, $g(y)=\begin{cases}0  & \quad\text{for }y \in E \\ \infty  & \quad\text{for }y \notin E \end{cases}$ . 
So, if $x \in E$, then the minimum is achieved at $y=x$, such that $g(x)=0$ and the $x-y$ term vanishes.
If $x\notin E$, then the minimum is achieved when $y \in E$, and the $x-y$ term is minimised. 
$\lvert x-y \rvert$ must therefore be the minimum distance between $x$ and the set $E$, i.e., $\lvert x-y \rvert=\text{dist}(x,E)$. The result becomes
$$u(t,x)= \frac{\text{dist(x,E)}^{2}}{4t}.$$