![[Pasted image 20241028134134.png|900]]
The total amount of heat energy in a domain $\Omega$ is
$$\iiint_{\Omega }c\rho T \text{ d}V.$$
By Fourier's law, the heat flux contribution per time is 
$$\iint_{\partial \Omega } -\mathbf n \cdot k \nabla T \text{ d}S,$$
where $\mathbf n$ is the normal vector pointing out of the domain.

We also have the energy per time contributed by the heat source
$$\iiint_{\Omega }q \text{ d}V.$$

The total amount of energy must be conserved:
$$\frac{\partial }{\partial t}\iiint_{\Omega }c\rho T \text{ d}V=\iint_{\partial \Omega } -\mathbf n \cdot k \nabla T \text{ d}S+\iiint_{\Omega }q \text{ d}V,$$
where we can apply the divergence theorem to get
$$\frac{\partial }{\partial t}\iiint_{\Omega }c\rho T \text{ d}V=\iiint_{\Omega } \nabla  \cdot (k \nabla T )\text{ d}V+\iiint_{\Omega }q \text{ d}V.$$
Since $\Omega$ is arbitrary, this can be written equivalently in differential form:
$$\frac{\partial }{\partial t}(c \rho T)= \nabla \cdot (k \nabla T)+q.$$

![[Pasted image 20241030122021.png]]
![[Pasted image 20241030122031.png]]

$$\begin{aligned}
-D\frac{\partial }{\partial x}\left((1-x^{2})\frac{\partial T(x)}{\partial x}\right)&= -I(x)+QS(x)a(x,x_{s})\\
-D\frac{\partial }{\partial x}\left((1-x^{2})\frac{\partial T(x)}{\partial x}\right)&= -B_{\text{out}}T(x)-A_{\text{out}}+QS(x)a(x,x_{s})\\
-D\frac{\partial }{\partial x}\left((1-x^{2})\frac{\partial T(x)}{\partial x}\right)+B_{\text{out}}T(x)&= -A_{\text{out}}+QS(x)a(x,x_{s})\\
\end{aligned}$$
We can express $T$ as a particular solution with two homogenous solutions:
$$T(x)=T_{p}(x)+C_{1}y_{1}(x)+C_{2}y_{2}(x),$$
such that
$$\begin{aligned}
-D\frac{\partial }{\partial x}\left((1-x^{2})\frac{\partial T_{p}(x)}{\partial x}\right)+B_{\text{out}}T_{p}(x)&= -A_{\text{out}}+QS(x)a(x,x_{s})\\
-D\frac{\partial }{\partial x}\left((1-x^{2})\frac{\partial y_{i}(x)}{\partial x}\right)+B_{\text{out}}y_{i}(x)&= 0\quad\text{for }i=1,2.
\end{aligned}$$

https://www.iitg.ac.in/shyamashree/Lecture16-2016.pdf

### inserting sum into hom. eq.
Let $y(x)=\sum_{n=0}^{\infty}\alpha _{n}x^{n}$. Then, the homogenous equation becomes
$$\begin{aligned}
-D(1-x^{2})y''(x)+2Dxy'(x)+B_{\text{out}}y(x)&= 0\\
(1-x^{2})y''(x)-2xy'(x)-\frac{B_{\text{out}}}{D}y(x)&= 0\\
(1-x^{2})\frac{\partial ^{2}}{\partial x^{2}}\left(\sum_{n=0}^{\infty}\alpha _{n}x^{n} \right)-2x \frac{\partial }{\partial x}\left(\sum_{n=0}^{\infty}\alpha _{n}x^{n} \right)-\frac{B_{\text{out}}}{D}\sum_{n=0}^{\infty}\alpha _{n}x^{n}&= 0\\
(1-x^{2})\sum_{n=2}^{\infty}\alpha _{n}n(n-1)x^{n-2}-2x \sum_{n=1}^{\infty}\alpha _{n}nx^{n-1}-\frac{B_{\text{out}}}{D}\sum_{n=0}^{\infty}\alpha _{n}x^{n}&= 0
\end{aligned}$$
The first term is
$$\begin{aligned}
(1-x^{2})\sum_{n=2}^{\infty}\alpha _{n}n(n-1)x^{n-2}&= \sum_{n=2}^{\infty}\alpha _{n}n(n-1)x^{n-2}-\sum_{n=2}^{\infty}\alpha _{n}n(n-1)x^{n}\\
&= \sum_{n=0}^{\infty}\alpha _{n+2}(n+2)(n+1)x^{n}-\sum_{n=0}^{\infty}\alpha _{n}n(n-1)x^{n}\\
&= \sum_{n=0}^{\infty}\left(\alpha _{n+2}(n+2)(n+1)-\alpha _{n}n(n-1) \right)x^{n},
\end{aligned}$$
where in the second step we used that $n(n-1)=0$ when $n=0$ or $n=1$. The second term is
$$\begin{aligned}
	-2x \sum_{n=1}^{\infty}\alpha _{n}nx^{n-1}&= -2 \sum_{n=1}^{\infty}\alpha _{n}nx^{n}\\
&= -2 \sum_{n=0}^{\infty}\alpha _{n}nx^{n},
\end{aligned}$$
so we get
$$\begin{aligned}
 \sum_{n=0}^{\infty}\left(\alpha _{n+2}(n+2)(n+1)-\alpha _{n}n(n-1) \right)x^{n}-2 \sum_{n=0}^{\infty}\alpha _{n}nx^{n}-\frac{B_{\text{out}}}{D}\sum_{n=0}^{\infty}\alpha _{n}x^{n}&= 0\\
\sum_{n=0}^{\infty}\left[\alpha _{n+2}(n+2)(n+1)- \alpha _{n}n(n-1)-2 \alpha _{n}n-\frac{B_{\text{out}}}{D}\alpha _{n} \right]x^{n}&= 0
\end{aligned}$$
(need to explain why)
$$\begin{aligned}
\alpha _{n+2}(n+2)(n+1)- \alpha _{n}n(n-1)-2 \alpha _{n}n-\frac{B_{\text{out}}}{D}\alpha _{n} &= 0\\
\alpha _{n+2}(n+2)(n+1)-\left[n(n-1)+2n+ \frac{B_{\text{out}}}{D} \right]\alpha _{n}&= 0\\
\alpha _{n+2}&= \frac{n(n-1)+2n+ \frac{B_{\text{out}}}{D} }{(n+2)(n+1)}\alpha _{n}\\
\alpha _{n+2}&= \frac{n(n+1)+ \frac{B_{\text{out}}}{D}}{(n+2)(n+1)}\alpha _{n}\\
\alpha _{n+2}&= f(n) \alpha _{n}
\end{aligned}$$

$$\begin{aligned}
\alpha _{2}&= f(0)\alpha _{0}\\
\alpha _{4}&= f(2)f(0)\alpha _{0}\\
\vdots \\
\alpha _{2n}&= \alpha _{0}\prod_{k=0 }^{n} f(2k)
\end{aligned}$$
$$\begin{aligned}
\alpha _{3}&= f(1)\alpha _{1}\\
\alpha _{5}&= f(3)f(1)\alpha _{1}\\
\vdots \\
\alpha _{2n+1}&= \alpha _{1}\prod_{k=0}^{n}f(2k+1)
\end{aligned}$$

$$\begin{aligned}
y(x)&= \sum_{n=0}^{\infty}\alpha _{n}x^{n}\\
&= \sum_{n=0}^{\infty}\alpha _{2n}x^{2n}+\sum_{n=0}^{\infty}\alpha _{2n+1}x^{2n+1}\\
&= \sum_{n=0}^{\infty}\left(\prod_{k=0}^{n}f(2k) \right)\alpha _{0}x^{2n}+\sum_{n=0}^{\infty}\left(\prod_{k=0}^{n}f(2k+1) \right)\alpha _{1}x^{2n+1}\\
&=: y_{1}(x)+y_{2}(x) 
\end{aligned}$$



$$\begin{aligned}
w(u)&= a_{0}\left(1+ \sum_{n=1}^{\infty}\left(\prod_{k=1}^{n}\frac{k(k-1)+B}{2k^{2}} \right)u^{n} \right)\\
&= a_{0}+a_{0}\frac{B}{2}u+a_{0}\frac{B}{2}\cdot \frac{B+2}{8}u^{2}+\dots \\
w'(u)&= a_{0}\frac{B}{2}+\dots \\
w'(0)&= a_{0}\frac{B}{2}
\end{aligned}$$

$$T(x)=\begin{cases}
T_{p}(x)+C_{1}y_{1}(x)+C_{2}y_{2}(x) & \quad\text{for }x<x_{s} \\
T_{p}(x)+w(1-x) & \quad\text{for }x>x_{s}
\end{cases}$$

### Inhomo
$$-D\frac{\partial }{\partial x}\left((1-x^{2})\frac{\partial T_{p}(x)}{\partial x}\right)+B_{\text{out}}T_{p}(x)= -A_{\text{out}}+QS(x)a(x,x_{s})$$
Let $T_{p}=\sum_{n=0}^{\infty}T_{n}P_{n}(x)$, then
$$\begin{aligned}
\sum_{n=0}^{\infty}-D \frac{\partial }{\partial x}\left((1-x^{2})\frac{\partial T_{n}P_{n}(x)}{\partial x}\right)+B_{\text{out}}T_{n}P_{n}(x)&=  -A_{\text{out}}+QS(x)a(x,x_{s})
\end{aligned}$$
![[Pasted image 20241030122047.png]]
Using $S(x)=1+S_{2} \frac{1}{2}(3x^{2}-1)=1+S_{2}P_{2}(x)$  
$$\begin{aligned}
\sum_{n=0}^{\infty}-D \frac{\partial }{\partial x}\left((1-x^{2})\frac{\partial T_{n}P_{n}(x)}{\partial x}\right)+B_{\text{out}}T_{n}P_{n}(x)&=  -A_{\text{out}}+QS(x)a(x,x_{s})\\
\sum_{n=0}^{\infty}Dn(n+1)T_{n}P_{n}(x)+B_{\text{out}}T_{n}P_{n}(x)&= -A_{\text{out}}+Q(1+S_{2}P_{2}(x)) a(x,x_{s})\\
\sum_{n=0}^{\infty}(Dn(n+1)T_{n}+B_{\text{out}}T_{n})P_{n}(x)&= -A_{\text{out}}+Q a(x,x_{s})+QS_{2}a(x,x_{s})P_{2}(x)\\
\sum_{n=0}^{\infty}(Dn(n+1)T_{n}+B_{\text{out}}T_{n})P_{n}(x)&= (-A_{\text{out}}+Q a(x,x_{s}))P_{0}(x)+QS_{2}a(x,x_{s})P_{2}(x)
\end{aligned}$$
Then, due to the orthogonality of Legendre polynomials,
$$\begin{aligned}
(D \cdot 0(0+1)T_{0}+B_{\text{out}}T_{0})P_{0}(x)&= (-A_{\text{out}}+Qa(x,x_{s}))P_{0}(x),\\
(D \cdot 2(2+1)T_{2}+B_{\text{out}}T_{2})P_{2}(x)&= QS_{2}a(x,x_{s})P_{2}(x),\\
\end{aligned}$$
$$T_{p}=T_{0}P_{0}(x)+T_{2}P_{2}(x)$$


Homo for $x>x_s$:
$$a_{n+1} = \frac{n(n+1)+B}{2(n+1)^2}a_n$$

$$\begin{aligned}
T_3&= \sum_{n=0}^{\infty}a_nu^n\\
&= \sum_{n=0}^{\infty}u^n\prod_{j=0}^{n}\frac{(j-1)j+B}{2j^2}a_0\\
T_3 (x)&= a_0\sum_{n=0}^{\infty}(1-x)^n\prod_{j=0}^{n}\frac{(j-1)j+B}{2j^2}\\
T_3'(x)&= -a_0\sum_{n=0}^{\infty}nu^{n-1}\prod_{j=0}^{n}\frac{(j-1)j+B}{2j^2}
\end{aligned}$$



![[Pasted image 20241110094124.png|900]]


![[Pasted image 20241105142315.png]]
