How Alexander Hatle
![[Pasted image 20230917195556.png|800]]
We let
$$g(y)=\sum_{k \in \mathbb Z^{n}}^{}f(y+k).$$
Each element can be written as
$$g_{j}(x)=\sum_{k \in \mathbb Z}^{}f_{j}(x+k),$$
where $x \in \mathbb{R}$. Since $g$ has period 1, we take its Fourier series
$$g_{j}(x)=\sum_{n \in \mathbb Z}^{}c_{j}(n)e^{2\pi inx}$$
Where
$$\begin{align*}
c_{j}(n)&= \int_{0}^{1}g_{j}(x)e^{-2\pi inx} \text{ d}x\\
&= \int_{0}^{1}\sum_{k \in \mathbb Z}f_{j}(x+k)e^{-2\pi inx} \text{ d}x
\end{align*}$$
We can use Fubinis theorem as the integral is bounded (else $\hat f$ wouldn't exist), #ask is this allowed?
$$\begin{align*}
c_{j}(n)&= \sum_{k \in \mathbb Z}^{}\int_{0}^{1}f_{j}(x+k)e^{-2\pi inx}\text{ d}x\\
&= \int_{0}^{1}\left(\dots+f_{j}(x-1)+f_{j}(x)+f_{j}(x+1)+\dots \right)e^{-2\pi inx}\text{ d}x\\
&= \int_{-\infty}^{\infty}f_{j}(x)e^{-2\pi inx}\text{ d}x=\hat f_{j}(n),
\end{align*}$$
where I have used that $e^{-2\pi inx_{j}}$ has period 1. So far, we have that
$$\begin{align*}
g_{j}(x)&= \sum_{k \in \mathbb Z}^{}f_{j}(x+k)=\sum_{n \in \mathbb Z}^{}\hat f_{j}(n)e^{-2\pi inx}\\
	g_{j}(0)&= \sum_{k \in \mathbb Z}f_{j}(k)=\sum_{m \in \mathbb Z}^{}\hat f_{j}(m)\\
	&\quad \text{ }\sum_{k \in \mathbb Z^{n}}^{}f(k)=\sum_{m \in \mathbb Z^{n}}^{}\hat f(m).
\end{align*}$$

![[Pasted image 20230906123326.png|800]]
We can let 
$$f_{m}=f*g_{m},$$
where $g_{m}=m^{n}e^{-\pi m^{2}\lVert x \rVert^{2}}$ is the Gaussian. Since $f$ and $g_{m}$ are both $L^{1}(\mathbb{R}^{n})$, their convolution $f_{m}$ is also $L^{1}(\mathbb{R}^{n})$.

$$\hat f_{m}(\xi )=\hat f(\xi )\int g_{m}(x) e^{-2\pi ix \cdot \xi } \text{ d}x$$


![[Pasted image 20230906123356.png|800]]

![[Pasted image 20230906123451.png|800]]
Assuming $\phi \in L^{1}(\mathbb{R}^{n})$ and $\int_{\mathbb{R}^{n}}\phi (x)\text{ d}x=1$. Let $\psi (x)=\text{essup}_{\lvert y \rvert \ge \lvert x \rvert}\lvert \phi (y) \rvert$ and assume further $\psi \in L^{1}(\mathbb{R}^{n})$. For a Lebesgue point $x_{0}$ of $f(x) \in L^{p}(\mathbb{R}^{n})(p>1)$, prove that 
$$\lim_{t \to 0^{+}}\phi _{t}*f(x_{0})=f(x_{0})$$
Firstly, I wish to express the difference of $\phi _{t}*f(x_{0})$ and $f(x_{0})$, to later show that this tends to zero as $t\to 0^{+}$.
$$\begin{align*}
(\phi_{t} * f)(x_{0}) &=  \int_{\mathbb{R}^{n}} \phi_{t}(x_{0} - y) f(y) \text{ d}y\\
\phi_{t} * f(x_{0}) - f(x_{0}) &=  \int_{\mathbb{R}^{n}} \phi_{t}(x_{0} - y)[f(y) - f(x_{0})] \text{ d}y,
\end{align*}$$
where I have used that $\int_{\mathbb{R}^{n}}\phi_{t} (x)\text{ d}x=1$.

Since $x_{0}$ is a Lebesgue point, we have that for any $\epsilon >0$, there exists $\delta >0$ such that whenever $\lVert y-x_{0} \rVert<\delta$, we have $\lvert f(y)-f(x_{0}) \rvert < \epsilon$. Knowing this, let's split up the integral above into two, one where the above condition holds and one where it doesn't, and then apply absolute value to get bounds.
$$\begin{align*}
\left\lvert \int_{\mathbb{R}^{n}}\phi _{t}(x_{0}-y)\left[f(y)-f(x_{0}) \right]\text{ d}y \right\rvert &\le  \int_{\lVert y-x_{0} \rVert<\delta }\lvert \phi _{t}(x_{0}-y) \rvert \lvert f(y)-f(x_{0}) \rvert  \text{ d}y\\
&+\int_{\lVert y -x_{0}\rVert \ge \delta }\lvert \phi _{t}(x_{0}-y) \rvert \lvert f(y)-f(x_{0}) \rvert  \text{ d}y\\
&=:I_{1}+I_{2} 
\end{align*}$$
Let's inspect $I_{1}$.
$$\begin{align*}
I_{1}&= \int_{\lVert y-x_{0} \rVert<\delta }\lvert \phi _{t}(x_{0}-y) \rvert \lvert f(y)-f(x_{0}) \rvert  \text{ d}y\\
&< \epsilon \int_{\lVert y-x_{0} \rVert<\delta }\left\lvert \phi _{t}(x_{0}-y)\right\rvert \text{ d}y\\
	I_{1} &\le \epsilon \lVert \phi  \rVert_{1}, 
\end{align*}$$
which can be made arbitrarily small since $\psi \in L^{1}(\mathbb{R}^{n})$.

Now moving onto $I_{2}$.
$$I_{2}=\int_{\lVert y-x_{0} \rVert \ge \delta }\lvert \phi _{t}(x_{0}-y) \rvert \lvert f(y)-f(x_{0}) \rvert  \text{ d}y$$
We have that $\psi (x)=\text{essup}_{\lVert y \rVert \ge \lVert x \rVert}\lvert \phi (y) \rvert \in L^{1}(\mathbb{R}^{n})$.
We let $\psi _{t}(x)= \frac{1}{t^{n}}\psi \left(\frac{x}{t}\right)$, then $\psi _{t}(x)=\text{essup}_{\lVert y \rVert \ge \lVert x \rVert}\lvert \phi_{t} (y) \rvert$.

It follows that $\psi _{t}(x_{0}-y)\ge \phi _{t}(x_{0}-y)$.
$$\begin{align*}
I_{2}&= \int_{\lVert y-x_{0} \rVert\ge \delta }\lvert \psi _{t}(x_{0}-y) \rvert \lvert f(y)-f(x_{0}) \rvert \text{ d}y\\
		&\le \lVert \psi _{t} \rVert_{q} \lVert f \rVert_{p}+f(x_{0})\lVert \psi _{t} \rVert_{q},
\end{align*}$$
where I have used Hölder's inequality. We know that $f \in L^{p}(\mathbb{R}^{n})$ for $p>1$, so we must bound $\lVert \psi _{t} \rVert_{q}$ for $q<\infty$.
$$\lVert \psi _{t} \rVert_{q}=\left(\int_{\mathbb{R}^{n}}\left\lvert \frac{1}{t^{n}}\psi (x) \right\rvert^{q} \text{ d}x \right)^{\frac{1}{q}}$$

![[Pasted image 20230906123425.png|800]]
Any degree order $N$ can be written as
$$\begin{align*}
P(x)&= \sum_{n=-N}^{N}c_{n}e^{2\pi inx}\\
	P'(x)&= \sum_{n=-N}^{N}c_{n}2\pi ine^{2\pi inx}\\
\lvert P'(x) \rvert&\le 2\pi N \left\lvert \sum_{n=-N}^{N}c_{n}e^{2\pi inx} \right\rvert\\
\lvert P'(x) \rvert&\le 2\pi N \lvert P(x) \rvert\\
	\lVert P' \rVert_{\infty}&≲N \lVert P \rVert_{\infty}\\
\end{align*}$$

