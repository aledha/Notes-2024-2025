Alexander Hatle
![[Pasted image 20231114141818.png|800]]
$$\begin{cases}
\partial _{t}u +\partial _{x}^{3}u= 0  & \quad\text{on }\mathbb{R}^{1+1} \\
u(x)= g(x) & \quad\text{on }\{t=0 \} \times \mathbb{R}_{x}
\end{cases}$$

Taking the Fourier transform,
$$\begin{align*}
 \partial _{t}\hat u+(i \xi )^{3}\hat u&= 0,
\end{align*}$$
which gives the problem
$$\begin{cases}
\partial _{t}\hat u-i \xi ^{3}\hat u= 0 \\
\hat u(t=0 )=\hat g.
\end{cases}$$
The solution to this ODE is $\hat u=\hat g \cdot e^{i \xi ^{3}t}$.
<div style="page-break-after: always;"></div>

![[Pasted image 20231114141852.png|800]]
By Plancherel, we have that
$$\lVert g \rVert_{L^{2}_{x}}= \frac{1}{\sqrt{2\pi }}\lVert \hat g \rVert_{L^{2}_{\xi }}$$
$$\begin{align*}
\lVert u \rVert_{L^{2}_{x}}&=  \frac{1}{\sqrt{2\pi }} \lVert \hat u \rVert_{L^{2}_{\xi }}\\
&= \frac{1}{\sqrt{2\pi }}\lVert \hat g \cdot e^{i \xi ^{3}t} \rVert_{L^{2}_{\xi }}\\
&=\frac{1}{\sqrt{2\pi }} \left(\int_{-\infty} ^{\infty}\lvert \hat g(\xi ) e^{i \xi ^{3}t} \rvert^{2} \text{ d}\xi \right)^{1/2}
\end{align*}$$
the magnitude of $e^{i \xi ^{3}t}$ is 1, so
$$\begin{align*}
\lVert u \rVert_{L^{2}_{x}}&=  \frac{1}{\sqrt{2\pi }}\left(\int_{-\infty}^{\infty}\lvert \hat g(\xi ) \rvert^{2} \text{ d}\xi  \right)^{2}\\
\lVert u \rVert_{L^{2}_{x}}&= \frac{1}{\sqrt{2\pi }}\lVert \hat g \rVert_{L^{2}_{\xi }}\\
\lVert u \rVert_{L^{2}_{x}}&= \lVert g \rVert_{L^{2}_{x}}
\end{align*}$$

<div style="page-break-after: always;"></div>

![[Pasted image 20231114141901.png|800]]
$$\begin{align*}
\mathcal{F}^{-1} \left[e^{i \xi ^{3}/3} \right]&= \int_{-\infty}^{\infty}e^{i \xi ^{3}/3}e^{i x \xi } \frac{\text{ d}\xi }{2\pi }\\
&= \frac{1}{2\pi }\int_{-\infty}^{\infty}e^{i(\xi ^{3}/3 + x \xi )}\text{ d}\xi \\
	&= \frac{1}{2\pi }\int_{-\infty}^{\infty}\text{cos} \left(\frac{\xi ^{3}}{3} + x \xi \right)+i \text{sin}\left(\frac{\xi ^{3}}{3} + x \xi \right) \text{ d}\xi \\
&= \frac{1}{2\pi }\lim_{R \to \infty}\int_{-R}^{R}\text{cos} \left(\frac{\xi ^{3}}{3} + x \xi \right)+i \text{sin}\left(\frac{\xi ^{3}}{3} + x \xi \right) \text{ d}\xi 
\end{align*}$$
The term $\frac{\xi ^{3}}{3}+ x \xi$ is odd with respect to $\xi$, making the cosine term even and the sin term odd. Since we are integrating over a symmetric interval,
$$\mathcal{F}^{-1}\left[e^{i \xi /3} \right]= \frac{1}{\pi }\lim_{R \to \infty}\int_{0}^{R}\text{cos}\left(\frac{\xi^{3} }{3}+x \xi  \right)\text{ d}\xi $$
<div style="page-break-after: always;"></div>

![[Pasted image 20231114141910.png|800]]
The first term is
$$\begin{align*}
\frac{\text{d}^{2}}{\text{d}x^{2}}Ai(x)&=  \frac{1}{\pi }\lim_{R \to \infty}\int^{R}_{0}\frac{\text{d}}{\text{d}x}\left(\xi \text{sin}\left(\frac{\xi ^{3}}{3} +x \xi \right) \right)\text{ d}\xi \\
	&= -\frac{1}{\pi }\lim_{R \to \infty}\int_{0}^{R}\xi ^{2}\text{cos}\left(\frac{\xi ^{3}}{3} +x \xi \right)\text{ d}\xi 
\end{align*}$$
While the second term is
$$xAi(x)=\frac{1}{\pi }\lim_{R \to \infty}\int_{0}^{R}x \text{cos}\left(\frac{\xi ^{3}}{3} +x \xi \right)\text{ d}\xi $$

$$-\frac{\text{d}^{2}}{\text{d}x^{2}}Ai(x)+xAi(x)=\frac{1}{\pi }\lim_{R \to \infty}\int_{0}^{R}(\xi ^{2}+x)\text{cos}\left(\frac{\xi ^{3}}{3} +x \xi \right)\text{ d}\xi $$
And we will show in the next problem that this equals
$$= \frac{1}{\pi }\lim_{R \to \infty}\int_{0}^{R}\partial _{\xi }\text{sin}\left(\frac{\xi ^{3}}{3} +x \xi \right) \text{ d}\xi =\frac{1}{\pi }\lim_{R \to \infty}\text{sin}\left(\frac{R^{3}}{3} +x R \right)$$
I couldn't figure this out
<div style="page-break-after: always;"></div>

![[Pasted image 20231114141928.png|800]]


$$\partial _{\xi }\text{sin}\left(\frac{\xi ^{3}}{3} +x \xi \right)=(\xi ^{2}+x)\cdot \text{cos}\left(\frac{\xi ^{3}}{3} +x \xi \right)$$
$$\begin{align*}
\int_{0}^{n}\text{cos}\left(\frac{\xi ^{3}}{3} +x \xi \right)\text{ d}\xi &= \int_{0}^{n}\frac{1}{\xi ^{2}+x} \partial _{\xi }\text{sin}\left(\frac{\xi ^{3}}{3} +x \xi \right) \text{ d}\xi \\
&= \left[\frac{1}{\xi ^{2}+x}\text{sin}\left(\frac{\xi ^{3}}{3} +x \xi \right) \right]_{0}^{n}-\int_{0}^{n} \frac{-2\xi }{(\xi ^{2}+x)^{2}}\text{sin}\left(\frac{\xi ^{3}}{3} +x \xi \right)\text{ d}\xi \\
	&= \frac{1}{n^{2}+x}\text{sin}\left(\frac{n ^{3}}{3} +x n \right)+2 \int_{0}^{n}\frac{\xi }{(\xi ^{2}+x)^{2}}\text{sin}\left(\frac{\xi ^{3}}{3} +x \xi \right)\text{ d}\xi
\end{align*}$$
Now, taking $n\to \infty$, the first term goes to zero. 
$$Ai(x)=\frac{2}{\pi }\int_{0}^{\infty} \frac{\xi }{(\xi ^{2}+x)^{2}}\text{sin}\left(\frac{\xi ^{3}}{3} +x \xi \right)\text{ d}\xi$$
The integrand in the second term goes to zero as $\xi\to \infty$, and for $x=0$ we have $Ai(0)= \frac{2}{\pi }\int_{0}^{\infty}\xi ^{-3} \text{sin}(\xi ^{3}/3)\text{ d}\xi<\infty$. Therefore, $Ai(x)$ is bounded. 