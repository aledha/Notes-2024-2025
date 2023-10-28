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
![[Pasted image 20231023102825.png|800]]

![[Pasted image 20231026173153.png|600]]
![[Pasted image 20231026173527.png|600]]
![[Pasted image 20231026173232.png|600]]
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


![[Pasted image 20231027172501.png|800]]

$$\Psi ^{(k)}:=(r^{2}\partial _{v})^{k}(r^{1+k}\overline{\phi })$$

$$-\partial _{u}\partial _{v}\Psi ^{(k)}+ \frac{a_{k}}{r}\partial _{v}\Psi ^{(k)}=0$$
Let's assume that $\Psi ^{(0)}=r \overline{\phi }$ solves the equation $-\partial _{u}\partial _{v}\Psi^{(0)}+ \frac{a_{0}}{r}\partial _{v}\Psi ^{(0)}=0$




midterm 2
* only cover materials since last midterm, focus on fundamental solutions
* Lecture notes §4-7
* hw 8.5 on saturday
* look at solutions on tuesday
* 