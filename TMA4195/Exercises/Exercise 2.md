![[Pasted image 20240930130151.png|800]]
For unscaled $x^{*}$:
$$u(x^{*})=e^{-10x^{*}}+e^{-100x^{*}} \quad\text{for }x \in [0,1]$$
We notice that $u$ has three distinct behaviours for different values of $x$. For small $x$, both terms are relevant. For intermediate $x$, the first term dominates over the second term. For $x$ near $1$, both terms tend to zero.
* $x= 100\cdot x^{*}$ such that $e^{-100x}\sim1$ when $x\sim1$.
* $x=10\cdot x^*$ such that $e^{-10x}\sim1$ when $x\sim1$.
* $x=1\cdot x^{*}$ such that $u\sim0$ when $x\sim1$.

*Rule*: we can approximate $e^{-x}\approx1$ when $x<\frac{1}{5}$.

For $x=100\cdot x^{*}$:
$$u(x)=e^{-\frac{x}{10}}+e^{-x}$$
So $e^{-\frac{x}{10}}\approx1$ when $\frac{x}{10}<\frac{1}{5}$ or when $x<2$. This corresponds to $x^{*}<\frac{2}{100}$.

For $x=10x^{*}$:
$$u(x)=e^{-x}+e^{-10x}.$$
So $e^{-10x}\approx1$ when $10x<\frac{1}{5}$ or when $x<2$. This corresponds to $x^{*}<\frac{2}{10}$.

The last is the remaining values, which are for $\frac{2}{5}<x^{*}<1$.

![[Pasted image 20240930132535.png|800]]
$$
\begin{aligned}
m'(t)&= -\alpha  &m(0)&=M \\
x''(t)&= \frac{\alpha \beta }{m(t)}-\frac{g}{\left(1+\frac{x(t)}{R} \right)^{2}}\qquad &x(0)&= x'(0)=0
\end{aligned}
$$
*Scaling*
* $m\to Mm$
* $x\to Rx$
* $t\to Tt$
This results in 
$$\begin{aligned}
\frac{R}{T^{2}}x''(t)&= \frac{\alpha \beta }{Mm(t)}-\frac{g}{(1+x(t))^{2}}\\
x''(t)&= \frac{T^{2}\alpha \beta }{RM}\frac{1}{m(t)}- \frac{gT^{2}}{R}\frac{1}{(1+ x(t))^2}
\end{aligned}$$
Set $\frac{T^{2}\alpha \beta }{RM}=1\quad\implies\quad T= \sqrt{\frac{RM}{\alpha \beta }}$. Then, our set of equations is

$$\begin{aligned}
m'(t)&= -\frac{\alpha }{M}\sqrt{\frac{RM}{\alpha \beta }}=-\sqrt{\frac{\alpha R}{\beta M}}\\
x''(t)&= \frac{1}{m(t)}-\frac{gM}{\alpha \beta }\frac{1}{(1+x(t))^{2}}
\end{aligned}$$

$$\begin{aligned}
m'(t)&= -\mu \\
x''(t)&= \frac{1}{m(t)}-\xi \frac{1}{(1+x(t))^{2}}
\end{aligned}$$

![[Pasted image 20240930153322.png|900]]
Let $y=y_{0}(t)+\epsilon y_{1}(t)+\epsilon ^{2}y_{2}(t)$, and substitute into the equation:
Since 
$$\begin{aligned}
y(0)&= 0\quad\implies\quad y_{0}(0)=y_{1}(0)=y_{2}(0)=0\\
y'(0)&= 0\quad\implies\quad y_{0}'(0)=y_{1}'(0)=y_{2}'(0)=0
\end{aligned}$$

$$
\begin{aligned}
y_{0}''(t)+\epsilon y_{1}''(t)+\epsilon ^{2}y_{2}''(t)+\epsilon y_{0}'(t)+\epsilon ^{2}y_{1}'(t)+1&= 0\\
y_{0}''(t)+1+\epsilon (y_{1}''(t)+y_{0}'(t))+\epsilon ^{2}(y_{2}''(t)+y_{1}'(t))&= 0
\end{aligned}
$$
Since this holds for all $0<\epsilon \ll 1$, we get a system of equations:
$$
\begin{aligned}
y''_{0}(t)+1&= 0\\
y''_{1}(t)+y_{0}'(t)&= 0\\
y_{2}''(t)+y'_{1}(t)&= 0
\end{aligned}
$$
From the first equation, we get
$$\begin{aligned}
y_{0}''(t)&= -1\\
y_{0}(t)&= -\frac{1}{2}t^{2}+B_{0}t+A_{0}\\
	y_{0}(0)=y_{0}'(0)=0 \quad\implies\quad y_{0}(t)&= -\frac{1}{2}t^{2}
\end{aligned}$$
Using this in the second equation,
$$\begin{aligned}
y_{1}''(t)-t&= 0\\
y_{1}''(t)&= t\\
y_{1}(t)&= \frac{1}{6}t^3
\end{aligned}$$

$$\begin{aligned}
y_{2}''(t)&= -\frac{1}{2}t^{2}\\
y_{2}(t)&= -\frac{1}{24}t^{4}
\end{aligned}$$

Thus, the approximate solution is
$$y(t)=-\frac{1}{2}t^{2}+\frac{\epsilon }{6}t^{3}-\frac{\epsilon ^{2}}{24}t^{4}$$

The general solution has the form
$$\begin{aligned}
y(t)&= A+Be^{-\epsilon t}- \frac{t}{\epsilon }\\
y'(0)&=-\epsilon B-\frac{1}{\epsilon }=0\\
B&= -\frac{1}{\epsilon ^{2}}\\
y(t)&= A-\frac{1}{\epsilon ^{2}}e^{-\epsilon t}-\frac{t}{\epsilon } \\
y(0)=0\quad\implies\quad A&= \frac{1}{\epsilon ^{2}}
\end{aligned}$$
Taylor expand:
$$\begin{aligned}
y(t)&= \frac{1}{\epsilon ^{2}}(1-e^{-\epsilon t})-\frac{t}{\epsilon }\\
&= \frac{1}{\epsilon ^{2}}\left(1- \sum_{n=0}^{\infty}\frac{(-\epsilon t)^{n}}{n!} \right)-\frac{t}{\epsilon }\\
&= \frac{1}{\epsilon ^{2}}\left(-\sum_{n=1}^{\infty}\frac{(-\epsilon t)^{n}}{n!} \right) -\frac{t}{\epsilon }\\
&= \frac{1}{\epsilon ^{2}}\left(\epsilon t-\frac{\epsilon ^{2}t^{2}}{2}+\frac{\epsilon ^{3}t^{3}}{6}-\frac{\epsilon ^{4}t^{4}}{24}+\dots \right)-\frac{t}{\epsilon }\\
&= \frac{t}{\epsilon }-\frac{t^{2}}{2}+\frac{\epsilon t^{3}}{6}-\frac{\epsilon ^{2}t^{4}}{24}+\dots-\frac{t}{\epsilon }\\
&= -\frac{t^{2}}{2}+\frac{\epsilon t^{3}}{6}-\frac{\epsilon ^{2}t^{4}}{24}+\dots
\end{aligned}$$

