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
![[Pasted image 20230906123723.png]]
![[Pasted image 20230912152506.png]]
#ask what does it mean that $v \in f^{*}(p)$? 

$$p \in \partial_{}f(v)\quad\Leftrightarrow\quad f(w)\ge p \cdot (w-v)+f(v) \quad\forall\quad w \in \mathbb{R}$$

$$v \in \partial_{}f^{*}(p)\quad\Leftrightarrow\quad f^{*}(w)\ge v \cdot (w-p)+f^{*}(p) \quad\forall\quad w \in \mathbb{R}$$
Since $f$ is convex, we have
$$f(tx +(1-t)y) \le tf(x)+(1-t)f(y) \quad\forall\quad x,y \in \mathbb{R}, \quad t \in (0,1).$$
First, assume that
$$\begin{align*}
pv&= f(v)+f^{*}(p)\\
f^{*}(p)&= pv-f(v) \quad \qquad \left(= \sup_{x \in \mathbb{R}^{d}} \{px-f(x) \} \right)\\
f^{*}(p)& \ge px-f(x) \quad\forall\quad x \in \mathbb{R}\\
f(x) & \ge px-f^{*}(p) -f(v) +f(v)\\
f(x)& \ge px -pv +f(v)\\
f(x)& \ge p(x-v)+f(v) \quad\forall\quad x \in \mathbb{R}
\end{align*}$$
The other way:
$$\begin{align*}
f(x) &\ge  p(x-v)+f(v) \quad\forall\quad x \in \mathbb{R}\\
	f(v) &\ge p(x-v)+f(x) \quad\forall\quad x \in \mathbb{R}\\
f(v) &= \sup_{x \in \mathbb{R}}
\end{align*}$$




![[Pasted image 20230912152515.png]]



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