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
$F$ can be written as
$$\begin{align*}
F(x,u,Du)&=  x^{1}u_{x^{1}}+x^{2}u_{x^{2}}-2u=0\\
F(x,z,p) &= x^{1}(s)p_{1}(s)+x^{2}(s)p_{2}(s)-2z(s)=0\tag{2.1}
\end{align*}$$
Characteristic equations:
$$\begin{align*}
\dot{x}^{j}(s)&= \partial_{p_{j}}F(x(s),z(s),p(s))\\
	\dot{z}(s)&= \sum\limits_{j}^{}\partial_{p_{j}}F(x(s),z(s),p(s))p_{j}(s)\\
			\dot{p}_{j}(s)&= - \partial_{x^{j}}F(x(s),z(s),p(s))-\partial_{z}F(x(s),z(s),p(s)) p_{j}(s)
\end{align*}$$
$$\dot{x}^{1}(s)=x^{1}(s)\text{, }\qquad \dot{x}^{2}(s)=x^{2}(s)$$
$$\dot{z}(s)=x^{1}(s)p_{1}(s)+x^{2}(s)p_{2}(s)\stackrel{(2.1)}{=}2z(s)$$
The B.C. read $u(x^{1},1)=g(x^{1})$.
$x^{1}(s)=x_{0}e^{s}\text{, }\qquad x^{2}(s)=1\cdot e^{s}\text{, }\qquad z(s)=g(x_{0})e^{2s}$

Given a point $(x^{1},x^{2})$, we need to find $x_{0}\text{, }s$ such that $x^{1}(s)=x^{1}\text{ and }x^{2}(s)=x^{2}$. We see that $s=\text{ ln }x^{2}$, and therefore $x_{0}=\frac{x^{1}}{x^{2}}$.

Finally,
$$u(x)=g\left(\frac{x^{1}}{x^{2}}\right)e^{2\text{ ln}x^{2}}=g\left(\frac{x^{1}}{x^{2}}\right)(x^{2})^{2},$$
where $x^{2}>0$.
Let us check that the PDE holds,
$$\begin{align*}
&\quad x^{1}\partial_{x^{1}}\left(g \left(\frac{x^{1}}{x^{2}} \right) (x^{2})^{2} \right)+ x^{2}\partial_{x^{2}}\left(g \left(\frac{x^{1}}{x^{2}} \right) (x^{2})^{2} \right),\\
	 &= x^{1} \cdot \frac{1}{x^{2}}g'\left( \frac{x^{1}}{x^{2}}\right)(x^{2})^{2}+x^{2} \cdot \left[\left(-\frac{x^{1}}{(x^{2})^{2}}\right)g'\left( \frac{x^{1}}{x^{2}}\right)(x^{2})^{2}+ 2g \left(\frac{x^{1}}{x^{2}} \right)x^{2}  \right],\\
&= x^{1}x^{2}g'\left( \frac{x^{1}}{x^{2}}\right)-x^{1}x^{2}g'\left( \frac{x^{1}}{x^{2}}\right)+2g\left( \frac{x^{1}}{x^{2}}\right) (x^{2})^{2}=2u.
\end{align*}$$
We can also see that the boundary condition holds, $u(x^{1},1)=g \left(\frac{x^{1}}{1} \right) 1^{2}=g(x^{1})$.

![[Pasted image 20230828185207.png]]
$F$ can be written as
$$\begin{align*}
F(x,u(x),Du)&= x^{1}u_{x^{1}}+2x^{2}u_{x^{2}}+u_{x^{3}}-3u=0\\
F(x,z,p)&= x^{1}p_{1}+2x^{2}p_{2}+p_{3}-3z
\end{align*}$$
Using the characteristic equations,
$$\dot{x}^{1}=x^{1}\text{, }\quad \dot{x}^{2}=2x^{2}\text{, }\quad \dot{x}^{3}=1$$
$$\dot{z}=x_{1}p_{1}+2x^{2}p_{2}+ p_{3}=3z$$
Solving these ODEs yields
$$\begin{align*}
x^{1}(s)=x^{1}_{0}e^{s}\text{, }\quad x^{2}(s)&= x_{0}^{2}e^{2s}\text{, }\quad x^{3}(s)=s\\
z(s)&= g(x^{1}_{0},x^{2}_{0})\cdot e^{3s}
\end{align*}$$
If $x(s)=(x^{1}\text{, }x^{2}\text{, }x^{3})$, then $s=x^{3}$, and we get the equations
$$\begin{cases}
x^{1}(x^{3}) & =x_{0}^{1}e^{x^{3}} & =x^{1}, \\
x^{2}(x^{3}) & =x_{0}^{2}e^{2x^{3}} & =x^{2},
\end{cases}$$
resulting in $x_{0}^{1}=x^{1}e^{-x^{3}}\text{, }\quad x_{0}^{2}=x^{2}e^{-2x^{3}}$.

The solution reads
$$u(x)=g(x^{1}e^{-x^{3}}\text{, }x^{2}e^{-2x^{3}})\cdot e^{3x^{3}}$$

![[Pasted image 20230828185219.png]]

$$F(x,z,p)=zp_{1}+p_{2}-1$$
$$\dot{x}^{1}=z, \quad \dot{x}^{2}=1\text{, }\quad \dot{z}=zp_{1}+p_{2}=1$$
Solving these,
$z(s)=s+z_{0}, \quad x^{2}(s)=s+x^{2}_{0}, \quad x^{1}(s)= \frac{1}{2}s^{2}+x^{1}_{0}$.
$$\begin{cases}
x^{1}(s)= \frac{1}{2}s^{2}+x_{0}^{1}=x^{1} \\
x^{2}(s)=s+x_{0}^{2}=x^{2}
\end{cases}$$

get new prob 3