![[Pasted image 20230827163029.png]]
First, we denote 
$$\begin{align*}
F(x,t,u(x),Du(x))&= \partial_{t}u(x)+t \partial_{x}u(x) -f(x,t)&= 0\\
F(x,t,z,p)&= p_{t}+tp_{x}-f&= 0
\end{align*}$$
Now, consider the curve $\gamma =\{x(s): s \in I\}$. Let
$$z(s)=u(t(s)\text{, }x(s)),\qquad p_{j}(s)=\partial_{j}u(t(s),x(s)).$$
The characteristic equations read
$$\begin{align*}
\dot{x}^{j}(s)&= \partial_{p_{j}}F(x(s),z(s),p(s))\\
	\dot{z}(s)&= \sum\limits_{j}^{}\partial_{p_{j}}F(x(s),z(s),p(s))p_{j}(s)\\
			\dot{p}_{j}(s)&= - \partial_{x^{j}}F(x(s),z(s),p(s))-\partial_{z}F(x(s),z(s),p(s)) p_{j}(s)
\end{align*}$$
In our case,

$$u_{t}+tu_{x}=f, \qquad u(0,x)=u_{0}(x)$$
$$\dot{t}(s)=1\text{, }\qquad \dot{x}(s)=t, \qquad \dot{z}(s)=p_{t}+tp_{x}=f$$
Solving the ODEs for t and x yields 
$t(s)=s, \qquad x(s)=x_{0}+ \frac{1}{2}s^{2}$.

Now, given a $(t,x) \in R^{2}$, we should be able to find $x_{0}\text{, }s$ such that $t(s)=t,\quad  x(s)=x$. 
This results in $s=t, \quad x_{0}=x- \frac{1}{2}t^{2}$




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
$x^{1}(s)= z_{0}s+ \frac{1}{2}s^{2}+ x_{0},\qquad x^{2}(s)=s+x_{0}, \qquad z(s)=z_{0}+s$.
$$\begin{cases}
x^{1}(s)= z_{0}s+\frac{1}{2}s^{2}+x_{0} & =x^{1} \\
x^{2}(s)=s+x_{0} & =x^{2}
\end{cases}$$
Here, $z_{0}=u(x_{0},x_{0})=\frac{1}{2}x_{0}$, so the equations become
$$\begin{cases}
\frac{1}{2}x_{0}s+\frac{1}{2}s^{2}+x_{0} & =x^{1} \\
s+x_{0} & =x^{2}
\end{cases}$$
$$\begin{align*}
\frac{1}{2}(x^{2}-s)s+ \frac{1}{2}s^{2}+x^{2}-s&= x^{1}\\
\frac{1}{2}x^{2}s+x^{2}-s &= x^{1}\\
s&= \frac{x^{1}-x^{2}}{\frac{1}{2}x^{2}-1}
\end{align*}$$
And $$x_{0}=x^{2}- \frac{x^{1}-x^{2}}{\frac{1}{2}x^{2}-1}=\frac{x^{2}(\frac{1}{2}x^{2}-1)-(x^{1}-x^{2})}{\frac{1}{2}x^{2}-1}= \frac{\frac{1}{2}(x^{2})^{2}-x^{1}}{\frac{1}{2}x^{2}-1}$$
Then,
$$\begin{align*}
u(x^{1},x^{2})=z_{0}+s&= \frac{1}{2}\frac{\frac{1}{2}(x^{2})^{2}-x^{1}}{\frac{1}{2}x^{2}-1}+\frac{x^{1}-x^{2}}{\frac{1}{2}x^{2}-1}\\
&= \frac{\frac{1}{4}(x^{2})^{2}- \frac{1}{2}x^{1}+x^{1}-x^{2}}{\frac{1}{2}x^{2}-1}\\
&= \frac{\frac{1}{4}(x^{2})^{2}-x^{2}+ \frac{1}{2}x^{1}}{\frac{1}{2}x^{2}-1}\\
u(x^{1},x^{2})&=  \frac{\frac{1}{2}(x^{2})^{2}-2x^{2}+x^{1}}{x^{2}-2}
\end{align*}$$
First, let's check the boundary condition, $u(x_{1},x_{1})= \frac{1}{2}x_{1}$.
$$u(x^{1},x^{1})=\frac{\frac{1}{2}(x^{1})^{2}-x^{1}}{x^{1}-2}= \frac{1}{2}x^{1}$$
Let's check that the PDE holds
$$u_{x^{1}}= \frac{1}{x^{2}-2}, \qquad u_{x^{2}}=\frac{-x^{1}+ \frac{1}{2}(x^{2})^{2}-2x^{2}+4}{(x^{2}-2)^{2}}$$
$$\begin{align*}
uu_{x^{1}}+u_{x^{2}}&= \frac{\frac{1}{2}(x^{2})^{2}-2x^{2}+x^{1}}{x^{2}-2} \cdot \frac{1}{x^{2}-2}+\frac{-x^{1}+ \frac{1}{2}(x^{2})^{2}-2x^{2}+4}{(x^{2}-2)^{2}}\\
&= \frac{(x^{2})^{2}-4x^{2}+4}{(x^{2}-2)^{2}}=1,
\end{align*}$$
which holds!


![[Pasted image 20230831130335.png]]

$$J(s, x,t):=\text{ det}D_{x}\mathbf{x}(s,x,t)=\left\lvert \begin{bmatrix}\partial_{x_{1}}x_{1} & \dots  & \partial_{x_{n}}x_{1} \\ \vdots &   & \vdots \\ \partial_{x_{1}}x_{n} & \dots & \partial_{x_{n}}x_{n} \end{bmatrix} \right\rvert$$
$$\dot{\mathbf{x}}(s)=\mathbf{b}(\mathbf{x}) \quad\Leftrightarrow\quad \begin{bmatrix}\dot{x}_{1} \\ \vdots \\ \dot{x}_d\end{bmatrix} =\begin{bmatrix}\mathbf{b}(\mathbf{x})_{1} \\ \vdots  \\ \mathbf{b}(\mathbf{x})_d\end{bmatrix}$$



![[Pasted image 20230831130344.png]]