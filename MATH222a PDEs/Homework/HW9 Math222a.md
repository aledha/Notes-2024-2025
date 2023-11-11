![[Pasted image 20231107160740.png|800]]
$$\begin{align*}
\mathcal{F}[x]&= \int_{-\infty}^{\infty}x \cdot e^{-i \xi  x}\text{ d}x\\\\
\end{align*}$$
We see that if $\xi =0$, then $\mathcal{F}[x]=0$ since $x$ is an odd function. For $\xi ≠0$, 
$$\begin{align*}
 i \xi \mathcal{F}[x]& = \mathcal{F}[\partial_{x}x]\\
\mathcal{F}[x]&= \frac{1}{i \xi } \mathcal{F}[1]\\
	&= \frac{2 \pi }{i \xi }\delta (\xi )
\end{align*}$$

![[Pasted image 20231107160754.png|800]]
$$\begin{align*}
\mathcal{F}\left[\text{sin}^{2}x \right]&=  \frac{1}{2\pi }\mathcal{F}\left[\text{sin}x \right]*\mathcal{F}\left[\text{sin}x \right]\\
	&= \frac{1}{2\pi }\int_{-\infty}^{\infty}\text{sin}x e^{-i  \xi x} \text{ d}x
\end{align*}$$
![[Pasted image 20231107160802.png|800]]
$$\begin{align*}
\mathcal{F}\left[e^{-\lvert x \rvert} \right]&= \int_{-\infty}^{\infty}e^{-\lvert x \rvert}e^{-i \xi x}\text{ d}x\\
&= \int_{0}^{\infty}e^{-(1+i \xi)x }\text{ d}x+\int_{-\infty }^{0}e^{(1- i \xi )x}
\text{ d}x \\
&= \left[- \frac{1}{1+i \xi } e^{-(1+i \xi)x }\right]_{0}^{\infty}+\left[ \frac{1}{1-i \xi }e^{-(-1+i \xi)x } \right]_{-\infty  }^{0}\\
&= \frac{1}{1+ i \xi }+\frac{1}{1- i \xi }\\
&= \frac{1-i \xi +1+i \xi }{1-i^{2}\xi ^{2}}\\
&= \frac{2}{1+\xi ^{2}}
\end{align*}$$
![[Pasted image 20231107160812.png|800]]
We have already shown that $\mathcal{F}\left[e^{-\lvert x \rvert} \right]=\frac{2}{1 + \xi ^{2}}$
By the inversion formula, we have that
$$\begin{align*}
e^{-\lvert x \rvert}&= \int_{-\infty}^{\infty}\frac{2}{1+\xi ^{2}}e^{i \xi x}\frac{\text{ d}\xi }{2\pi }\\
g(x):=e^{-\lvert x \rvert}&= \frac{1}{\pi } \int_{-\infty}^{\infty}\frac{1}{1+\xi  ^{2}}e^{i \xi x} \text{ d}\xi 
\end{align*}$$
Notice that 
$$\mathcal{F}\left[\frac{1}{1+x^{2}} \right]=\int_{-\infty}^{\infty}\frac{1}{1+x^{2}}e^{-i \xi x}\text{ d}x=\pi g(-x)$$
Then,
$$\mathcal{F}\left[\frac{1}{1+x^{2}} \right]=\pi e^{-\lvert x \rvert}$$

![[Pasted image 20231107160827.png|800]]
If we substitute $z=s \lambda ^{2}$, then $\text{ d}z=\lambda ^{2}\text{ d}s$ and
$$\begin{align*}
\int_{0}^{\infty}s^{\alpha -1}e^{-s \lambda ^{2}}\text{ d}s &=\int_{0}^{\infty}\left(\frac{z}{\lambda^{2} } \right)^{\alpha -1}e^{-z} \frac{\text{ d}z}{\lambda ^{2}}\\
&= \frac{1}{\lambda ^{2(\alpha -1)+2}}\int_{0}^{\infty}z^{\alpha -1}e^{-z}\text{ d}z\\
&= \lambda^{-2\alpha }\Gamma (\alpha ) 
\end{align*}$$
![[Pasted image 20231107160842.png|800]]
$$\mathcal{F}\left[\lvert x \rvert^{-\alpha } \right]=\int_{\mathbb{R}^{d}}\lvert x \rvert^{-\alpha }e^{-i \xi \cdot x}\text{ d}x$$

$$\mathcal{F}\left[e^{-s \lvert x \rvert^{2}} \right]= \left(\frac{\pi }{s} \right)^{d/2}e^{-\frac{\lvert \xi  \rvert^{2}}{4s}}$$
Notice that 



$$\begin{align*}
-\Delta  (e^{-s\lvert x \rvert^{2}})&= \sum_{k=1}^{d}\partial_{x^{j}}^{2}e^{-s \lvert x \rvert^{2}} \\
	&= \sum_{k=1}^{d} \partial _{x^{j}}(-s \cdot 2x^{j}e^{-s \lvert x \rvert^{2}})\\
	&= 2s\sum_{k=1}^{d}(-e^{-s \lvert x \rvert}+ 2(x^{j})^{2}e^{-s \lvert x \rvert})\\
&= 2s( -d(d-1)+2\lvert x \rvert^{2})e^{-s \lvert x \rvert}
\end{align*}$$
![[Pasted image 20231107160854.png|800]]
$$u(\lambda x)=\lambda ^{a}u(x)$$
Want to show that 
$$\hat u(\lambda \xi )=\lambda ^{-a-d}\hat u (\xi )$$