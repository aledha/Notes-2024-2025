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

![[Pasted image 20230906123425.png|800]]