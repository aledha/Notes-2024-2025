![[Pasted image 20240223103120.png]]

![[Pasted image 20240223103130.png]]
jeg har skutt gullfuglen
skyte fuglen
![[Pasted image 20240223103147.png]]

![[Pasted image 20240223103156.png]]
Let's call $z=x+yi$,
$$w(x,y)=\frac{2e^{x+yi}-3}{3e^{x+yi}-2}.$$
This mapping maps every vertical line in the imaginary plane (every fixed $\text{Re}(z)$) to a circle with its center on the real number line. So the image of this mapping is between the two circles, the first corresponding to fixed $\text{Re}(z)=0$ and the second corresponding to $\text{Re}(z)=1$.
We need to find the size and location of these circles. Starting with the image of the vertical line $x=0$, the circle is described by
$$w(0,y)=\frac{2e^{yi}-3}{3e^{yi}-2}\quad\text{for }0 \le y \le 2\pi.$$
Since we already know that this circle is centered on the real number line, we only need to figure out where the circle intersects the real number line, namely when $y=0$ and when $y=\pi$. These two values are
$$\begin{align*}
w(0,0)=\frac{2-3}{3-2}&= -1,\\
w(0,\pi )=\frac{-2-3}{-3-2}&= 1,
\end{align*}$$
meaning that this is a circle centered at $0$ with radius $1$.

The vertical line $x=1$ maps to 
$$w(1,y)=\frac{2ee^{yi}-3}{3ee^{yi}-2} \quad\text{for }0 \le y\le2\pi, $$
which intersects the real number line at 
$$\begin{align*}
w(1,0)&= \frac{2e-3}{3e-2},\\
w(1,\pi )&= \frac{-2e-3}{-3e-2}.
\end{align*}$$
So the center of this circle is
$$\frac{1}{2}(w(1,\pi )+w(0,\pi ))≈0.6133\dots ,$$
while the radius is
$$\frac{1}{2}(w(1,\pi )-w(0,\pi ))≈0.2175\dots$$

