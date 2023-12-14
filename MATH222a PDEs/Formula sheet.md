![[Pasted image 20231212114702.png|800]]
![[Pasted image 20231212114814.png]]

Morrey:
![[Pasted image 20231212115923.png]]


Fourier 
1. $({\partial _{x^{j}}u})^{\wedge}=i \xi _{j}\hat u$
2. $(x^{j}u)^{\wedge}=i \partial _{\xi ^{j}}\hat u$
3. Modulation: 
	1. $(u(x-x_{0}))^{\wedge}=e^{-i \xi \cdot x_{0}}\hat u(\xi )$.
	2. $(e^{i \xi _{0}\cdot x}u)^{\wedge}=\hat u(\xi -\xi _{0})$ 
$$\begin{align*}
(u *v)^{\wedge}&= \hat u \cdot \hat v \tag{1}\\
(u \cdot v)^{\wedge}&= \frac{1}{(2\pi )^{d}}\hat u*\hat v \tag{2}
\end{align*}$$

maximum principle
![[Pasted image 20231212122407.png]]

![[Pasted image 20231212123747.png]]
lambo on wave


$$u \in BMO \quad\Leftrightarrow\quad [u]_{BMO}=\sup_{x \in \mathbb{R}^{d},r>0}\frac{1}{\lvert B_{r}(x) \rvert}\int_{B_{r}(x)}\lvert u(y)-u_{B_{r}(x)} \rvert \text{ d}y<\infty$$
where $u_{B_{r}(x)}$ is the average of $u$ in $B_{r}(x)$.


$$\begin{align*}
\mathcal{F}\left[1 \right]&= 2 \pi \delta _{0}(\xi )\\
\mathcal{F}^{-1}\left[1 \right]&= \delta _{0}(x)
\end{align*}$$

$$\mathcal{F}^{-1}\left[f \right](x)= \frac{1}{2\pi }\mathcal{F}\left[f \right](-x)$$