To find the derivative of $\tan x \sin x$, we will use the Product Rule:

**Product Rule**: If $f(x) = g(x) \cdot  h(x)$, then $f'(x) = g'(x) \cdot h(x) + g(x) \cdot h'(x)$

Let $f(x) = \tan x\sin x$ Then $g(x) = \tan x$ and $h(x) = \sin x$.

**Now find the derivatives of g(x) and h(x):** 
To find the derivative of $g(x)=\tan x = \frac{\sin x}{\cos x}$, we will use the quotient rule, which is similar to the product rule:

**Quotient rule:** if $g(x)=\frac{u(x)}{v(x)},$ then $g'(x)=\frac{u'(x)v(x)-u(x)v'(x)}{(v(x))^2}$.

Letting $u(x)=\sin x$ and $v(x)=\cos x$, we get 

$$
\begin{aligned}
g'(x)&= \frac{\cos x \cos x-\sin x(-\sin x)}{\cos ^2 x},\\
&= \frac{\cos ^2x+\sin ^2 x}{\cos ^2 x},\\
&= \frac{1}{\cos ^2 x},
\end{aligned}
$$
where we used the Pythagorean Identity in the second line.

The derivative of $h(x)$ is $h'(x)=\cos x$

**Plug these values into the Product Rule formula:** $f'(x) = g'(x) \cdot h(x) + g(x) \cdot h'(x)$ 

$$
\begin{aligned}
f'(x) &=  \frac{\sin x}{\cos ^2 x} + \tan x \cdot \cos x\\
&= \frac{\tan x}{\cos x}+\tan x \cdot \cos x\\
&= \left(\frac{1}{\cos x}+\cos x \right)\tan x
\end{aligned}
$$

**That's the simplest form of the derivative. So,** 
$$\frac{\text{d}}{\text{d}x}(\tan x \sin x) = \left(\frac{1}{\cos x}+\cos x \right)\tan x.$$