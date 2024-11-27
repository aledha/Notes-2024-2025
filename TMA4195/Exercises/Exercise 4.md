# Q1
![[Pasted image 20241124141816.png|800]]
Let $y=y_0 +\epsilon y_1 +\mathcal{O}(\epsilon ^2)$, then
$$\begin{aligned}
\epsilon y''+(1+x)y'+y&= 0\\
\epsilon y_0+(1+x)(y_0'+\epsilon y_1')+y_0+\epsilon y_1&= 0\\
(y_0+(1+x)y'_1+y_1)\epsilon +((1+x)y_0'+y_0)&= 0
\end{aligned}$$
### Outer solution
![[Pasted image 20241124144438.png|300]]
We start by solving the outer solution. Since the boundary layer is at $x=0$, we use the BC that $y(1)=1$ for the outer solution
$$\begin{aligned}
(1+x)y'_0+y_0 &= 0\\
((1+x)y_0)'&= 0\\
(1+x)y_0&= C\\
y_0 &= \frac{C}{1+x}\\
y_0(1)&= \frac{C}{2}=1\\
y_0(x)&= \frac{2}{1+x}
\end{aligned}$$
Since we are looking for leading order (0th order) we only care about $y_0$, which is the outer solution.

### Inner solution
We postulate that
$$y(x)=Y \left(\frac{x}{\delta (\varepsilon )} \right),$$
on the inner solution, where $\delta (\varepsilon )$ is some function.  Let $\eta  =\frac{x}{\delta (\varepsilon )}$,
$$\begin{aligned}
\varepsilon \frac{\partial ^2}{\partial x^2}Y \left(\frac{x}{\delta (\varepsilon )} \right)+(1+x)\frac{\partial }{\partial x}Y \left(\frac{x}{\delta (\varepsilon )} \right)+Y \left(\frac{x}{\delta (\varepsilon )} \right)&= 0\\
 \varepsilon \frac{1}{\delta (\varepsilon )^2}Y''(\eta )+(1+\delta (\varepsilon )\eta )\frac{1}{\delta (\varepsilon )}Y'(\eta )+Y(\eta )&= 0
\end{aligned}$$
let $\delta (\varepsilon )=\varepsilon$,
$$\begin{aligned}
\frac{1}{\varepsilon }Y''+\left(\frac{1}{\varepsilon }+\eta  \right)Y'+Y&= 0\\
Y''+(1+\varepsilon \eta )Y'+\varepsilon Y&= 0
\end{aligned}$$
Let $Y=Y_0+\varepsilon Y_1$:
$$\begin{aligned}
Y_0''+\varepsilon Y_1''+Y_0'+\varepsilon Y_1'+\varepsilon \eta Y_0'+\varepsilon Y_0&= 0\\
Y_0''+Y_0'&= 0
\end{aligned}$$
Solving
$$\begin{aligned}
\lambda ^2 +\lambda &= 0\\
\lambda_1 &= 0\\
\lambda _2 &= -1,
\end{aligned}$$
which gives the general solution
$$\begin{aligned}
Y_0&= C_1e^{\lambda _1 \eta }+C_2e^{\lambda _2 \eta }\\
&= C_1+C_2 e^{-\eta }
\end{aligned}$$
Since we are at the inner solution, we use the BC $Y_0(0)=0$:
$$\begin{aligned}
Y_0(0)&= C_1+C_2=0\\
Y_0(\eta )&= C_1 -C_1e^{-\eta }\\
&= K(1-e^{-\eta })
\end{aligned}$$
### Match inner and outer
Matching condition:
$$\begin{aligned}
\lim_{\eta  \to \infty}Y(\eta )&= \lim_{x \to 0}y(x)\\
\lim_{\eta  \to \infty}K(1-e^{-\eta })&= \lim_{x \to 0}\frac{2}{1+x}\\
K&= 2
\end{aligned}$$
Then, the uniform solution is
$$\begin{aligned}
y^u&= y(x)+Y\left(\frac{x}{\varepsilon }\right)-\lim_{x \to 0}y(x)\\
&= \frac{2}{1+x}+2(1-e^{-x/\varepsilon })-2\\
&= \frac{2}{1+x}-2e^{-x/\varepsilon }
\end{aligned}$$

## Q2
![[Pasted image 20241124155640.png|800]]
$y=y_0+\varepsilon y_1$
### Outer solution
Corresponds to the BC $y(1)=1/2$
$$\begin{aligned}
\varepsilon y_0''+y_0'+\varepsilon y_1'+y_0^2+2\epsilon y_0y_1&= \mathcal{O}(\varepsilon ^2)\\
y'_0+y_0^2&= 0\\
\frac{\text{d}y_0}{\text{d}x}&= -y_0^2\\
\int y_0^{-2}\text{ d}y_0&= -\int \text{ d}x\\
-y_0^{-1}&= -x+C\\
y_0(x)&= \frac{1}{x-C}\\
y_0 (1)&= \frac{1}{1-C}=\frac{1}{2}\\
C&= -1\\
y_0(x)&= \frac{1}{x+1}
\end{aligned}$$
### Inner solution
Let $\eta =\frac{x}{\varepsilon}$ and
$$Y\left(\frac{x}{\varepsilon }\right)=y(x)$$
then,
$$\begin{aligned}
\varepsilon \frac{\text{d}^2}{\text{d}x^2}Y\left(\frac{x}{\varepsilon }\right)+\frac{\text{d}}{\text{d}x}Y\left(\frac{x}{\varepsilon }\right)+Y\left(\frac{x}{\varepsilon }\right)^2&= 0\\
	\frac{1}{\varepsilon }Y''+\frac{1}{\varepsilon }Y'+Y^2&= 0\\
Y''+Y'+\varepsilon Y^2&= 0\\
Y_0''+\varepsilon Y_1''+Y_0'+\varepsilon Y_0'+\varepsilon Y_0^2&= \mathcal{O}(\varepsilon ^2)\\
Y_0''+Y_0'&= 0
\end{aligned}$$
using lambda tricks 
$$\begin{aligned}
\lambda ^2+\lambda &= 0\\
\lambda _0&= 0\\
\lambda _1&= -1
\end{aligned}$$
giving us the general solution
$$\begin{aligned}
Y_0&= C_1e^{\lambda _0 \eta }+C_2e^{\lambda _1 \eta }\\
&= C_1+C_2 e^{-\eta }
\end{aligned}$$
Since we are at the inner solution, we use the BC $Y_0(0)=\frac{1}{4}$:
$$\begin{aligned}
Y_0(0)&= C_1+C_2=\frac{1}{4}\\
Y_0(\eta )&= \frac{1}{4}-C_2+C_2e^{-\eta }\\
&= \frac{1}{4}+K(-1+e^{-\eta })
\end{aligned}$$
Matching condition:
$$\begin{aligned}
\lim_{\eta  \to \infty}Y(\eta )&= \lim_{x \to 0}y(x)\\
\lim_{\eta  \to \infty}\frac{1}{4}+K(-1+e^{-\eta })&= \lim_{x \to 0}\frac{1}{1+x}\\
\frac{1}{4}-K&= 1\\
K&= -\frac{3}{4}
\end{aligned}$$
Then,
$$\begin{aligned}
Y_0 (\eta ) &= \frac{1}{4}+\frac{3}{4}-\frac{3}{4}e^{-\eta }\\
&= 1-\frac{3}{4}e^{-\eta }
\end{aligned}$$
Uniform:
$$\begin{aligned}
y^u&= y(x)+Y\left(\frac{x}{\varepsilon }\right)-\lim_{x \to 0}y(x)\\
&= \frac{1}{1+x}+1-\frac{3}{4}e^{-x/\varepsilon }-1\\
&= \frac{1}{1+x}-\frac{3}{4}e^{-x/\varepsilon }
\end{aligned}$$
![[Pasted image 20241124170216.png|800]]
Since the problem is symmetric around $x=0$, we can solve with the BCs $u'(0)=0$ and $u(1)=1$. 
A simpler way to see that $u$ is even: set $v(x)=u(-x)$, then
$$\begin{aligned}
\epsilon (-1)^2v''-(2-(-x)^2)v&= -1\\
\varepsilon v''-(2-x^2)v&= -1
\end{aligned}$$
so $u$ is even and must therefore have $u'(0)=0$.

Note that for $x≈1$, 
$$\begin{aligned}
\varepsilon u''-\underbrace{(2-1)u(1)}_{≈0}&= -1\\
\varepsilon u''&≈-1
\end{aligned}$$
and that $\lvert u''(x\sim1) \rvert>>1$. 
We therefore assume that the boundary layer is at $x=1$. 
### Outer solution
Using the BC $u(1)$ and the expansion $u=u_0+\varepsilon u_1$:
$$\begin{aligned}
\varepsilon u_0 ''-(2-x^2)(u_0+\varepsilon u_1)&= -1\\
\varepsilon (u_0''-(2-x^2)u_1)-(2-x^2)u_0&= -1\\
\text{leading order:}\qquad (2-x^2)u_0&= 1\\
u_0(x)&= \frac{1}{2-x^2}
\end{aligned}$$

### Inner solution
Since the boundary layer is now at $x=1$, we set $\eta =\frac{1-x}{\delta (\varepsilon) }$, and $U\left(\frac{1-x}{\delta (\varepsilon) }\right)=u(x)$. Then,
$$\begin{aligned}
\varepsilon \partial _x^2U-(2-x^2)U&= -1\\
\frac{\varepsilon }{\delta (\varepsilon)^2 }U''-(2-x^2)U&= -1\\
\frac{\varepsilon }{\delta (\varepsilon)^2 }U''-(2-\left(1-\delta (\varepsilon )\eta  \right)^2)U&= -1\\
\frac{\varepsilon }{\delta (\varepsilon)^2 }U''-(2-\left(1-2\delta (\varepsilon )\eta+(\delta (\varepsilon )\eta )^2  \right))U&= -1\\
\frac{\varepsilon }{\delta (\varepsilon)^2 }U''-(1+2)U&= -1
\end{aligned}$$