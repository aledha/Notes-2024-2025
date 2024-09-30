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
