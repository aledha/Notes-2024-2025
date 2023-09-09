By: Alexander Hatle
![[Pasted image 20230906123534.png]]
We define
$$\begin{align*}
\tilde{x}^{i}&=\Phi (x^{i}) =x^{i} \quad\text{for }i=1,\dots,d-1,\\
	\tilde{x}^{d}&=\Phi (x^{d})= x^{d}-\gamma (x^{1},\dots,x^{d-1}),
\end{align*}$$
Where $\gamma$ is from Definition 2.8 about $C^{k}$ boundary. 
We know that $\Phi (\Gamma)$ is flat a neighbourhood near $\Phi (x_{0})$.
Then, 
$$\tilde F(\tilde x,\tilde u(\tilde x), D_{\tilde x}\tilde u (\tilde x))=F(x,z,p)=0,$$
where $x = \Phi ^{-1}(\tilde x),\quad  z = \tilde u (\tilde x),\quad  p_{j}= \sum_{k}^{}\partial_{x^{j}}\tilde x^{k}(\Phi ^{-1}(\tilde x))\partial_{\tilde x^{k}}\tilde u(\tilde x)$.


<div style="page-break-after: always; visibility: hidden"> \pagebreak </div>

![[Pasted image 20230906123624.png]]
We will use calculus of variations to 
$$\begin{align*}
\frac{\text{d}}{\text{d}h}\int_{0}^{t}L\left(\mathbf w(s)+h \phi (s), \dot {\mathbf w}(s)+h \dot \phi (s)\right) \text{ d}s\bigg|_{h=0}&= 0\quad\forall\quad \phi \in C^{2}_{c}((0,t)\to \mathbb{R}^{d})\\
\int_{0}^{t} \sum_{j}^{}\left[\phi^{j} (s)\cdot \partial_{\mathbf w^{j}}L(\mathbf w(s),\dot{\mathbf w}(s)) +\dot \phi^{j} (s)\partial_{\dot{\mathbf w}^{j}}L(\mathbf w(s),\dot{\mathbf w}(s)) \text{ d}s \right] &= 0
\end{align*}$$
We denote the minimiser as $\mathbf x(s)$
$$\int_{0}^{t}\phi D_{x}L+\dot \phi D_{v}L \text{ d}s=0.$$
Integration by parts on the second term gives $\int_{0}^{t}\dot \phi D_{v}L \text{ d}s=\left[\phi D_{v}L \right]_{0}^{t}-\int_{0}^{t}\phi \frac{\text{d}}{\text{d}s}(D_{v}L)\text{ d}s$, where the compact support of $\phi$ suggests that the first term on RHS is zero.
Then the expression reads
$$\begin{align*}
\int_{0}^{t}\left[\phi(s) D_{x}L(\mathbf x(s), \dot {\mathbf x}(s))- \phi(s) \frac{\text{d}}{\text{d}s}D_{v}L(\mathbf x(s), \dot {\mathbf x}(s)) \right] \text{ d}s&= 0\\
\int_{0}^{1}\phi (s)\underbrace{\left[D_{x}L(\mathbf x(s), \dot {\mathbf x}(s))-\frac{\text{d}}{\text{d}s}D_{v}L(\mathbf x(s), \dot {\mathbf x}(s)) \right]}_\text{Euler-Lagrange}\text{ d}s&= 0\quad\forall\quad \phi \in C^{2}_{c}((0,t)\to \mathbb{R}^{d})
\end{align*}$$
A minimiser must solve this equation above for each $\phi,$ then it must also solve the Euler-Lagrange equation. $\square$
<div style="page-break-after: always; visibility: hidden"> \pagebreak </div>

![[Pasted image 20230906123635.png]]
Picking up from the last calculation, but allowing $\phi (0)≠0$, the integration by parts becomes
$\int_{0}^{t}\dot \phi D_{v}L \text{ d}s=\left[\phi D_{v}L \right]_{0}^{t}-\int_{0}^{t}\phi \frac{\text{d}}{\text{d}s}(D_{v}L)\text{ d}s=-\phi (0)D_{v}L(\mathbf x(0),\dot {\mathbf x}(0))-\int_{0}^{t}\phi \frac{\text{d}}{\text{d}s}(D_{v}L)\text{ d}s$

Putting this back and doing the same operations as in a), we get
$$\int_{0}^{1}\phi (s)\left[D_{x}L(\mathbf x(s), \dot {\mathbf x}(s))-\frac{\text{d}}{\text{d}s}D_{v}L(\mathbf x(s), \dot {\mathbf x}(s)) \right]\text{ d}s-\phi (0)D_{v}L(\mathbf x(0),\dot {\mathbf x}(0))=0,$$
$\forall\quad \phi \in C^{2}((0,t)\to \mathbb{R}^{d}:\phi (t)=0)$.
But for the solution $\mathbf x$, the integral must be zero by a). Therefore $\phi (0) D_{v}L(\mathbf x(0),\dot {\mathbf x}(0))=0,$ and since $\phi(0)$ can be nonzero, then
$$D_{v}L(\mathbf x(0),\dot {\mathbf x}(0))=0.\quad \square$$
<div style="page-break-after: always; visibility: hidden"> \pagebreak </div>

![[Pasted image 20230906123645.png]]

$$\begin{align*}
\frac{\text{d}}{\text{d}h}\int_{0}^{t}L(\mathbf w(s)+h\phi (s), \dot {\mathbf w}(s)+h \dot \phi (s)) \text{ d}s+g(\mathbf w(0)+h \phi (0))\bigg|_{h=0}&= 0\\
		\int_{0}^{t} \sum_{j}^{}\phi ^{j}(s)\partial_{x^{i}}L(\mathbf w(s),\dot {\mathbf w}(s))+\dot \phi ^{j}(s)\partial_{v^{i}}L(\mathbf w(s),\dot {\mathbf w}(s)) \text{ d}s+ \sum_{j}^{}\phi ^{j}(0)\partial_{x^{j}}g(\mathbf w(0))  &=0 \\
\int _{0}^{t}\phi D_{x}L+\dot \phi D_{v}L \text{ d}s+\phi (0)\cdot D_{x}g(\mathbf w(0))=0
\end{align*}$$


<div style="page-break-after: always; visibility: hidden"> \pagebreak </div>

![[Pasted image 20230906123657.png]]
First, we define
$$g(x)=\sup_\limits{\alpha }f_{\alpha} (x).$$
Then we inspect the arbitrary point $\tau x+ (1-\tau )y$, where the function value is 
$$g(\tau x + (1-\tau )y)= f_{\beta }(\tau x + (1-\tau )y), $$
for some $\beta$ that gives the supremum over the set of functions (given that this is a finite number). We know that since $f_{\beta }$ is convex,
$$f_{\beta }(\tau x + (1-\tau )y)\le \tau f_{\beta }(x)+ (1-\tau )f_{\beta }(y)\le \tau \sup_\limits{\alpha }f_{\alpha }(x)+(1-\tau )\sup_\limits{\alpha }f_{\alpha }(y)$$
It follows that
$$g(\tau x + (1-\tau )y)\le \tau g(x)+(1-\tau )g(y),$$
i.e., that $g(x)=\sup_{\alpha }f_{\alpha }(x)$ is convex. $\square$

<div style="page-break-after: always; visibility: hidden"> \pagebreak </div>

![[Pasted image 20230906123711.png]]
We consider points $x<y<z$. Using the convexity of $f$ and setting $\alpha \in (x,y)$ gives
$$\begin{align*}
f(\alpha )&\le \tau f(x)+(1-\tau )f(y) \\
&\le  \frac{\alpha-x}{y-x}f(y)+\left(1- \frac{\alpha-x}{y-x}\right)f(x)\\
&\le  f(x)+\frac{f(y)-f(x)}{y-x}(\alpha -x)
\end{align*}$$
which is precisely the line passing through $(x,f(x)), (y,f(y))$. This means that the graph of $f$ is under the straight line in the interval $(x,y)$. 

For $\alpha >y$, the graph must be above the straight line. This can be shown by reusing the same argument: we have three points $x<y<\alpha$, so the point $f(y)$ must be below the straight line passing through $(x,f(x)),(\alpha ,f(\alpha ))$. Therefore, $f$ must be **above** the line passing through $(x,f(x)), (y,f(y))$ in the interval $(x,y)$.

This same line of reasoning can be used to show that in the interval $(x,y)$, $f$ must be above the line passing through$(y,f(y)),(z,f(z))$, and that in the interval $(y,z)$, $f$ must be below the line passing through $(y,f(y)),(z,f(z))$.

Now, we have shown that $f$ is contained between these two lines. Then, it is easy to see that $\lim_{\alpha  \to y^{+}}f(\alpha )=\lim_{\alpha  \to y^{-}}f(\alpha ) \quad\forall\quad y$, and $f$ is therefore continuous.

<div style="page-break-after: always; visibility: hidden"> \pagebreak </div>

![[Pasted image 20230906123723.png]]

We will first show the "if" part. 
$$\lim_{h \to 0^{\pm}} \frac{f(x+h)-f(x)}{h}$$
Setting $y=x+h$,
$$\lim_{h \to 0^{\pm} } \frac{f(y)-f(x)}{h}\ge \lim_{h \to 0^{\pm} }\frac{m \cdot (y-x)+f(x)-f(x)}{h}=m$$


We consider three points, $x-h<x<x+h$. We denote $y^{+}=x+h,y^{-}=x-h$.
Let us assume that $m$ belongs to the subdifferential of $f$ at $x$. Then,
$f(y)\ge m(y-x)+f(x) \quad\forall\quad y \in \mathbb{R}$
$$\begin{align*}
f(y^{+})&\ge m h+f(x)\\
f(y^{-})&\ge m(-h)+f(x)
\end{align*}$$
$$\frac{f(x)-f(y^{-})}{h}\le m\le \frac{f(y^{+})-f(x)}{h}$$
Now we can use the convexity of $f$, namely 
$$f(x)\le \frac{1}{2}f(y^{-}) + \frac{1}{2}f(y^{+}) \quad\implies\quad 2f(x)-f(y^{+})\le f(y^{-}).$$
Inserting this into the previous inequality gives
$$\frac{f(y^{+})-f(x)}{h}\le m \le \frac{f(y^{+})-f(x)}{h},$$
which implies that $m=\frac{f(y^{+})-f(x)}{h}=\frac{f(x+h)-f(x)}{h}$.
Since this must hold for all $y$, it must also hold for $h\to 0,$ i.e.,
$$m=\lim_{h \to 0} \frac{f(x+h)-f(x)}{h}=f'(x)$$
