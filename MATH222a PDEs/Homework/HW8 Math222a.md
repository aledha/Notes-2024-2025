![[Pasted image 20231023102748.png|1000]]


![[Pasted image 20231023102811.png|800]]
$$\begin{align*}
\Psi (t,r)&= r \overline{\phi }(t,r)\\
&= r\int_{\partial B_{r}(x) }\phi (t,y) \text{ d}\sigma  (y)
\end{align*}$$

First property:
$$\begin{align*}
(-\partial _{t}^{2}+\partial _{r}^{2})\Psi (t,r)&= -r\partial _{t}^{2}\overline{\phi }(t,r)+ \partial _{r}^{2}r\overline{\phi }(t,r)\\
	&= -r \partial _{t}^{2}\overline{\phi }(t,r)+\partial _{r}(\overline{\phi }(t,r)+r \partial _{r}\overline{\phi }(t,r))\\
&= -r \partial _{t}^{2}\overline{\phi }(t,r)+2 \partial _{r}\overline{\phi }(t,r)+ r \partial _{r}^{2}\overline{\phi }(t,r)
\end{align*}$$
We know that $\overline{\phi}$ solves the radial wave equation $(-\partial _{t}^{2}+\partial _{r}^{2}+ \frac{2}{r}\partial _{r})\overline{\phi}=0$, so we can write
$$\frac{1}{r}(-\partial _{t}^{2}+\partial _{r}^{2})\Psi (t,r)=-\partial _{t}^{2}\overline{\phi }(t,r)+ \frac{2}{r}\partial _{r}\overline{\phi }(t,r)+ \partial _{r}^{2}\overline{\phi }(t,r)=0,$$
and $\Psi$ satisfies the first property.

Second property:
$$\lim_{r \to 0}\Psi (t,r)=\lim_{r \to 0}r \overline{\phi }(t,r)= \phi (t,x)\cdot \lim_{r \to 0}r=0,$$
since $\phi \in C^\infty$.

Third property:
$$\begin{align*}
\lim_{t \to 0}\Psi (t,r)&= \lim_{t \to 0}r\int_{\partial B_{r}(x)}\phi (t,y)\text{ d}y\\
	&= r\int_{\partial B_{r}(x)}g(y) \text{ d}y\\
&= r \overline{g}
\end{align*}$$

Fourth property:
$$\begin{align*}
\lim_{t \to 0}\partial _{t}\Psi (t,r)&= \lim_{t \to 0} \partial _{t}r\int_{\partial B_{r}(x)}\phi (t,y) \text{ d}y\\
		&= r\int_{\partial B_{r}(x)}h(y) \text{ d}y\\
	&= r \overline{h}
\end{align*}$$
<div style="page-break-after: always;"></div>

![[Pasted image 20231023102825.png|800]]


![[Pasted image 20231027154828.png|600]]
As per the hint, we will use the null coordinates $u= \frac{1}{2}(t-r), \quad v= \frac{1}{2}(t+r)$.

$$\begin{align*}
\Psi (v+u,v-u)&= - \frac{1}{2}\int_{0}^{v+u}\int_{v-u-(v+u)+s}^{v-u+(v+u)-s}\square \Psi (s,y) \text{ d}y \text{ d}s\\
&+ \frac{1}{2}(\Psi (0,v-u-(v+u))+\Psi (0,v-u+(v+u)))\\
&+ \frac{1}{2}\int_{v-u-(v+u)}^{v-u+(v+u)} \partial _{t}\Psi (0,y) \text{ d}y\\
	\Psi (v+u,v-u)&= \frac{1}{2}\left(r \overline{g}(-2u)+r \overline{g}(2v) \right)+\frac{1}{2}\int_{-2u}^{2v}r \overline{h}(y) \text{ d}y
\end{align*}$$

$$\begin{align*}
\phi (t,x) &=  \lim_{v \to u^{+}} \frac{\Psi (v+u,v-u)}{r}\\
&= \lim_{v \to u^{+}} \frac{1}{2}( \overline{g}(-2u)+ \overline{g}(2v))+ \frac{1}{2}\int_{-2u}^{2v}\overline{h}(y) \text{ d}y\\
	&= \lim_{r \to 0^{+}} \frac{1}{2}( \overline{g}(r-t)+\overline{g}(r+t))+\frac{1}{2}\int_{r-t}^{r+t} \overline{h}(y) \text{ d}y
\end{align*}$$
What would $\overline{g}(-t)$ be?
<div style="page-break-after: always;"></div>


![[Pasted image 20231027172501.png|800]]
Was able to show that $\Psi$ solves $\left(-\partial _{t}^{2}+\partial _{r}^{2}+ \frac{c_{k}}{r^{2}}\right)\Psi=0$, but couldn't figure out much more.
$$\begin{align*}
\left(-\partial _{t}^{2}+\partial _{r}^{2}+ \frac{c_{k}}{r^{2}}\right)(r^{1+k}\overline{\phi })&= -r^{1+k}\partial _{t}^{2}\overline{\phi }+\partial _{r}(r^{k+1}\partial _{r}\overline{\phi }+ (1+k)r^{k}\overline{\phi })+ c_{k}r^{k-1}\overline{\phi }\\
&= -r^{1+k}\partial _{t}^{2}\overline{\phi }+r^{k+1}\partial _{r}^{2}\overline{\phi }+(k+1)r^{k}\partial _{r}\overline{\phi }+(1+k)k r^{k-1}\overline{\phi } + (1+k)r^{k}\partial _{r}\overline{\phi }+ c_{k}r^{k-1}\overline{\phi }\\
&= r^{1+k}\left[-\partial _{t}^{2}\overline{\phi}+\partial _{r}^{2}\overline{\phi }+ \frac{2(k+1)}{r} \partial _{r}\overline{\phi }+ \frac{(1+k)k+c_{k}}{r^{2}}\overline{\phi }\right]
\end{align*}
$$
Notice that $\frac{d-1}{r}=\frac{3+2k-1}{r}=\frac{2(k+1)}{r}$ and since $\overline{\phi }$ solves $-\partial _{t}^{2}\overline{\phi}+\partial _{r}^{2}\overline{\phi }+ \frac{d-1}{r} \partial _{r}\overline{\phi}$, we have
$$\left(-\partial _{t}^{2}+\partial _{r}^{2}+ \frac{c_{k}}{r^{2}}\right)(r^{1+k}\overline{\phi })=r^{1+k}\frac{(1+k)k+c_{k}}{r^{2}}\overline{\phi },$$
and we can choose $c_{k}=-(1+k)k$ such that $\Psi :=r^{1+k}\overline{\phi}$ solves $\left(-\partial _{t}^{2}+\partial _{r}^{2}+ \frac{c_{k}}{r^{2}}\right)\Psi=0$.

Let's convert the equation to $u= \frac{1}{2}(t-r), \quad v= \frac{1}{2}(t+r)$, with $\partial_{u}= 2 (\partial _{t}-  \partial _{r}), \quad \partial _{v}= 2(\partial _{t}+\partial _{r})$.
$$\begin{align*}
-\partial _{t}^{2}+\partial _{r}^{2}+ \frac{c_{k}}{r^{2}} &= -(\partial _{t}-\partial _{r})(\partial _{t}+\partial _{r})+ \frac{c_{k}}{r^{2}}\\
&= - \frac{1}{4}\partial _{u}\partial _{v}+ \frac{c_{k}}{r^{2}}
\end{align*}$$
Following the hint and trying to construct an equation for $r^{2}\partial _{v}\Psi$,
$$\begin{align*}
(r^{2}\partial _{v}+2)\left(- \frac{1}{4}\partial _{u}\partial _{v}+ \frac{c_{k}}{r^{2}}\right)\Psi &= \left(- \frac{r^{2}}{4}\partial _{u}\partial _{v}^{2}+(v-u)^{2}\partial _{v}\frac{c_{k}}{(v-u)^{2}} - \frac{1}{2}\partial _{u}\partial _{v}+2 \frac{c_{k}}{r^{2}} \right)\Psi \\
&= \left(- \frac{r^{2}}{4}\partial _{u}\partial _{v}^{2}- \frac{2c_{k}}{r}+c_{k}\partial _{v}- \frac{1}{2}\partial _{u}\partial _{v}+2 \frac{c_{k}}{r^{2}} \right)\Psi =0\\
r^{2}\partial _{v}\Psi &= \frac{r^{4}}{4c_{k}}\partial _{u}\partial _{v}^{2}\Psi +2(r-1) \Psi  + \frac{r^{2}}{2c_{k}}\partial _{u}\partial _{v}\Psi 
\end{align*}$$
And since $- \frac{1}{4}\partial _{u}\partial _{v}\Psi + \frac{c_{k}}{r^{2}}\Psi =0$, 
$$\begin{align*}
r^{2}\partial _{v}\Psi &=  \frac{r^{4}}{4c_{k}}\partial _{u}\partial _{v}^{2}\Psi +2(r-1)\Psi +2\Psi \\
&= \frac{r^{4}}{4c_{k}}\partial _{u}\partial _{v}^{2}\Psi +2r \Psi 
\end{align*}$$
which doesn't seem helpful?

