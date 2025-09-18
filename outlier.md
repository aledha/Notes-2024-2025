We see that $\Omega$ is outside the unit circle, below the $y=x$ and to the left of the line $x=1$.

The line $y=x$ corresponds to $\theta=\frac{\pi}{4}$, so $0\leq \theta\leq \frac{\pi}{4}$. 

The unit circle gives the lower limit $r=1$ while the line $x=1$ gives $r\cos \theta=1$, so $1\leq r\leq \frac{1}{\cos \theta}$.

$$
\begin{align}
	\int_{0}^{\pi/4} \int_{1}^{1/\cos \theta} \frac{r\cos \theta}{r^2} r \,drd\theta  & = \int_{0}^{\pi/4} \cos \theta \left( \frac{1}{\cos \theta}-1 \right) \, d\theta \\
 & =[\theta-\sin \theta]_{0}^{\pi/4} \\
 & =\frac{\pi}{4}-\frac{\sqrt{ 2 }}{2} \\
 & \approx 0.08
\end{align}
$$
