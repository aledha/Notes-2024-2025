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
$$\begin{align*}
\partial_{y^{1}}G(x,y)&= \partial_{y^{1}} \lvert y-x \rvert E_{0}'(\lvert y-x \rvert)+\partial_{y^{1}} \lvert y-x^{*} \rvert E_{0}'(\lvert y-x^{*} \rvert)\\
&-\partial_{y^{1}} \lvert y-\overline{x} \rvert E_{0}'(\lvert y-\overline{x} \rvert)-\partial_{y^{1}} \lvert y-\hat x \rvert E_{0}'(\lvert y-\hat x \rvert)
\end{align*}$$

![[Pasted image 20231012132905.png|800]]

![[Pasted image 20231012132915.png|800]]

![[Pasted image 20231012132931.png|800]]