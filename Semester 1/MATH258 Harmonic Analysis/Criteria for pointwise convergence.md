We denote the $N$-th symmetric partial sum of the series as
$$S_{N}f(x)=\sum\limits_{k=-N}^{N}\hat f(k)e^{2 \pi i kx}$$
We want to find criteria for when $\lim_\limits{N \to \infty}S_{N}f(x)=f(x)$ for some $x$, i.e., pointwise convergence. The partial sum can be rewritten as
$$\begin{align*}
S_{N}f(x)&= \sum_{k=-N}^{N}\int_{0}^{1}f(t)e^{-2\pi ikt}\text{ d}t \cdot e^{2\pi ikx}\\
&= \int_{0}^{1}f(t)D_{N}(x-t)\text{ d}t\\
&= \int_{0}^{1}f(x-t)D_{N}(t) \text{ d}t
\end{align*}$$
where 
$$D_{N}(t)=\sum_{k=-N}^{N}e^{2 \pi ikt}$$
Summing this gives us
$$D_{N}(t) = \frac{\text{ sin}(\pi (2N+1)t)}{\text{ sin}(\pi t)}$$

There are two criteria we cover

