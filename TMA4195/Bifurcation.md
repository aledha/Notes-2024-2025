"When things split in two"
Considering stability properties when we have an additional parameter.

Start with an example
$$\begin{aligned}
u'&= -u(u-1)(u-2)+\mu \\
&= f(\mu ,u)
\end{aligned}$$
When $\mu =0$, then $f$ is a third degree polynomial:
![[IMG_0302.jpg|300]]

$u=2$ is stable, while $u=1$ is unstable. Solution might oscillate around $u=2$.

If $\mu$ increases more and more, the stable equilibrium point moves to the right, and eventually the unstable point will disappear: 
![[IMG_0303.jpg|300]]
Say we started at $u=0$ and $\mu$ increases past the critical value so that one equilibrium point vanishes, then the system goes to the closest other point.
![[IMG_0303 2.jpg|300]]
## Bifurcation diagram
Another example:
$$u'=(u-\mu )(u-\mu ^{3})=:f(\mu ,u)$$
$f(\mu ,u)=0 \quad\implies\quad u_{e}=\mu ,\quad u_{e}=\mu ^{3}$.
The bifurcation diagram is the two curves for $u_{e}$:

![[IMG_0304.jpg|400]]
To finish the diagram, we need to mark the stability of the equilibrium points.

$$\begin{aligned}
f(\mu ,u)&= u ^{2}-(\mu +\mu ^{3})u+\mu ^{4}\\
\frac{\partial f}{\partial u}&= 2u-(\mu +\mu ^{3})
\end{aligned}$$
we want to track the sign of this partial derivative along the curves.
Along $u=\mu$:
$$\begin{aligned}
\frac{\partial f}{\partial u}(\mu ,\mu )&= 2\mu -\mu -\mu ^{3}\\
&=  \mu(1 -\mu ^{2})
\end{aligned}$$

---

Find the solutions to
$$f(\mu ,u)=0$$
in the $\mu u$-plane to make a bifurcation diagram.

Then classify equilibrium points:
* If $\frac{\partial f}{\partial u}<0$ we have asymptotically unstable.
* If $\frac{\partial f}{\partial u}>0$ unstable.

From previous example
$$\begin{aligned}
f(\mu ,u)&=  u ^{2}-(\mu +\mu ^{3})u+\mu ^{4}\\
\frac{\partial f}{\partial u}&= 2u-(\mu +\mu ^{3})\\
\end{aligned}$$
For $u=\mu$:
$$\begin{aligned}
\frac{\partial f}{\partial u}&= 2\mu -\mu -\mu ^{3}\\
&= \mu (1-\mu ^{2})\\
&= \mu (1-\mu )(1+\mu )
\end{aligned}$$
So $\frac{\partial f}{\partial u}<0$ for $\mu \in (-1,0)\cup(1,\infty)$ $\quad\implies\quad$ *stable*.

For $u=\mu ^{3}$:
$$\begin{aligned}
\frac{\partial f}{\partial u}&= 2\mu ^{3}-(\mu +\mu ^{3})\\
&= \mu ^{3}-\mu \\
&= -(\mu -\mu ^{3})
\end{aligned}$$
*Stable* for $\mu \in (-\infty,-1)\cup(0,1)$.

#insert diagram

We have three intersection points for $\mu =-1,0,1$.
* $\mu =-1:\quad u'=(u+1)^{2}$
* $\mu =0:\quad u'=u^{2}$
* $\mu =1:\quad u'=-(u-1)^{2}$

$$\begin{aligned}
u'&= (u-\mu )^{2}\\
\frac{\text{ d}u}{(u-\mu )^{2}}&= \text{ d}t\\
-\frac{1}{u-\mu }&= t-C\\
u&= \mu +\frac{1}{C-t}\\
u_{0}&= \mu +\frac{1}{C} \quad\implies\quad C=\frac{1}{u_{0}-\mu }\\
u(t)&= \mu + \frac{1}{\frac{1}{u_{0}-\mu }-t}\\
u(t)&= \mu +\frac{u_{0}-\mu }{1-(u_{0}-\mu )t}
\end{aligned}$$

## Chemical Tank

* $c(t):$ concentration of chemical
* $\theta (t):$ temperature
The reaction rate is 
$$ke^{-\frac{A}{\theta (t)}}c(t)$$
where $[k]=\text{s}^{-1}$ and $[c]=\text{molm}^{-3}$.

$$\begin{aligned}
(Vc(t))'&= -Vke^{-\frac{A}{\theta (t)}}c(t)+qc_{\text{in}}-qc(t)\\
c'(t)&= -ke^{-\frac{A}{\theta (t)}}c(t)+\frac{q}{V}(c_{\text{in}}-c(t)
\end{aligned}$$
The heat density per second (power density) is
$$hke^{-\frac{A}{\theta (t)}}c(t),$$
where $h$ is a constant. $[hke^{-\frac{A}{\theta (t)}}c(t)]=\mathrm{Js^{-1}m^{-3}}$, so $[h]=\mathrm{Jmol^{-1}}$.

$C_{V}$ heat capacity: $\theta (t)C_{V}V$ total thermal energy in tank.

$$\begin{aligned}
(VC_{V}\theta (t))'&= Vhke^{-\frac{A}{\theta (t)}}c(t) + q \theta _{\text{in}} C_{V}-q \theta (t)C_{V}\\
\theta'(t)&=  \frac{hk}{C_{V}}e^{-\frac{A}{\theta (t)}}+ \frac{q}{V}\left(\theta _{\text{in}}-\theta (t) \right)
\end{aligned}$$

So we have the problem
$$
\begin{aligned}
c'(t)&= -ke^{-\frac{A}{\theta (t)}}c(t)+\frac{q}{V}(c_{\text{in}}-c(t)\\
\theta'(t)&=  \frac{hk}{C_{V}}e^{-\frac{A}{\theta (t)}}+ \frac{q}{V}\left(\theta _{\text{in}}-\theta (t) \right)\\
c(0)&= c_{\text{in}},\qquad \theta (0)=\theta _{\text{in}}
\end{aligned}
$$
We are going to vary $q$ and see the results. Experiments show that flushing slowly increases temperature, which we want to explain. When we increase the rate, we lose an equilibrium point.

### Scale the equations
* $t\to \frac{V}{q}t$    (time it takes to fill the tank)
* $c\to c_{\text{in}}c$
* $\theta \to \theta _{\text{in}}\theta$

Then,
$$
\begin{aligned}
\frac{q}{V}c_{\text{in}}c'(t)&= -ke^{-\frac{A}{\theta _{\text{in}}\theta (t)}}c_{\text{in}}c(t)) +\frac{q}{V}(c_{\text{in}}-c_{\text{in}}c(t))\\
c'(t)&= -\frac{Vk}{q}e^{-\frac{A}{\theta _{\text{in}}}\frac{1}{\theta (t)}}c(t)+1-c(t)\\
c'(t)&= -\frac{1}{\mu }e^{-\frac{\gamma }{\theta (t)}}c(t)+1-c(t),
\end{aligned}
$$
where $\mu = \frac{q}{Vk}$ and $\gamma =\frac{A}{\theta _{\text{in}}}$.


$$\begin{aligned}
\frac{q}{V}\theta _{\text{in}}\theta'(t)&=  \frac{hk}{C_{V}}e^{-\frac{A}{\theta _{\text{in}}\theta (t)}}c_{\text{in}}c(t)+ \frac{q}{V}\left(\theta _{\text{in}}-\theta _{\text{in}}\theta (t) \right)\\
\theta '(t)&= \frac{Vhk}{qC_{V}\theta _{\text{in}}}e^{-\frac{\gamma }{\theta }}c_{\text{in}}c(t)+1-\theta (t)\\
\theta'(t)&= \frac{1}{\mu }\frac{hc_{\text{in}}}{C_{V}\theta _{\text{in}}}e^{-\frac{\gamma }{\theta (t)}}c(t)+1-\theta (t)\\
\theta'(t)&= \frac{\eta }{\mu }e^{-\frac{\gamma }{\theta (t)}}+1-\theta (t),
\end{aligned}$$
where $\eta =\frac{hc_{\text{in}}}{C_{V}\theta _{\text{in}}}$.

Multiply the equation for $c'(t)$ with $\eta$:
$$\eta c'(t)=-\frac{\eta }{\mu }e^{-\frac{\gamma }{\theta (t)}}+\eta -\eta c(t)$$
Add this equation with the equation for $\theta'(t)$ to get
$$\begin{aligned}
\theta '(t)+\eta c'(t)&= 1-\theta (t)+\eta -\eta c(t)\\
(\theta (t)+\eta c(t))'&= 1+\eta -(\theta +\eta c(t))
\end{aligned}$$
denote $h(t)=\theta (t)+\eta c(t)$. Then $h(0)=1+\eta$ and
$$\begin{aligned}
h'(t)&= 1+\eta -h\\
h(t)&= 1+\eta 
\end{aligned}$$

$$\begin{aligned}
\theta +\eta c(t)&= 1+\eta \\
\eta c(t)&= 1+\eta -\theta (t)\\
\theta' (t)&= \frac{1}{\mu }(1+\eta -\theta (t))e^{-\frac{\gamma }{\theta (t)}}+1-\theta (t)
\end{aligned}$$
Let's formulate $\theta (t)=1+u(t)$ where $u(t)$ is the "increase" in temperature.
$u(0)=0$,
$$\begin{aligned}
u'(t)&= \frac{1}{\mu }(\eta -u(t))e^{-\frac{\gamma }{u(t)-1}}-u(t)
\end{aligned}$$

We get an equilibrium point when
$$\begin{aligned}
\frac{1}{\mu }(\eta -u)e^{-\frac{\gamma }{u+1}}&= u\\
\underbrace{(\eta -u)e^{-\frac{\gamma }{u+1}}}_{=W(u)}&= \mu u\\
u \mu &= W(u)
\end{aligned}$$
Vary $\mu$ (which is proportional to the rate $q$) and see what happens.

$$
\begin{aligned}
f(\mu ,u)&= \frac{1}{\mu }(\eta -u)e^{-\frac{\gamma }{\theta }}-u\\
f(\mu ,u)&= \frac{1}{\mu }W(u)-u\\
\frac{\partial f}{\partial u}&= \frac{1}{\mu }W'(u)-1
\end{aligned}
$$
If $\frac{\partial f}{\partial u}<0$ (stable), then
$$W'(u)<\mu ,$$
or when the slope of $W$ is less than the slope of the line. 
