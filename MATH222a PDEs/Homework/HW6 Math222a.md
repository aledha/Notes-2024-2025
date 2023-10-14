![[Pasted image 20231012132842.png|800]]
Let's use the method of imaginary charges. 
![[IMG_E59770F5CB44-1.jpeg|200]]
Considering point charges reflected across the origin, the $x^{1}$- and $x^{2}$-axis, we end up with the function
$$G(x,y)=E_{0}(y-x)+E_{0}\left(y-x^{*} \right)-E_{0}\left(y-\overline{x} \right)-E_{0}\left(y-\hat x \right).$$
where $x^{*}=\begin{bmatrix}-x^{1} & -x^{2}\end{bmatrix}^{T},\quad \overline{x}=\begin{bmatrix}x^{1} & -x^{2}\end{bmatrix}^{T}\quad \hat  x=\begin{bmatrix}-x^{1} & x^{2}\end{bmatrix}^{T}$.
When $y^{1}=0$, it is apparent that the first and last term cancel each other, and the second term cancels with the third.
When $y^{2}=0$, the first term cancels with the third term, while the second term cancels with the last term.

![[Pasted image 20231012132850.png|800]]
First, we write down what the Poisson kernel is,
$$\nu (y) \cdot D_{y}G(x,y)$$
$$\begin{align*}
u(x)&= -\int_{\partial U}\nu (y)\cdot D_{y}G(x,y)u(y) \text{ d}S(y)\\
&= -\int_{0}^{\infty}\nu (y) \cdot D_{y}G(x,y)u(y) \text{ d}y^{1}-\int_{0}^{\infty}\nu (y) \cdot D_{y}G(x,y)u(y) \text{ d}y^{2}\\
&= \int_{0}^{\infty}\partial_{y^{2}}G(x,y)u(y)\text{ d}y^{1}+\int_{0}^{\infty}\partial_{y^{1}}G(x,y)u(y)\text{ d}y^{2}
\end{align*}$$
![[Pasted image 20231005214154.png]]
Using this fundamental solution, let's compute $\partial _{y^{1}}G(x,y)$.
$$\begin{align*}
\partial_{y^{1}}G(x,y)&= \partial_{y^{1}} \lvert y-x \rvert E_{0}'(\lvert y-x \rvert)+\partial_{y^{1}} \lvert y-x^{*} \rvert E_{0}'(\lvert y-x^{*} \rvert)\\
&-\partial_{y^{1}} \lvert y-\overline{x} \rvert E_{0}'(\lvert y-\overline{x} \rvert)-\partial_{y^{1}} \lvert y-\hat x \rvert E_{0}'(\lvert y-\hat x \rvert)\\
&= \frac{y^{1}-x^{1}}{\lvert y-x \rvert}\left(- \frac{1}{2 \pi \lvert y-x \rvert} \right) + \frac{y^{1}+x^{1}}{\lvert y-x^{*} \rvert}\left(- \frac{1}{2 \pi \lvert y-x^{*} \rvert} \right)\\
&-\frac{y^{1}-x^{1}}{\lvert y-\overline{x} \rvert}\left(- \frac{1}{2 \pi \lvert y-\overline{x} \rvert} \right)-\frac{y^{1}+x^{1}}{\lvert y-\hat x \rvert}\left(- \frac{1}{2 \pi \lvert y-\hat x \rvert} \right)\\
&= \frac{1}{2\pi }\left( -\frac{y^{1}-x^{1}}{\lvert y-x \rvert^{2}} -\frac{y^{1}+x^{1}}{\lvert y-x^{*} \rvert^{2}} +\frac{y^{1}-x^{1}}{\lvert y-\overline{x} \rvert^{2}} +\frac{y^{1}+x^{1}}{\lvert y-\hat x \rvert^{2}}  \right)
\end{align*}$$
Here, we set $y_{1}=0$, and get that 
$$\begin{align*}
\lvert y-x \rvert&= \lvert y-\hat x \rvert=\sqrt{(x^{1})^{2}+(y^{2}-x^{2})^{2}},\\
	\lvert y-x^{*} \rvert&= \lvert y-\overline{x} \rvert= \sqrt{(x^{1})^{2}+(y^{2}+x^{2})^{2}}.
\end{align*}$$
$$\partial y^{1} G(x,y)= \frac{1}{2\pi }\left( \frac{2x^{1}}{(x^{1})^{2}+(y^{2}-x^{2})^{2}}- \frac{2x^{1}}{(x^{1})^{2}+(y^{2}+x^{2})^{2}} \right)$$
I propose, by the symmetry of the problem, that 
$$\partial y^{2} G(x,y)= \frac{1}{2\pi }\left( \frac{2x^{2}}{(x^{2})^{2}+(y^{1}-x^{1})^{2}}- \frac{2x^{2}}{(x^{2})^{2}+(y^{1}+x^{1})^{2}} \right)$$
These expressions could probably be simplified further.

<div style="page-break-after: always;"></div>

![[Pasted image 20231012132905.png|800]]
As the hint suggests, let's consider the function
$$h(x,y)=G(x,y)-E(x-y),$$
which is harmonic since
$$\Delta h(x,y)=\Delta G(x,y)-\Delta E(x-y)=0$$
Let $\epsilon >0$ and denote $V_{\epsilon }(y)=\{U \}\backslash \overline{B_{\epsilon }(y)}$. For any fixed $y \in U$, we have that $G(\cdot ,y)$ is harmonic in $V_{\epsilon }(y)$. 
For sufficiently small $\epsilon$, $V_{\epsilon }(y)$ is also connected.

If there exists $x_{0}\in V_{\epsilon }(y)$ such that $G(x_{0})=\min_{\overline{V_{\epsilon }(y)}}G$,
then $G$ is constant.
$G$ cannot be constant in $V_{\epsilon }(y)$ since we can take an arbitrarily small $\epsilon$, and it's not constant on $U$.

There therefore does not exist a point in $V_{\epsilon }(y)$ that attains the minimum (which is 0 on $\partial U$), and $G(\cdot ,y)>0$ on $V_{\epsilon }(y)$.

<div style="page-break-after: always;"></div>

![[Pasted image 20231012132915.png|800]]
$$(\partial_{x}+i \partial _{y})f=0 \quad \text{in }U_{+}$$
Let $f=u+iv$ such that $u,v:\mathbb{R}^{2}\to \mathbb{R}$. Then our equation reads
$$(\partial _{x}+i \partial _{y})(u+iv)=(u_{x}-v_{y})+i(u_{y}+v_{x})=0\quad \text{in }U_{+}$$
Or
$$\begin{align*}
u_{x}(z)-v_{y}(z)&= 0\\
u_{y}(z)+v_{x}(z)&= 0
\end{align*}\quad \text{in }U_{+}\tag{3.1}$$

Let's define a function $g$ in $U_{-}$,
$$\begin{align*}
g(z)&= \overline{f}(\overline{z})=u(\overline{z})-iv(\overline{z})\\
&=:p(z)+iq(z)
\end{align*}$$
We want to satisfy
$$\begin{align*}
p_{x}(z)-q_{y}(z)&= 0\\
p_{y}(z)+q_{x}(z)&= 0
\end{align*}\quad \text{in }U_{-}$$
We inspect the first expression,
$$\begin{align*}
p_{x}(z)-q_{y}(z)&= \partial _{x}(u(\overline{z}))-\partial _{y}(-v(\overline{z}))\\
&= u_{x}(\overline{z})-v_{y}(\overline{z}),
\end{align*}$$
where I have used the chain rule. Since for $z \in U_{-}$ then $\overline{z}\in U_{+}$ and $p_{x}(z)-q_{y}(z)=u_{x}(\overline{z})-v_{y}(\overline{z})=0$. 
The second expression is similar,
$$\begin{align*}
p_{y}(z)+q_{x}(z)&= \partial _{y}(u(\overline{z}))+\partial _{x}(-v(\overline{z}))\\
	&= -u_{y}(\overline{z})-v_{x}(\overline{z})=0.
\end{align*}$$
So far, we have shown that $g$ is holomorphic in $U_{-}$, and that the extension is holomorphic in $U$.

To show that the extension is smooth, we need to show that $f$ and $g$ agrees on $\overline{U}\cap \{y=0 \}$. Since $f$ is real-valued here, we have that $v(x,0)=0$.
$$f(x,0)=u(x,0)=u(x,-0)=g(x,0).$$