By Alexander Hatle
![[Pasted image 20240223103120.png]]
Since all the sides are straight, we can describe the boundaries as
$$\begin{align*}
\mathbf R(0,\eta )&= (1-\eta )\mathbf R(0,0)+\eta \mathbf R(0,1)\\
\mathbf R(1,\eta )&= (1-\eta )\mathbf R(1,0)+\eta \mathbf R(1,1)\\
\mathbf R(\xi ,0 )&= (1-\xi )\mathbf R(0,0)+\xi  \mathbf R(1,0)\\
\mathbf R(\xi ,1 )&= (1-\xi  )\mathbf R(0,1)+\xi \mathbf R(1,1)
\end{align*}$$
The linear interpolants in the $\xi$ direction is
$$\begin{align*}
\Pi _{\xi }\mathbf R&= (1-\xi )\mathbf R(0,\eta )+\xi \mathbf R(1,\eta ),\\
&= (1-\xi )\left[(1-\eta )\mathbf R(0,0)+\eta \mathbf R(0,1) \right] + \xi \left[(1-\eta )\mathbf R(1,0)+\eta \mathbf R(1,1) \right],\\
&= (1-\xi )(1-\eta) \mathbf R(0,0)+(1-\xi )\eta \mathbf R(0,1)+\xi (1-\eta )\mathbf R(1,0)+\xi \eta \mathbf R(1,1),
\end{align*}$$
while the $\eta$ is similar,
$$\begin{align*}
\Pi _\eta \mathbf R&= (1-\eta )\mathbf R(\xi ,0)+\eta \mathbf R(\xi ,1),\\
&= (1-\eta )\left[(1-\xi )\mathbf R(0,0)+\xi \mathbf R(1,0) \right] + \eta \left[(1-\xi )\mathbf R(0,1)+\xi \mathbf R(1,1) \right],\\
&= (1-\xi )(1-\eta ) \mathbf R(0,0)+ \xi (1-\eta )\mathbf R(1,0)+ (1-\xi )\eta \mathbf R(0,1)+ \xi \eta \mathbf R(1,1),\\
&= \Pi _{\xi} \mathbf R.
\end{align*}$$
The transfinite interpolation is obtained by the Boolean sum
$$\begin{align*}
\hat {\mathbf R}(\xi ,\eta )&= (\Pi _{\xi }+\Pi_{\eta }-\Pi _{\xi }\Pi _{\eta } )\mathbf R(\xi ,\eta ),\\
&= 2\Pi _{\xi }\mathbf R(\xi ,\eta  ) -(1-\xi )(1-\eta ) \mathbf R(0,0)- \xi (1-\eta )\mathbf R(1,0)- (1-\xi )\eta \mathbf R(0,1)- \xi \eta \mathbf R(1,1),\\
&= 2\Pi _{\xi }\mathbf R(\xi ,\eta )-\Pi _{\xi }\mathbf R(\xi ,\eta ),\\
&= \Pi _{\xi }\mathbf R(\xi ,\eta ),\\
&= (1-\xi )(1-\eta ) \mathbf R(0,0)+ \xi (1-\eta )\mathbf R(1,0)+ (1-\xi )\eta \mathbf R(0,1)+ \xi \eta \mathbf R(1,1).
\end{align*}$$
This is equivalent to a bilinear mapping of the four corners $\mathbf R(0,0), \mathbf R(1,0),\mathbf R(0,1)$ and $\mathbf R(1,1)$.

<div style="page-break-after: always;"></div>


![[Pasted image 20240223103130.png]]
See attached Julia file. Output:
![[Pasted image 20240301205410.png|500]]

![[Pasted image 20240223103147.png]]
First, I constructed a Hermite interpolant for $x$ with
$$x(\xi )=0H_{0}(\xi )+1H_{1}(\xi )+T \tilde H_{0}(\xi )+T \tilde H_{1}(\xi ),$$
then I sat the bottom and top boundaries as
$$\begin{align*}
\mathbf R(\xi ,0)&= [x(\xi ), y_\text{bottom}(x(\xi ))],\\
\mathbf R(\xi ,1)&= [x(\xi ), y_\text{top}(x(\xi ))].
\end{align*}$$
The impose the derivative condition on the top and bottom boundary, we must figure out the normal direction. This direction can be described as
$$\mathbf n =\frac{1}{\sqrt{\text{d}y^{2}+\text{d}x^{2}}}\left[-\text{d}y,\text{d}x \right],$$
where we obtain $\text{d}y, \text{d}x$ from computing the derivative at the top and bottom points,
$$y'(x(\xi ))=\frac{\text{d}y}{\text{d}x}.$$
See attached Julia file. I get the following as output.
![[Pasted image 20240301213548.png|500]]

<div style="page-break-after: always;"></div>

![[Pasted image 20240223103156.png]]
Firstly, notice that 
$$\partial _{z}w(z)=\frac{2e^{z}(3e^{z}-2)-(2e^{z}-3)3e^{z}}{(3e^{z}-2)^{2}}=\frac{5e^{z}}{(3e^{z}-2)^{2}}≠0,$$
meaning that this defines a conformal mapping.
Let's call $z=x+yi$,
$$w(x,y)=\frac{2e^{x+yi}-3}{3e^{x+yi}-2}.$$
This mapping maps every vertical line in the imaginary plane (every fixed $\text{Re}(z)$) to a circle with its center on the real number line. So the image of this mapping is between the two circles, the first corresponding to fixed $\text{Re}(z)=0$ and the second corresponding to $\text{Re}(z)=1$.
We need to find the size and location of these circles. Starting with the image of the vertical line $x=0$, the circle is described by
$$w(0,y)=\frac{2e^{yi}-3}{3e^{yi}-2}\quad\text{for }0 \le y \le 2\pi.$$
Since we already know that this circle is centered on the real number line, we only need to figure out where the circle intersects the real number line, namely when $y=0$ and when $y=\pi$. These two values are
$$\begin{align*}
w(0,0)=\frac{2-3}{3-2}&= -1,\\
w(0,\pi )=\frac{-2-3}{-3-2}&= 1,
\end{align*}$$
meaning that this is a circle centered at $0$ with radius $1$.

The vertical line $x=1$ maps to 
$$w(1,y)=\frac{2ee^{yi}-3}{3ee^{yi}-2} \quad\text{for }0 \le y\le2\pi, $$
which intersects the real number line at 
$$\begin{align*}
w(1,0)&= \frac{2e-3}{3e-2},\\
w(1,\pi )&= \frac{-2e-3}{-3e-2}.
\end{align*}$$
So the center of this circle is
$$\frac{1}{2}(w(1,\pi )+w(0,\pi ))≈0.6133\dots ,$$
while the radius is
$$\frac{1}{2}(w(1,\pi )-w(0,\pi ))≈0.2175\dots$$
Since this mapping is conformal, grid orthogonality is preserved. Therefore, we can simply plug in the rectangular grid to the mapping and get a structured grid with orthogonal grid lines.
![[Pasted image 20240301194454.png|500]]
We clearly see that the area is between the two circles described above.

<div style="page-break-after: always;"></div>

![[Pasted image 20240301213619.png]]
See attached file. My function includes an argument to include the history of the mesh, so that the prosess could be animated. Sadly, I cannot attach an animation, so here's the final result of the example in the problem, as well as a test on another polygon.

![[Pasted image 20240301215303.png|500]]
![[Pasted image 20240301215224.png|500]]
]]