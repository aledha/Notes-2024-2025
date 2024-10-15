![[Pasted image 20241015105910.png|800]]
$$\begin{aligned}
\ddot x_{0}+ \epsilon \ddot x_{1}+\epsilon ^{2}\ddot x_{2}+2 \epsilon (\dot x_{0}+\epsilon \dot x_{1})+\epsilon (x_{0}+\epsilon x_{1})&= 0\\
\ddot x_{0}+\epsilon (\ddot x_{1}+\dot x_{0}+x_{0})+ \epsilon ^{2}(\ddot x_{2}+\dot x_{1}+x_{1})&= 0
\end{aligned}$$
This gives a system of equations
$$\begin{aligned}
\ddot x_{0}&= 0\\
\ddot x_{1}+\dot x_{0}+x_{0}&= 0\\
\ddot x_{2}+\dot x_{1}+x_{1}&= 0
\end{aligned}$$
With the initial conditions
$$\begin{aligned}
x_{0}(0)+\epsilon x_{1}(0)+\epsilon ^{2}x_{2}(0)&= 0\\
\dot x_{0}(0)+\epsilon \dot x_{1}(0)+\epsilon ^{2}\dot x_{2}(0)&= 1-\epsilon 
\end{aligned}$$
Solving,
$$\begin{aligned}
x_{0}(t)&= At+B\\
x_{0}(0)&= 0\\
x_{0}(t)&= At\\
\dot x_{0}(0)&= 1\\
x_{0}(t)&= t
\end{aligned}$$
$x_{1}$ can be found as
$$\begin{aligned}
\ddot x_{1}+\dot x_{0}+x_{0}&= 0\\
\ddot x_{1}&= -1-t\\
\dot x_{1}&= -t-\frac{1}{2}t^{2}+A\\
x_{1}(t)&= -\frac{1}{2}t^{2}-\frac{1}{6}t^{3}+At+B\\
x_{1}(0)&= B=0\\
\dot x_{1}(0)&= A=-1\\
x_{1}(t)&= -\frac{1}{6}t^{3}-\frac{1}{2}t^{2}-t
\end{aligned}$$

![[Pasted image 20241015111737.png|800]]
$y=y_{0}+\epsilon y_{1}$:
$$\begin{aligned}
\dot y_{0}+\epsilon \dot y_{1}-y_{0}-\epsilon y_{1}-\epsilon (y_{0}+\epsilon y_{1})^{2}e^{-t}&= 0\\
(\dot y_{0}-y_{0})+\epsilon (\dot y_{1}-y_{1}-y_{0}^{2}e^{-t})&= 0
\end{aligned}$$
System:
$$\begin{aligned}
\dot y_{0}-y_{0}&= 0\\
\dot y_{1}-y_{1}-y_{0}^{2}e^{-t}&= 0
\end{aligned}$$
$$\begin{aligned}
\dot y_{0}&= y_{0}\\
\dot y_{1}&= y_{1}+y_{0}^{2}e^{-t}
\end{aligned}$$
with initial condition
$$y(0)=y_{0}(0)+\epsilon y_{1}(0)=1$$
$$\begin{aligned}
y_{0}(t)&= Ae^{t}\\
y_{0}(0)&= A=1\\
y_{0}(t)&= e^{t}
\end{aligned}$$

$$\begin{aligned}
\dot y_{1}&= y_{1}+e^{2t}e^{-t}\\
\dot y_{1}-y_{1}&= e^{t}
\end{aligned}$$
Integrating factor method:
$$\begin{aligned}
\exp\left(\int -1 \text{ d}t\right)&= \exp(-t)
\end{aligned}$$
$$\begin{aligned}
\dot y_{1}e^{-t}-y_{1}e^{-t}&= e^{t}e^{-t}\\
(y_{1}e^{-t})'&= 1\\
y_{1}e^{-t}&= t +C\\
y_{1}(t)&= te^{t}+Ce^{t}\\
y_{1}(0)&= C=0\\
y_{1}(t)&= te^{t}
\end{aligned}$$

![[Pasted image 20241015114250.png|800]]

$$\begin{aligned}
\ddot v(t)&= -\frac{1}{\epsilon }\sin (\epsilon v)\\
v(0)&= 1\\
\dot v(0)&= 0
\end{aligned}$$
Setting $v(t)=v_{0}(\omega t)+\epsilon v_{1}(\omega t)+\epsilon ^{2}v_{2}(\omega t)+\dots$:
$$\begin{aligned}
\omega ^{2}(\ddot v_{0}+\epsilon \ddot v_{1}+\epsilon ^{2}\ddot v_{2}+\dots)&= -\frac{1}{\epsilon }\sin (\epsilon v_{0}+\epsilon ^{2}v_{1}+\epsilon ^{3}v_{2}+\dots)\\
(1+\epsilon \omega _{1}+\epsilon ^{2}\omega _{2}+\dots)^{2}(\ddot v_{0}+\epsilon \ddot v_{1}+\epsilon ^{2}\ddot v_{2}+\dots)&= -\frac{1}{\epsilon }\sin (\epsilon v_{0}+\epsilon ^{2}v_{1}+\epsilon ^{3}v_{2}+\dots)
\end{aligned}$$
with the initial condition 
Taylor expansion for $\sin x$:
$$\begin{aligned}
\sin x&= \sum_{n=0}^{\infty}\frac{f^{(n)}(0)}{n!}\cdot x^{n}\\
&= \sum_{n=1}^{\infty}\frac{(-1)^{n}}{2n!}x^{2n-1}\\
&= x-\frac{1}{6}x^{3}+\frac{1}{120}x^{5}+\dots 
\end{aligned}$$
then,
$$\begin{aligned}
-\frac{1}{\epsilon }\sin (\epsilon v_{0}+\epsilon ^{2}v_{1}+\epsilon ^{3}v_{2})&= -\frac{1}{\epsilon }\left[\epsilon v_{0}+\epsilon ^{2}v_{1}+\epsilon ^{3}v_{2} -\frac{1}{6}\epsilon ^{3}(v_{0}+\epsilon v_{1}+\epsilon ^{2}v_{2})^{3}+\dots \right]\\
&= -v_{0}-\epsilon v_{1}+ \epsilon ^{2}v_{2}+\frac{1}{6}\epsilon ^{2}\left(v_{0}+\epsilon v_{1}+\epsilon ^{2}v_{2} \right)^{3}+\dots 
\end{aligned}$$
then
$$\begin{aligned}
(1+\epsilon \omega _{1}+\epsilon ^{2}\omega _{2}+\dots)^{2}(\ddot v_{0}+\epsilon \ddot v_{1}+\epsilon ^{2}\ddot v_{2}+\dots )&= -v_{0}-\epsilon v_{1}- \epsilon ^{2}v_{2}+\frac{1}{6}\epsilon ^{2}\left(v_{0}+\epsilon v_{1}+\epsilon ^{2}v_{2} \right)^{3}+\dots \\
(1+\epsilon \omega _{1}+\epsilon ^{2}\omega _{2}+\dots)(1+\epsilon \omega _{1}+\epsilon ^{2}\omega _{2}+\dots)&=1+2\epsilon  \omega _{1}+\epsilon ^{2}(2\omega _{1}^{2}+2\omega _{2})+\epsilon ^{3}(2\omega _{3}^{2}+2\omega _{1}\omega _{2})+\dots \\
(1+2\epsilon  \omega _{1}+\epsilon ^{2}(2\omega _{1}^{2}+2\omega _{2})+\epsilon ^{3}(2\omega _{3}^{2}+2\omega _{1}\omega _{2})+\dots)(\ddot v_{0}+\epsilon \ddot v_{1}+\epsilon ^{2}\ddot v_{2}+\dots )&= -v_{0}-\epsilon v_{1}- \epsilon ^{2}v_{2}+\frac{1}{6}\epsilon ^{2}\left(v_{0}+\epsilon v_{1}+\epsilon ^{2}v_{2} \right)^{3}+\dots \\
\ddot v_{0}+\epsilon (\ddot v_{1}+2\omega _{1}\ddot v_{0})+\epsilon ^{2}(\omega _{1}^{2}\ddot v_{0}+2 \omega _{2}\ddot v_{0}+\ddot v_{2}+2 \omega _{1}\ddot v_{1})+\dots &= -v_{0}-\epsilon v_{1}+\epsilon ^{2}\left(-v_{2}+\frac{1}{6}v_{0}\right)
\end{aligned}$$
System:
$$\begin{aligned}
\ddot v_{0}&= -v_{0}\\
\ddot v_{1}+2\omega _{1}\ddot v_{0}&= -v_{1}\\
\omega _{1}^{2}\ddot v_{0}+2 \omega _{2}\ddot v_{0}+\ddot v_{2}+2 \omega _{1}\ddot v_{1}&= -v_{2}+\frac{1}{6}v_{0}
\end{aligned}$$
Solving the first:
$$\begin{aligned}
\ddot v_{0}&= -v_{0}\\
v_{0}(t)&= A \sin t+B \cos t\\
v_{0}(0)&= B=1\\
\dot v_{0}(0)&= A \cos 0-\sin t=0\\
v_{0}(t)&= \cos t
\end{aligned}$$
Substituting into the second:
$$\begin{aligned}
\ddot v_{1}-2 \omega _{1}\cos t&= -v_{1}\\
\ddot v_{1}+v_{1}&= 2 \omega _{1}\cos t\\
 
\end{aligned}$$