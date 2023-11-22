![[Pasted image 20231107160740.png|800]]
$$\begin{align*}
\mathcal{F}[x]&= \int_{-\infty}^{\infty}x \cdot e^{-i \xi  x}\text{ d}x\\\\
\end{align*}$$
We see that if $\xi =0$, then $\mathcal{F}[x]=0$ since $x$ is an odd function. For $\xi ≠0$, 
$$\begin{align*}
 i \xi \mathcal{F}[x]& = \mathcal{F}[\partial_{x}x]\\
\mathcal{F}[x]&= \frac{1}{i \xi } \mathcal{F}[1]\\
	&= \frac{2 \pi }{i \xi }\delta (\xi ).
\end{align*}$$

![[Pasted image 20231107160754.png|800]]
$$\begin{align*}
\mathcal{F}\left[\text{sin}^{2}x \right]&=  \mathcal{F}\left[ \frac{1 - \cos(2x)}{2}  \right]\\
&= \pi \delta (\xi )- \int_{-\infty}^{\infty}\frac{\cos(2x)}{2} e^{-i \xi x}\text{ d}x\\
&= \pi \delta (\xi )-\int_{\infty}^{\infty}\frac{e^{2ix}-e^{-2ix}}{2}e^{-i \xi x}\text{ d}x\\
&= \pi \delta (\xi )-\frac{1}{2}\int_{-\infty}^{\infty}e^{-(-2+\xi )ix}-e^{-(2+\xi )ix}\text{ d}x\\
&= \pi \delta (\xi )- \frac{1}{2}\left(2\pi \delta (\xi -2) -2\pi \delta (\xi +2\right)\\
&= \pi \left(\delta (\xi )+\delta (\xi +2)-\delta (\xi -2) \right)
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
<div style="page-break-after: always;"></div>

![[Pasted image 20231107160827.png|800]]
If we substitute $z=s \lambda ^{2}$, then $\text{ d}z=\lambda ^{2}\text{ d}s$ and
$$\begin{align*}
\int_{0}^{\infty}s^{\alpha -1}e^{-s \lambda ^{2}}\text{ d}s &=\int_{0}^{\infty}\left(\frac{z}{\lambda^{2} } \right)^{\alpha -1}e^{-z} \frac{\text{ d}z}{\lambda ^{2}}\\
&= \frac{1}{\lambda ^{2(\alpha -1)+2}}\int_{0}^{\infty}z^{\alpha -1}e^{-z}\text{ d}z\\
&= \lambda^{-2\alpha }\Gamma (\alpha ) 
\end{align*}$$
<div style="page-break-after: always;"></div>

![[Pasted image 20231107160854.png|800]]
$$u(\lambda x)=\lambda ^{a}u(x)$$
Want to show that 
$$\hat u(\lambda \xi )=\lambda ^{-a-d}\hat u (\xi )$$

We can set $z^{j}= \lambda x^{j}$ for each $j$, and then the Jacobian is
$$\left\lvert \frac{\partial (z_{1},\dots z_{d})}{\partial (x_{1},\dots ,x_{d})} \right\rvert=\lambda ^{d},$$
such that $\text{ d}z=\text{ d}z_{1}\cdots  \text{ d}z_{d}=\lambda^{d}\text{ d}x_{1}\cdots \text{ d}x_{d}=\lambda \text{ d}x$. Performing the change of variables,
$$\begin{align*}
\mathcal{F}\left[u \right](\xi )&= \int_{\mathbb{R}^{d}}u(x)e^{-i \xi \cdot x}\text{ d}x\\
	\mathcal{F}\left[u \right](\lambda \xi )&= \int_{\mathbb{R}^{d} }u(x)e^{-i \lambda \xi \cdot x} \text{ d}x\\
&= \int_{\mathbb{R}^{d}}u \left(\frac{z}{\lambda } \right)e^{-i \xi \cdot z} \frac{\text{d}z}{\lambda ^{d}}\\
&= \int_{\mathbb{R}^{d}}\lambda ^{-a}u(z)e^{-i \xi \cdot z}\frac{\text{d}z}{\lambda ^{d}}\\
	&= \lambda ^{-a-d}\cdot \mathcal{F}\left[u \right](\xi ),
\end{align*}$$
which is what we wanted to show.
**![](https://lh7-us.googleusercontent.com/fCgJjBoSwtJj9vE5sDbdPKj9K8Kv5Erpn1eWX9HUg_YFQDTqJLX5NT1Wi59IKNPP1HJSmzW3OwAvKX6PphYpD6SJvty2odjtBvaLhG4ZiOD1ZmZ5Nlg7woEg35PwJhHRl-sQpv75RqNna7QmuynWpgM)**