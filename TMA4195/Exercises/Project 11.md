![[Pasted image 20241115121724.png|800]]
![[Pasted image 20241115121804.png|800]]
![[Pasted image 20241115121817.png|800]]


$$
\begin{aligned}
C_{a}\frac{\partial T}{\partial t}&=D\frac{\partial }{\partial x}\left((1-x^{2})\frac{\partial T(x)}{\partial x}\right)-B_{\text{out}}T(x) -A_{\text{out}}+QS(x)a(x,x_{s})\\
C_{a}\frac{\partial }{\partial t}(T+\delta T)&= D\frac{\partial }{\partial x}\left((1-x^{2})\frac{\partial }{\partial x}(T+\delta T)\right)-B_{\text{out}}(T+\delta T) -A_{\text{out}}+QS(x)a(x,x_{s})\\
C_{a}\frac{\partial T}{\partial t} + C_{a}\frac{\partial \delta T}{\partial t}&= D\frac{\partial }{\partial x}\left((1-x^{2})\frac{\partial T}{\partial x}\right)-B_{\text{out}}T -A_{\text{out}}+QS(x)a(x,x_{s})+ D \frac{\partial }{\partial x}\left((1-x^{2})\frac{\partial \delta T}{\partial x}\right)-B_{\text{out}} \delta T
\end{aligned}
$$
Since $T$ is the equilibrium solution,
$$
\begin{aligned}
C_{a}\frac{\partial \delta T}{\partial t}&= D \frac{\partial }{\partial x}\left((1-x^{2})\frac{\partial \delta T}{\partial x} \right)-B_{\text{out}}\delta T\\
&= D(1-x^{2})\frac{\partial ^{2}\delta T}{\partial x^{2}}-2Dx \frac{\partial \delta T}{\partial x}-B_{\text{out}}\delta T
\end{aligned}
$$


![[Pasted image 20241118082240.png|800]]
$$\begin{aligned}
C_{a}\frac{\partial }{\partial t}(e^{\lambda t}u(x))&=  D(1-x^{2})\frac{\partial ^{2}}{\partial x^{2}}(e^{\lambda t}u(x))-2Dx \frac{\partial }{\partial x}(e^{\lambda t}u(x))-B_{\text{out}}(e^{\lambda t}u(x))\\
\lambda C_{a}e^{\lambda t}u(x)&= D(1-x^{2})e^{\lambda t}u''(x)-2Dxe^{\lambda t}u'(x)-B_{\text{out}}e^{\lambda t}u(x)\\
0&= D(1-x^{2})u''(x)-2Dx u'(x)-(B_{\text{out}}+\lambda C_{a})u(x)
\end{aligned}$$