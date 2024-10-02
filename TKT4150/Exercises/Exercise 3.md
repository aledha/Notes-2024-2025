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
 $\mathbf n_{0}=\cos \theta \mathbf e_{1}+\sin \theta \mathbf e_{2}$.
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