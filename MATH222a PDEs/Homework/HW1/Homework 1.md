![[Pasted image 20230827163029.png]]
First, we denote 
$$F(x,u(x),Du(x))=\partial_{t}u(x)+t \partial_{x}u(x) -f(x,t)=0$$
Now, consider the curve $\gamma =\{x(s): s \in I\}$. Let
$$z(s)=u(x(s)),\qquad p_{j}(s)=\partial_{j}u(x(s)).$$
$$F(x,z,p)=p_{2}+x^{2}p_{1}-f$$
The characteristic equations read
$$\begin{align*}
\dot{x}^{j}(s)&= \partial_{p_{j}}F(x(s),z(s),p(s))\\
	\dot{z}(s)&= \sum\limits_{j}^{}\partial_{p_{j}}F(x(s),z(s),p(s))p_{j}(s)\\
			\dot{p}_{j}(s)&= - \partial_{x^{j}}F(x(s),z(s),p(s))-\partial_{z}F(x(s),z(s),p(s)) p_{j}(s)
\end{align*}$$
In our case,
$$\begin{align*}
\dot{x}^{1}(s)&= x^{2}\\
\dot{x}^{2}(s)&= 1\\
	\dot{z}(s) &= p_{1}x^{2}+p_{2}=f
\end{align*}$$
$$\begin{align*}
\int_{x^{1}_{0}}^{x^{1}}\text{ d}x^{1}&= \int_{0}^{s}x^{2}(s)\text{ d}s\\
x^{1}(s)&= x_{0}^{1}+x^{2}(s)-x_{0}^{2}
\end{align*}$$
$${x}^{2}(s)=x_{0}^{2}+s$$
$$\begin{align*}
\int_{z_{0}}^{z}\text{ d}z&= \int_{0}^{s}f(x(s)) \text{ d}s\\
z(s)&= z_{0}
\end{align*}$$


![[Pasted image 20230828185154.png]]

![[Pasted image 20230828185207.png]]

![[Pasted image 20230828185219.png]]

![[Pasted image 20230828185233.png]]

![[Pasted image 20230828185245.png]]