$$
\int_{k}^{k+1}\int_{-(x-k)}^{x-k}e^{y-x}dydx
$$

$$
\begin{align}
	\int_{0}^{1}\int_{-u}^{u}e^{y-u-k}dydu  & =\int_{0}^1 [e^{ y-u-k }]_{-u}^u du \\
 & =\int_{0}^1(e^{-k}-e^{-2u-k})du \\
 & =e^{-k}\left[ u+ \frac{1}{2}e^{ -2u } \right]_{0}^1 \\
 & =\frac{1}{2}e^{ -k }(1+e^{ -2 }).
\end{align}
$$

$$
\begin{align}
	\sum_{k=0}^\infty\frac{1}{2}e^{ -k }(1+e^{ -2 }) & = \frac{1+e^{ -2 }}{2}\sum_{k=0}^\infty e^{ -k } \\
 & =\frac{1+e^{ -2 }}{2(1-e^{ -1 })} \\
 & \approx 0.898
\end{align}
$$
