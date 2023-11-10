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
Since 
$$\partial _{x}\text{tan}^{-1}(x)=\frac{1}{1+x^{2}}$$

![[Pasted image 20231107160827.png|800]]

![[Pasted image 20231107160842.png|800]]

![[Pasted image 20231107160854.png|800]]