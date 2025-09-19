$\Omega$ is the area inside the circle $x^2+y^2=4$ but outside the unit square $[0,1]\times[0,1]$. Therefore, we divide the integral into
$$
\int \int_{\Omega}x+y^2 \,dA = \int \int_{C}x+y^2 \, dA -  \int \int_{S}x+y^2 \, dA,
$$
where $C$ denotes the circle and $S$ denotes the square.

$$
\begin{align}
	\int \int_{C}x+y^2 \, dA & =\int_{0}^{\pi/2}\int_{0}^2 (r\cos \theta+r^2\sin^2 \theta)r \,drd\theta, \\
 & =\int_{0}^{\pi/2} \left( \frac{2^3}{3}\cos \theta + \frac{2^4}{4}\sin^2 \theta \right)\,d\theta \\
 & =\int_{0}^{\pi/2}\left(  \frac{8}{3} \cos \theta + 4 \cdot \frac{1}{2}(1-\cos (2\theta))\right) \,d\theta \\
 & =\left[ \frac{8}{3}\sin \theta  +2\theta - \sin(2\theta)\right]_{0}^{\pi/2} \\
 & =\frac{8}{3}+\pi
\end{align}
$$

$$
\begin{align}
	\int \int_{S}x+y^2 \, dA & =\int_{0}^1 \int_{0}^1 (x+y^2) \,dxdy \\
 & =\int_{0}^1 \left( \frac{1}{2}+y^2 \right) \,dy \\
 & =\frac{1}{2}+\frac{1}{3} \\
 & =\frac{5}{6}
\end{align}
$$


$$
\begin{align}
	\int \int_{\Omega}x+y^2 \,dA  & =\frac{8}{3}+\pi - \frac{5}{6} \\
 & =\frac{11}{6}+\pi  \\
 & \approx 4.97
\end{align}
$$
