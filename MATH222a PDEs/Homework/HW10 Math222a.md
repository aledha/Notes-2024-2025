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
The solution to this is $\hat u=\hat g \cdot e^{i \xi ^{3}t}$.
![[Pasted image 20231114141852.png|800]]
By Plancherel, we have that
$$\begin{align*}
\lVert u \rVert_{L^{2}_{x}}&=  \frac{1}{\sqrt{2\pi }} \lVert \hat u \rVert_{L^{2}_{\xi }}\\
&= \frac{1}{\sqrt{2\pi }}\lVert \hat g \cdot e^{i \xi ^{3}t} \rVert_{L^{2}_{\xi }}
\end{align*}$$

![[Pasted image 20231114141901.png|800]]

![[Pasted image 20231114141910.png|800]]

![[Pasted image 20231114141928.png|800]]

![[Pasted image 20231114141945.png|800]]

![[Pasted image 20231114141934.png|800]]