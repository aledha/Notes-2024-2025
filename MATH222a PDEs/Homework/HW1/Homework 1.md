Alexander Hatle, 09/01/23
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
\dot{x}^{j}(s)&= \partial_{p_{j}}F(x(s),z(s),p(s)),\\
	\dot{z}(s)&= \sum\limits_{j}^{}\partial_{p_{j}}F(x(s),z(s),p(s))p_{j}(s),\\
			\dot{p}_{j}(s)&= - \partial_{x^{j}}F(x(s),z(s),p(s))-\partial_{z}F(x(s),z(s),p(s)) p_{j}(s)\tag{1}.
\end{align*}$$
In our case,

$$u_{t}+tu_{x}=f, \qquad u(0,x)=u_{0}(x),$$
$$\dot{t}(s)=1\text{, }\qquad \dot{x}(s)=t, \qquad \dot{z}(s)=p_{t}+tp_{x}=f.$$
Solving the ODEs for $t$ and $x$ yields 
$t(s)=s, \qquad x(s)=x_{0}+ \frac{1}{2}s^{2}$.

Now, given a $(t,x) \in R^{2}$, we should be able to find $x_{0}\text{, }s$ such that $t(s)=t,\quad  x(s)=x$. 
This results in $s=t, \quad x_{0}=x- \frac{1}{2}t^{2}$. 
Solving the ODE for $z$ gives
$$z(s)=u_{0}(x_{0})+\int_{0}^{s}f(t(\tau ),x(\tau ))\text{ d}\tau  .$$
Inserting for $x_{0}$, and using our expressions for $t(s),x(s)$ results in
$$u(x,t)=u_{0}\left(x- \frac{1}{2}t^{2}\right)+\int_{0}^{t}f\left(\tau ,x+ \frac{1}{2}(\tau^{2}-t^{2})\right)\text{ d}s.$$


![[Pasted image 20230828185154.png]]
$F$ can be written as
$$\begin{align*}
F(x,z,p) &= x^{1}(s)p_{1}(s)+x^{2}(s)p_{2}(s)-2z(s)=0.\tag{2}
\end{align*}$$
Using the characteristic equations, $(1)$,
$$\dot{x}^{1}(s)=x^{1}(s)\text{, }\qquad \dot{x}^{2}(s)=x^{2}(s),$$
$$\dot{z}(s)=x^{1}(s)p_{1}(s)+x^{2}(s)p_{2}(s)\stackrel{(2)}{=}2z(s).$$
Solving and using our B.C. gives
$x^{1}(s)=x_{0}e^{s}\text{, }\qquad x^{2}(s)=1\cdot e^{s}\text{, }\qquad z(s)=g(x_{0})e^{2s}.$

Given a point $(x^{1},x^{2})$, we need to find $x_{0}\text{, }s$ such that $x^{1}(s)=x^{1}\text{ and }x^{2}(s)=x^{2}$. We see that $s=\text{ ln }x^{2}$, and therefore $x_{0}=\frac{x^{1}}{x^{2}}$. We must impose that $x^{2}>0$.

Inserting $s$ and $x_{0}$ gives us our solution
$$u(x)=g\left(\frac{x^{1}}{x^{2}}\right)e^{2\text{ ln}x^{2}}=g\left(\frac{x^{1}}{x^{2}}\right)(x^{2})^{2}.$$
Let us check that $u$ solves the PDE holds,
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
$$\dot{x}^{1}=x^{1}\text{, }\quad \dot{x}^{2}=2x^{2}\text{, }\quad \dot{x}^{3}=1,$$
$$\dot{z}=x_{1}p_{1}+2x^{2}p_{2}+ p_{3}=3z.$$
Solving these ODEs yields
$$\begin{align*}
x^{1}(s)=x^{1}_{0}e^{s}\text{, }\quad x^{2}(s)&= x_{0}^{2}e^{2s}\text{, }\quad x^{3}(s)=s,\\
z(s)&= g(x^{1}_{0},x^{2}_{0})\cdot e^{3s}.
\end{align*}$$
If $x(s)=(x^{1}\text{, }x^{2}\text{, }x^{3})$, then $s=x^{3}$, and we get the equations
$$\begin{cases}
x^{1}(x^{3}) & =x_{0}^{1}e^{x^{3}} & =x^{1}, \\
x^{2}(x^{3}) & =x_{0}^{2}e^{2x^{3}} & =x^{2},
\end{cases}$$
resulting in $x_{0}^{1}=x^{1}e^{-x^{3}}\text{, }\quad x_{0}^{2}=x^{2}e^{-2x^{3}}$.

The solution reads
$$u(x)=g(x^{1}e^{-x^{3}}\text{, }x^{2}e^{-2x^{3}})\cdot e^{3x^{3}}.$$

![[Pasted image 20230828185219.png]]
$F$ can be written as
$$F(x,z,p)=zp_{1}+p_{2}-1$$
Our characteristic equations are
$$\dot{x}^{1}=z, \quad \dot{x}^{2}=1\text{, }\quad \dot{z}=zp_{1}+p_{2}=1.$$
Solving these,
$x^{1}(s)= z_{0}s+ \frac{1}{2}s^{2}+ x_{0},\qquad x^{2}(s)=s+x_{0}, \qquad z(s)=z_{0}+s$.

Finding $x_{0},s$
$$\begin{cases}
x^{1}(s)= z_{0}s+\frac{1}{2}s^{2}+x_{0} & =x^{1}, \\
x^{2}(s)=s+x_{0} & =x^{2}.
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
$$u_{x^{1}}= \frac{1}{x^{2}-2}, \qquad u_{x^{2}}=\frac{-x^{1}+ \frac{1}{2}(x^{2})^{2}-2x^{2}+4}{(x^{2}-2)^{2}},$$
$$\begin{align*}
uu_{x^{1}}+u_{x^{2}}&= \frac{\frac{1}{2}(x^{2})^{2}-2x^{2}+x^{1}}{x^{2}-2} \cdot \frac{1}{x^{2}-2}+\frac{-x^{1}+ \frac{1}{2}(x^{2})^{2}-2x^{2}+4}{(x^{2}-2)^{2}},\\
&= \frac{(x^{2})^{2}-4x^{2}+4}{(x^{2}-2)^{2}}=1,
\end{align*}$$
which holds!


![[Pasted image 20230831130335.png]]
The Jacobian is
$$J(s, x,t):=\text{ det}D_{x}\mathbf{x}(s,x,t)=\left\lvert \begin{bmatrix}\partial_{x_{1}}x_{1} & \dots  & \partial_{x_{n}}x_{1} \\ \vdots &   & \vdots \\ \partial_{x_{1}}x_{n} & \dots & \partial_{x_{n}}x_{n} \end{bmatrix} \right\rvert.$$
Taking the Jacobian matrix of both sides of the ODE, and using the chain rule,
$$\begin{align*}
D_{x}\dot{\mathbf{x}}(s)&= D_{x}\mathbf{b}(\mathbf{x}(s,x,t)),\\
	\frac{\text{d}}{\text{d}s}D_{x}\mathbf{x}(s,x,t)&= D_{\mathbf{x}}\mathbf{b}(x) \cdot (D_{x}\mathbf{x}).\\
\end{align*}$$
Using Jacobi's formula $\frac{\text{d}}{\text{d}s}\text{ det}A=\text{ det}A \text{ tr }\left( A^{-1} \frac{\text{d}A}{\text{d}s}\right)$.
$$\begin{align*}
\frac{\text{d}}{\text{d}s}\text{ det }D_{x}\mathbf{x}&= \text{ det}D_{x}\mathbf{x} \text{ tr }\left((D_{x}\mathbf{x})^{-1}\frac{\text{d}D_{x}\mathbf{x}}{\text{d}s}\right),\\
J_{s}&= J \cdot \text{tr }((D_{x}\mathbf{x})^{-1}D_{\mathbf{x}}\mathbf{b}(x)(D_{x}\mathbf{x})),\\
J_{s}&= J \cdot \text{ tr }(D_\mathbf{x}\mathbf{b})=J \cdot (\partial_{x^{1}}b(\mathbf{x})_{1}+ \dots + \partial_{x^{d}}b(\mathbf{x})_{d}),\\
J_{s}&= J(\text{div }\mathbf{b}(\mathbf{x})).
\end{align*}$$
![[Pasted image 20230831130344.png]]
Characteristic equations:
$$\dot{x}(s)=b(\mathbf{x}(s,x,t)), \qquad \dot{z}=p_{t}=-\text{ div}(z \mathbf{b}), \qquad \dot{t}=1$$
We see that $t=s$
$$\begin{align*}
z(s)&= z_{0}-\int_{0}^{s}\text{ div}\Big(z\big(\tau \big)\cdot b\big(\mathbf{x}(\tau ,x,t)\big)\Big)\text{ d}\tau \\
&= z_{0}-\int_{0}^{s}z(\tau )(\partial_{x^{1}}b(\mathbf{x}(\tau ))_{1}+ \dots + \partial_{x^{d}}b(\mathbf{x}(\tau ))_{d})\text{ d}\tau 
\end{align*}$$
I'm kinda stuck here.