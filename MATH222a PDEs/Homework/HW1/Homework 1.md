![[Pasted image 20230827163029.png]]
First, we denote 
$$F(x,u(x),Du(x))=\partial_{t}u(x)+t \partial_{x}u(x) -f(x,t)=0$$
Now, consider the curve $\gamma =\{x(s): s \in I\}$. Let
$$z(s)=u(x(s)),\qquad p_{j}(s)=\partial_{j}u(x(s)).$$
$$F(x,z,p)=$$
The characteristic equations read
$$\begin{align*}
\dot{x}^{j}(s)&= \partial_{p_{j}}F(x(s),z(s),p(s))\\
	\dot{z}(s)&= \sum\limits_{j}^{}\partial_{p_{j}}F(x(s),z(s),p(s))p_{j}(s)\\
			\dot{p}_{j}(s)&= - \partial_{x^{j}}F(x(s),z(s),p(s))-\partial_{z}F(x(s),z(s),p(s)) p_{j}(s)
\end{align*}$$

