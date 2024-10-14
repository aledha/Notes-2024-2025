Alexander Hatle
![[Pasted image 20241001140743.png|800]]
![[Pasted image 20241001141237.png|700]]
$$T=\begin{bmatrix}-50 & 35 & 0 \\ 35 & -70 & 0 \\ 0 & 0 & 0\end{bmatrix}$$
We can find the principal stresses by setting
$$\begin{aligned}
\det\begin{bmatrix}-50-\sigma  & 35 & 0 \\ 35 & -70-\sigma  & 0 \\ 0 & 0 & -\sigma \end{bmatrix}&= 0\\
(-50-\sigma )(-70-\sigma )(-\sigma )-35(35)(-\sigma )&= 0\\
-\sigma (3500+120\sigma +\sigma ^{2}-1225)&= 0
\end{aligned}$$
So $\sigma =0$ or
$$\sigma ^{2}+120\sigma +2275=0$$
which have the solutions $\sigma =-96.4$ or $\sigma =-23.6$.
Thus, $\sigma _{1}=0,\quad \sigma _{2}=-23.6,\quad \sigma _{3}=-96.4$.

To find the directions, we set
$$\begin{aligned}
T \mathbf n&=  \sigma \mathbf n\\
(T-\sigma I)\mathbf n&= 0
\end{aligned}$$
For $\sigma _{1}=0$, it is clear that $\mathbf n_{1}=[0,0,1]$.
For $\sigma _{2}=-23.6$:
$$\begin{aligned}
\begin{bmatrix}-50+23.6 & 35 & 0 \\ 35 & -70+23.6 & 0 \\ 0 & 0 & 23.6\end{bmatrix}\begin{bmatrix}n_1\\
n_{2}\\
n_{3}\end{bmatrix}=\begin{bmatrix}-26.4 & 35 & 0 \\ 35 & -46.4 & 0 \\ 0 & 0 & 23.6\end{bmatrix}\begin{bmatrix}n_1\\
n_{2}\\
n_{3}\end{bmatrix}=0
\end{aligned}$$
We see that $n_{3}=0$ and $n_{1}=\frac{35}{26.4}n_{2}$, so
$$\begin{aligned}
\mathbf n_{2}&= \frac{1}{\sqrt{\left(\frac{35}{26.4} \right)^{2}+1^{2}}}\begin{bmatrix}\frac{35}{26.4} \\ 1 \\ 0\end{bmatrix}\\
&= \begin{bmatrix}0.798\\
0.602\\
0\end{bmatrix}
\end{aligned}$$
For $\sigma _{3}=-96.4$:
$$\begin{aligned}
\begin{bmatrix}-50+96.4 & 35 & 0 \\ 35 & -70+96.4 & 0 \\ 0 & 0 & 96.4\end{bmatrix}\begin{bmatrix}n_1\\
n_{2}\\
n_{3}\end{bmatrix}=\begin{bmatrix}46.4 & 35 & 0 \\ 35 & 26.4 & 0 \\ 0 & 0 & 96.4\end{bmatrix}\begin{bmatrix}n_1\\
n_{2}\\
n_{3}\end{bmatrix}=0
\end{aligned}$$
again, $n_{3}=0$ and $n_{1}=-\frac{35}{46.4}n_{2}$, so
$$\begin{aligned}
\mathbf n_{3}&= \frac{1}{\sqrt{\left(\frac{-35}{46.4} \right)^{2}+1^{2}}}\begin{bmatrix}-\frac{35}{46.4} \\ 1 \\ 0\end{bmatrix}\\
&= \begin{bmatrix}-0.602\\
0.798\\
0\end{bmatrix}
\end{aligned}$$
The angles of these are 
$$\begin{aligned}
\alpha _{2}&= \tan ^{-1}\left(\frac{0.602}{0.798} \right)=37.03\degree\\
\alpha _{3}&= \tan ^{-1}\left(\frac{0.798}{-0.602} \right)=180\degree-52.97\degree=127.0\degree
\end{aligned}$$

![[Pasted image 20241001150712.png|800]]

$$\begin{aligned}
\sigma _{eq}&= \sqrt{\frac{1}{2}\left[(0-(-23.6))^{2}+(0-(-96.4))^{2}+(-23.6-(-96.4))^{2} \right]}\\
&= 87.03 \text{ MPa}
\end{aligned}$$
Since $\sigma _{eq}<\sigma _{\text{max}}$, the stress matrix does not lead to a fracture.

![[Pasted image 20241001151140.png|800]]
![[Pasted image 20241001151156.png|800]]
We can find out where each corner of the square deforms to:
* $A(0,0)$
	* $x_{1}=0$
	* $x_{2}=0$
* $B(1,0)$
	* $x_{1}=1$
	* $x_{2}=0$
* $C(1,1)$
	* $x_{1}=1+0.1 \cdot 1=1.1$
	* $x_{2}=(1+0.1)\cdot 1=1.1$
* $D(0,1)$
	* $x_{1}=0.1 \cdot 1=0.1$
	* $x_{2}=(1+0.1)\cdot 1=1.1$
So the deformed points are $A^{*}(0,0),\quad B^{*}(1,0),\quad C^{*}(1.1,1.1),\quad D^{*}(0.1,1.1)$.

![[Pasted image 20241001152038.png|800]]
$$\begin{aligned}
\lambda (AC)&=  \frac{A^{*}C^{*}}{AC}\\
&= \frac{\sqrt{1.1^{2}+1.1^{2}}}{\sqrt{1^{2}+1^{2}}}\\
&= 1.1
\end{aligned}$$

$$\begin{aligned}
\lambda (BD)&= \frac{B^{*}D^{*}}{BD}\\
&= \frac{\sqrt{(0.1-1)^{2}+1.1^{2}}}{\sqrt{(-1)^{2}+1^{2}}}\\
&= 1.005
\end{aligned}$$
![[Pasted image 20241001152702.png|800]]
In the deformed configuration,
$$\begin{aligned}
\mathbf e_{1}^{*}&= \frac{A^{*}D^{*}}{\lvert A^{*}D^{*} \rvert}\\
&= \frac{1}{\sqrt{0.1^2+1.1^2}}\begin{bmatrix}0.1\\
1.1\end{bmatrix}\\
&= \begin{bmatrix}0.0905\\
0.9959\end{bmatrix}
\end{aligned}$$
We also see that $\mathbf e_{2}^{*}=\mathbf e_{2}=\begin{bmatrix}1 \\ 0\end{bmatrix}$.
$$\begin{aligned}
\alpha &= \cos ^{-1}\left(\frac{\mathbf e_{1}\cdot \mathbf e_{2}}{\lvert \mathbf e_{1} \rvert \cdot \lvert \mathbf e_{2} \rvert} \right)\\
&= \cos ^{-1}(0.0905)\\
&= 84.8\degree
\end{aligned}$$

![[Pasted image 20241001154026.png|800]]
$F_{ij}=\frac{\partial x_{i}}{\partial X_{j}}$.
$$\begin{aligned}
\mathbf F&= \begin{bmatrix}\frac{\partial x_{1}}{\partial X_{1}} & \frac{\partial x_{1}}{\partial X_{2}} \\ \frac{\partial x_{2}}{\partial X_{1}} & \frac{\partial x_{2}}{\partial X_{2}} \end{bmatrix}\\
&= \begin{bmatrix}1 & 0.1\\
0 & 1.1\end{bmatrix}
\end{aligned}$$
$$\begin{aligned}
\mathbf E&= \frac{1}{2}(\mathbf F^{T}\mathbf F-\mathbf I)\\
&= \frac{1}{2}\left(\begin{bmatrix}1 & 0\\
0.1 & 1.1\end{bmatrix}\begin{bmatrix}1 & 0.1\\
0 & 1.1\end{bmatrix}-\begin{bmatrix}1 & 0\\
0 & 1\end{bmatrix} \right)\\
&= \frac{1}{2}\left(\begin{bmatrix}1 & 0.1\\
0.1 & 0.1^2+1.1^1\end{bmatrix} -\begin{bmatrix}1 & 0\\
0 & 1\end{bmatrix}\right)\\
&= \begin{bmatrix}0 & 0.05\\
0.05 & 0.11\end{bmatrix}
\end{aligned}$$

![[Pasted image 20241001154955.png|800]]
 Any direction vector may be denoted as
 $$\begin{aligned}
\mathbf n_{0}&= \cos \theta \mathbf e_{1}+\sin \theta \mathbf e_{2}\\
&= \cos \theta \begin{bmatrix}1\\
0\end{bmatrix}+\sin \theta \begin{bmatrix}0 \\
1\end{bmatrix}\\
&= \begin{bmatrix}\cos \theta  \\
\sin \theta \end{bmatrix}
\end{aligned}$$
 The deformed vector is
$$\begin{aligned}
\mathbf n&= \mathbf F \mathbf n_{0}\\
&= \mathbf F(\cos \theta \mathbf e_{1}+\sin \theta \mathbf e_{2})\\
&= \cos \theta \mathbf F \mathbf e_{1}+ \sin \theta \mathbf F \mathbf e_{2}\\
&= \cos \theta \begin{bmatrix}1 & 0.1\\
0 & 1.1\end{bmatrix}\begin{bmatrix}1\\
0\end{bmatrix}+ \sin \theta \begin{bmatrix}1 & 0.1\\
0 & 1.1\end{bmatrix}\begin{bmatrix}0 \\
1\end{bmatrix}\\
&= \cos \theta \begin{bmatrix}1\\
0\end{bmatrix}+\sin \theta \begin{bmatrix}0.1\\
1.1\end{bmatrix}\\
&= \begin{bmatrix}\cos \theta +0.1\sin \theta \\
1.1\sin \theta \end{bmatrix}
\end{aligned}$$
Now we can calculate the stretch ratio

$$
\begin{aligned}
\lambda &= \frac{\lVert \mathbf n \rVert}{\lVert \mathbf n_{0} \rVert}\\
&= \frac{(\cos \theta  +0.1\sin \theta )^{2}+1.1^{2}\sin ^{2}\theta }{\cos ^{2}\theta +\sin^{2} \theta }\\
&= \frac{\cos ^{2}\theta +0.2\cos \theta \sin \theta +0.01\sin ^{2}\theta +1.21\sin ^{2}\theta }{1}\\
&= \cos ^{2}\theta +0.2\cos \theta \sin \theta +1.22\sin ^{2}\theta \\
&= 1+0.2\cos \theta \sin \theta +0.22\sin ^{2}\theta 
\end{aligned}
$$
$$\begin{aligned}
\epsilon &= \lambda -1\\
&= 0.2\cos \theta \sin \theta +0.22\sin ^{2}\theta 
\end{aligned}$$
Calculating using the Green strain tensor
$$\begin{aligned}
\epsilon &= \mathbf n_{0}^{T}\mathbf E \mathbf n_{0}\\
&= \begin{bmatrix}\cos \theta  & \sin \theta \end{bmatrix}\begin{bmatrix}0 & 0.05\\
0.05 & 0.11\end{bmatrix}\begin{bmatrix}\cos \theta \\
\sin \theta \end{bmatrix}\\
&= \begin{bmatrix}\cos \theta  & \sin \theta \end{bmatrix}\begin{bmatrix}0.05\sin \theta \\
0.05\cos \theta +0.11 \sin \theta \end{bmatrix}\\
&= 0.05\cos \theta \sin \theta +\sin \theta (0.05\cos \theta +0.11\sin \theta )\\
&= 0.1\cos \theta \sin \theta +0.11\sin^{2} \theta 
\end{aligned}$$
which is half of the longitudinal strain calculated using $\mathbf F$.
![[Pasted image 20241002185347.png|700]]
$$
\begin{aligned}
\lambda (\theta )&= 1+0.2\cos \theta \sin  \theta +0.22\sin ^{2}\theta \\
\lambda'(\theta )&= -0.2 \sin^{2} \theta +0.2\cos ^{2}\theta +0.44 \sin \theta \cos \theta \\
&= 0.2 \cos 2\theta +0.22 \sin 2\theta =0\\
0.22\sin 2\theta &= -0.2\cos 2\theta \\
\tan 2\theta &= -\frac{0.2}{0.22}\\
2\theta &= \pi n +\tan ^{-1} \left(-\frac{10}{11} \right)\\
\theta &= \frac{\pi }{2}n-\frac{1}{2}\tan ^{-1}\left(\frac{10}{11} \right)\\
&= \frac{\pi }{2}n-0.369
\end{aligned}
$$
This gives us the solutions $\theta = \{1.202,2.773,4.323,5.914 \}=\{68.86\degree,158.85\degree,248.86\degree,338.86\degree \}$.
$$\begin{aligned}
\mathbf E \mathbf n(\theta )&= \begin{bmatrix}0 & 0.05\\
0.05 & 0.11\end{bmatrix}\begin{bmatrix}\cos \theta +0.1\sin \theta \\
1.1\sin \theta \end{bmatrix}\\
&= \begin{bmatrix}0.055\sin \theta \\
0.05\cos \theta +0.005\sin \theta +0.121 \sin \theta \end{bmatrix}\\
&= \begin{bmatrix}0.055\sin \theta \\
0.05\cos \theta +0.126\sin \theta \end{bmatrix}
\end{aligned}$$
Calculating $\mathbf E \mathbf n$ for each of the directions:
$$\begin{aligned}
\mathbf E \mathbf n(68.86\degree)&= \begin{bmatrix}0.051\\
0.136\end{bmatrix}\\
\mathbf E \mathbf n(158.85\degree)&= \begin{bmatrix}0.020\\
-0.001\end{bmatrix}\\
\mathbf E \mathbf n(248.86\degree)&= \begin{bmatrix}-0.051\\
-0.136\end{bmatrix}\\
\mathbf E \mathbf n(338.86\degree)&= \begin{bmatrix}-0.020\\
0.001\end{bmatrix}
\end{aligned}$$
I notice that $\mathbf E \mathbf n(68.86\degree)=-\mathbf E \mathbf n(248.86\degree)$, and $\mathbf E \mathbf n(158.85\degree)=-\mathbf E \mathbf n(338.85\degree)$, which makes sense since these are $180\degree$ apart from each other.

![[Pasted image 20241009121934.png|800]]
Consider the endpoints of the material line, 
We can express the deformed length as
$$\begin{aligned}
\text{ d}s^{2}&=  \left(\frac{\partial x_{i}}{\partial s_{0}}\frac{\partial x_{i}}{\partial s_{0}} \right)\text{ d}s_{0}^{2}\\
\frac{\text{d}s}{\text{d}s_{0}}&= \sqrt{\frac{\partial x_{i}}{\partial s_{0}}\frac{\partial x_{i}}{\partial s_{0}}}
\end{aligned}.$$

By the chain rule, we have that
$$\begin{aligned}
\frac{\partial x_{i}}{\partial s_{0}}&= \frac{\partial x_{i}}{\partial X_{k}}\frac{\partial X_{k}}{\partial s_{0}}\\
&= F_{ik}\frac{\text{ d} X_{k}}{\text{ d}s_{0}}.
\end{aligned}$$
Let the direction vector $\mathbf e=e_{i}\mathbf b_{i},$ where $\mathbf b_{i}$ are the basis vectors. The vector of the reference length in direction $e$ is
$$\text{ d}\mathbf r_{0}=\mathbf e \text{ d}s_{0}=\mathbf b_{k}\text{ d}X_{k},$$
then
$$\begin{aligned}
e_{k}\text{ d}s_{0}&= \text{ d}X_{k}\\
e_{k}&= \frac{\text{d}X_{k}}{\text{d}s_{0}}.
\end{aligned}$$
Substituting into the earlier equation, we get that
$$\frac{\partial x_{i}}{\partial s_{0}}=F_{ik}e_{k},$$
and 
$$\begin{aligned}
\frac{\text{d}s}{\text{d}s_{0}}&=  \sqrt{F_{ij}e_{j}F_{ik}e_{k}}\\
&= \sqrt{\mathbf e^{T} (\mathbf F^{T}\mathbf F) \mathbf e}
\end{aligned}$$
Since
$$\begin{aligned}
\mathbf E&=  \frac{1}{2}(\mathbf F^{T}\mathbf F-\mathbf I)\\
\mathbf F^{T}\mathbf F&= 2\mathbf E+\mathbf I,
\end{aligned}$$
we can rewrite this as
$$\begin{aligned}
\frac{\text{d}s}{\text{d}s_{0}}&= \sqrt{\mathbf e^{T}(2\mathbf E+\mathbf I)\mathbf e}\\
&= \sqrt{\mathbf e^{T}e+2\mathbf e^{T}\mathbf E \mathbf e}\\
&= \sqrt{1+2e_{i}E_{ij}e_{j}}.
\end{aligned}$$
So the stretch ratio is
$$\lambda = \sqrt{1+2e_{i}E_{ij}e_{j}},$$
and the longitudinal strain is 
$$\begin{aligned}
\epsilon &= \lambda -1\\
&= \sqrt{1+2e_{i}E_{ij}e_{j}}-1.
\end{aligned}$$

![[Pasted image 20241014132626.png|800]]
$$\epsilon =\sqrt{1+2e_{i}E_{ij}e_{j}}-1\tag{3}$$
Trying direction $\mathbf e_{1}=\begin{bmatrix}1 & 0 & 0\end{bmatrix}^{T}$ first,
$$\begin{aligned}
\epsilon &= \sqrt{1+2E_{11}}-1,\\
\lambda &= \sqrt{1+2E_{11}}.
\end{aligned}$$
We see that this generalizes to
$$\begin{aligned}
\epsilon _{k}&= \sqrt{1+2E_{kk}}-1\\
\lambda  _{k}&= \sqrt{1+2E_{kk}}
\end{aligned}$$
![[Pasted image 20241014133153.png|800]]
Since we have a sphere, the stresses must be equal in both directions: $\sigma _{1}=\sigma _{2}$, and the radiuses must also be equal: $r_{1}=r_{2}$. Then,
$$\begin{aligned}
\frac{\sigma }{r}+\frac{\sigma }{r}&= \frac{p}{t}\\
\sigma &= \frac{r}{2t}p.
\end{aligned}$$
![[Pasted image 20241014133524.png|800]]
$$\frac{\sigma _{z}}{r_{z}}+\frac{\sigma _{\theta }}{r_{\theta }}=\frac{p}{t}.$$
If we assume that $r_{z}\gg r_{\theta}$, then $\frac{\sigma _{z}}{r_{z}}$ is negligible compared to $\frac{\sigma _{\theta }}{r_{\theta }}$. Then,
$$\begin{aligned}
\frac{\sigma _{\theta }}{r_{\theta }}&= \frac{p}{t}\\
\sigma _{\theta }&= \frac{r_{\theta }}{t}p.
\end{aligned}$$
![[Pasted image 20241014134323.png|800]]
![[IMG_514E57C1E805-1.jpeg|800]]
From the figure, we see that
$$\begin{aligned}
F_{p}&= A_{p}p\\
&= \pi (r-t)^{2}p
\end{aligned}$$
since $t\ll r$, we can approximate this as
$$F_{p}=\pi r^{2}p.$$
For $F_{z}$, we can approximate the crossection $A_{t}$ as $2\pi r \cdot t$, giving
$$F_{z}=2\pi rt \sigma _{z}.$$
Setting $F_{z}=F_{p}$ gives
$$\begin{aligned}
2\pi rt \sigma _{z}&= \pi r^{2}p\\
\sigma _{z}&= \frac{r}{2t}p.
\end{aligned}$$
