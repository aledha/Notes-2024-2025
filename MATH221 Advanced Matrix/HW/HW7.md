Alexander Hatle

![[Pasted image 20231015233438.png|800]]
Let 
$$A=\begin{bmatrix}U_{1} & U_{2}\end{bmatrix}\begin{bmatrix}\Sigma _{1} & 0 \\ 0 & 0\end{bmatrix}\begin{bmatrix}V_{1}    &  V_{2}\end{bmatrix}^{T},$$
where $U_{1}\in \mathbb{R}^{m \times r},V_{1} \in \mathbb{R}^{n \times r}$,  $\Sigma _{1}\in \mathbb{R}^{r \times r},$ and $\text{rank}(A)=r$.
Using the fact that multiplying with an orthogonal matrix does not change the norm,
$$\begin{align*}
\lVert A X -I\rVert_{F}&=  \left\lVert U\Sigma V^{T} X-I\right\rVert_{F}\\
&= \left\lVert \Sigma V^{T} X-U^{T} \right\rVert_{F}.
\end{align*}$$
Let's denote $Y=V^{T}X$,
$$\begin{align*}
\lVert AX-I \rVert_{F}&= \left\lVert \Sigma Y-U^{T} \right\rVert_{F}\\
&= \left\lVert \begin{bmatrix}\Sigma_{1} & 0\\
0 & 0 \end{bmatrix}\begin{bmatrix}Y_{1}\\
Y_{2}\end{bmatrix} -\begin{bmatrix}U_{1}^{T}\\
U_{2}^{T}\end{bmatrix} \right\rVert_{F}\\
			&= \lVert \Sigma _{1}Y_{1}-U_{1}^{T} \rVert_{F}+\lVert -U_{2}^{T} \rVert_{F},
\end{align*}$$
which is minimized by $Y_{1}=\Sigma _{1}^{-1}U_{1}^{T}$.
$$\begin{align*}
V^{T}X&= Y \\
X&= VY\\
X&= \begin{bmatrix}V_{1} & V_{2}\end{bmatrix}\begin{bmatrix}\Sigma _{1}^{-1}U_{1}^{T}\\
Y_{2}\end{bmatrix}\\
X&= V_{1}\Sigma _{1}^{-1}U_{1}^{T}+V_{2}Y_{2}\\
X&= A^{+}+V_{2}Y_{2}
\end{align*}$$
Any matrix of this form minimizes the norm, which has a value of
$$\lVert AA^{+}-I \rVert_{F}=\lVert U_{2} \rVert_{F}.$$
![[Pasted image 20231015233458.png|800]]
Let's say that $C \in \mathbb{R}^{n \times m},\quad A \in \mathbb{R}^{n \times p},\quad B \in \mathbb{R}^{q \times m}$, and $X \in \mathbb{R}^{p \times q}$. 
I will use the following notation for the SVD
$$\begin{align*}
A&= U_{A}\Sigma _{A}V^{T}_{A}=\begin{bmatrix}U_{A1} & U_{A2}\end{bmatrix}\begin{bmatrix}\Sigma _{A1} & 0 \\ 0 & 0\end{bmatrix}\begin{bmatrix}V_{A1} & V_{A2}\end{bmatrix}^{T}\\
B&= U_{B}\Sigma _{B}V^{T}_{B}=\begin{bmatrix}U_{B1} & U_{B2}\end{bmatrix}\begin{bmatrix}\Sigma _{B1} & 0 \\ 0 & 0\end{bmatrix}\begin{bmatrix}V_{B1} & V_{B2}\end{bmatrix}^{T},
\end{align*}$$
where $\Sigma _{A1} \in \mathbb{R}^{r_{A} \times r_{A}}$ and $\Sigma _{B1} \in \mathbb{R}^{r_{B} \times r_{B}}$, and $\text{rank}(A)=r_{A},\quad \text{rank}(B)=r_{B}$.
Let's write up the norm
$$\begin{align*}
\lVert AXB-C \rVert_{F}&= \lVert U_{A}\Sigma _{A}V^{T}_{A}XU_{B}\Sigma _{B}V_{B}^{T}-C \rVert_{F}\\
	&= \left\lVert \Sigma _{A}Y \Sigma _{B}-U_{A}^{T}CV_{B} \right\rVert_{F},
\end{align*}$$
where $Y=V_{A}^{T}XU_{B}\in \mathbb{R}^{p \times q}$ and I have used that multiplying with an orthogonal matrix does not change its norm. Also, minimizing $\lVert Y \rVert_{F}$ is the same as minimizing $\lVert X \rVert_{F}$. Using our block matrix decomposition,
$$\begin{align*}
\left\lVert AXB-C \right\rVert_{F}&= \left\lVert \begin{bmatrix}\Sigma _{A1} & 0 \\ 0 & 0\end{bmatrix}\begin{bmatrix}Y_{11} & Y_{12}\\
Y_{21} & Y_{22}\end{bmatrix}\begin{bmatrix}\Sigma _{B1} & 0 \\ 0 & 0\end{bmatrix} -\begin{bmatrix}U_{A1}^{T} \\ U_{A2}^{T}\end{bmatrix}C\begin{bmatrix}V_{B1} & V_{B2}\end{bmatrix}\right\rVert_{F}
\end{align*}$$
Here, $Y_{11}\in \mathbb{R}^{r_{A} \times r_{B}}, \quad Y_{21}\in \mathbb{R}^{(p-r_{A}) \times r_{B}}, \quad Y_{12}\in \mathbb{R}^{r_{A}\times(q-r_{B})}, \quad Y_{22}\in \mathbb{R}^{(p-r_{A})\times(q-r_{B})}$. 
$$\begin{align*}
\left\lVert AXB-C \right\rVert_{F}&=  \left\lVert \begin{bmatrix}\Sigma _{A1}Y_{11}\Sigma _{B1} & 0 \\ 0 & 0\end{bmatrix} -\begin{bmatrix}U_{A1}^{T}CV_{B1} & U_{A1}^{T}CV_{B2} \\ U_{A2}^{T}CV_{B1} & U_{A2}^{T}CV_{B2}\end{bmatrix}\right\rVert_{F}\\
&= \left\lVert \Sigma _{A1}Y_{11}\Sigma _{B1}-U_{A1}^{T}CV_{B1} \right\rVert_{F}+\lVert U_{A2}^{T}CV_{B1} \rVert_{F}\\
&\quad + \lVert U_{A1}^{T}CV_{B2} \rVert_{F}+\lVert U_{A2}^{T}CV_{B2} \rVert_{F},
\end{align*}$$
which is minimized when $Y_{11}=\Sigma _{A1}^{-1}U_{A1}^{T}CV_{B1}\Sigma _{B1}^{-1}$. 
Further, $\lVert Y \rVert_{F}$ is minimized when the rest of $Y$ is set to zero. We then obtain the desired result,
$$\begin{align*}
X_{0}&= V_{A}YU_{B}^{T}\\
&= \begin{bmatrix}V_{A1}   &  V_{A2}\end{bmatrix}\begin{bmatrix}\Sigma _{A1}^{-1}U_{A1}^{T}CV_{B1}\Sigma _{B1}^{-1} & 0 \\ 0 & 0\end{bmatrix}\begin{bmatrix}U_{B1}^{T} \\ U_{B2}^{T}\end{bmatrix}\\
&= V_{A1}\Sigma _{A1}^{-1}U_{A1}^{T}CV_{B1}\Sigma _{B1}^{-1}U_{B1}^{-1}\\
&= A^{+}CB^{+}.
\end{align*}$$
<div style="page-break-after: always;"></div>


![[Pasted image 20231015233512.png|800]]

$$\begin{align*}
AA^{+}A&= U \Sigma V^{T}V \Sigma ^{+}U^{T}U \Sigma V^{T}\\
&= U \Sigma \Sigma ^{+}\Sigma V^{T}\\
&= U \begin{bmatrix}\Sigma _{1} & 0\\
0 & 0\end{bmatrix}\begin{bmatrix}\Sigma ^{-1}_{1} & 0\\
0 & 0\end{bmatrix}\begin{bmatrix}\Sigma _{1} & 0\\
0 & 0\end{bmatrix} V^{T}\\
&= U \Sigma V^{T}=A
\end{align*}$$

$$\begin{align*}
A^{+}AA^{+}&= V \Sigma ^{+}U^{T}U \Sigma V^{T}V \Sigma ^{+}U^{T}\\
&= V  \begin{bmatrix}\Sigma _{1}^{-1} & 0\\
0 & 0\end{bmatrix}\begin{bmatrix}\Sigma _{1} & 0\\
0 & 0\end{bmatrix}\begin{bmatrix}\Sigma _{1}^{-1} & 0\\
0 & 0\end{bmatrix}U^{T}\\
&= V \Sigma ^{+}U^{T}=A^{+}
\end{align*}$$
$$\begin{align*}
(A^{+}A)^{T}&= (V \Sigma ^{+}U^{T}U \Sigma V^{T})^{T}\\
&= V \Sigma ^{T}U^{T} U (\Sigma ^{+})^{T}V^{T}\\
&= V \Sigma ^{T}(\Sigma ^{+})^{T}V^{T}\\
&= V \begin{bmatrix}\Sigma ^{T}_{1} & 0\\
0 & 0\end{bmatrix}\begin{bmatrix}\Sigma _{1}^{-T} & 0\\
0 & 0\end{bmatrix}V^{T}\\
&= V\begin{bmatrix}\Sigma _{1}^{-1} & 0\\
0 & 0\end{bmatrix}\begin{bmatrix}\Sigma _{1} & 0\\
0 & 0\end{bmatrix}V^{T}\\
&= V \Sigma ^{+}U^{T}U \Sigma V^{T}=A^{+}A
\end{align*}$$

$$\begin{align*}
(AA^{+})^{T}&= (U \Sigma V^{T}V \Sigma ^{+}U^{T})^{T}\\
&= U (\Sigma ^{+})^{T}V^{T}V \Sigma ^{T}U^{T} \\
&= U (\Sigma ^{+})^{T}\Sigma ^{T}U^{T}\\
&= U \Sigma \Sigma ^{+}U^{T}\\
&= U \Sigma V^{T}V \Sigma ^{+}U^{T}=AA^{+}
\end{align*}$$
<div style="page-break-after: always;"></div>

![[Pasted image 20231015233530.png|800]]

$$\begin{align*}
H&= \begin{bmatrix}0 & A^{T} \\ A & 0\end{bmatrix}=\begin{bmatrix}0 & V \Sigma^{T } U^{T} \\ U \Sigma V^{T} & 0\end{bmatrix}\\
&= \begin{bmatrix}V  & 0\\
0& U\end{bmatrix}\begin{bmatrix}0 & \Sigma^{T} U^{T}\\
\Sigma V^{T}  & 0\end{bmatrix}\\
&= \begin{bmatrix}V &0\\
0 &  U\end{bmatrix} \begin{bmatrix}0 & \Sigma ^{T}\\
\Sigma  & 0\end{bmatrix}\begin{bmatrix}V^{T} &0\\
0 &  U^{T}\end{bmatrix}\\
&= :C \tilde \Sigma C^{T}
\end{align*}$$
Note that $C$ is unitary, 
$$\begin{bmatrix}V & 0 \\ 0 & U\end{bmatrix}\begin{bmatrix}V^{T} & 0 \\ 0 & U^{T}\end{bmatrix}=\begin{bmatrix}I & 0 \\ 0 & I\end{bmatrix}.$$

If $C^{T}v$ is an eigenvector of $\tilde \Sigma$, then $Hv=C \tilde \Sigma (C^{T}v)=C \lambda C^{T}v=\lambda v$.
Thus, $H$ and $\tilde \Sigma$ have the same eigenvalues, while if $v$ is a an eigenvector of $H$, then $C^{T}v$ is an eigenvector of $\tilde \Sigma$.
Let's find these eigenvectors and eigenvalues.
$$\begin{bmatrix}& &     &  \sigma _{1} &   &  \\&  &   &  & \ddots \\ & &   &   &   &  \sigma _{n} \\   \sigma _{1} \\ & \ddots\\ &   &  \sigma _{n}\end{bmatrix}\begin{bmatrix}p_{1} \\ \vdots \\ p_{n} \\ q_{1} \\ \vdots \\ q_{n}\end{bmatrix}=\begin{bmatrix}\sigma _{1}q_{1} \\ \vdots \\ \sigma _{n}q_{n} \\ \sigma _{1}p_{1} \\ \vdots \\ \sigma _{n}p_{n}\end{bmatrix}$$
We see that we get an eigenvector if we choose $p,q$ such it's nonzero for all indices except for exactly one $q_{j}=\pm p_{j}$.
The $2n$ unit eigenvectors are of the form $\frac{1}{\sqrt{2}}\begin{bmatrix}e_{j} \\ \pm e_{j}\end{bmatrix}$, where $e_{j}$ denotes the $j$th canonical basis vector. The corresponding eigenvalue is $\pm \sigma _{j}$. 

Therefore, the $2n$ eigenvectors of $H$ are 
$$\begin{align*}
C \frac{1}{\sqrt{2}}\begin{bmatrix}e_{j} \\ \pm e_{j}\end{bmatrix}&=  \frac{1}{\sqrt{2}}\begin{bmatrix}V & 0 \\ 0 & U\end{bmatrix}\begin{bmatrix}e_{j} \\ \pm e_{j}\end{bmatrix}\\
&= \frac{1}{\sqrt{2}}\begin{bmatrix}v_{j}\\
\pm u_{j}\end{bmatrix},
\end{align*}$$
with corresponding eigenvalues $\sigma _{j}$.

For rectangular $A \in \mathbb{R}^{m\times n}$, we have that 
$$H=\begin{array}{c}
\begin{matrix}
 \!n \! & m
\end{matrix} \\
\left[\ \begin{matrix}
0 & A^{T} \\ A & 0
	\end{matrix}\ \right]
	&\begin{matrix}
 \!n \! \\ m
\end{matrix}
\end{array}$$
The argument is the same until we inspect the eigenvalues and vectors of $\tilde \Sigma$. Let's assume that $A$ has rank $r$.
$$\begin{bmatrix}& &  &   &  \sigma _{1} &   &  \\&  & &  &  & \ddots \\ & &  & &   &   &  \sigma _{r} \\& & &  &   &   &     & 0 \\    \sigma _{1} \\ & \ddots\\ &   &  \sigma _{r} \\  &   &   & 0\end{bmatrix}\begin{bmatrix}p_{1} \\ \vdots \\ p_{n} \\ q_{1} \\ \vdots \\ q_{m}\end{bmatrix}=\begin{bmatrix}\sigma _{1}q_{1} \\ \vdots \\ \sigma _{r}q_{r} \\ 0 \\ \sigma _{1}p_{1} \\ \vdots \\ \sigma _{r}p_{r} \\ 0\end{bmatrix}$$
Again, we end up with the eigenvectors of the form $\frac{1}{\sqrt{2}}\begin{array}{c}\begin{bmatrix}e_{j} \\ \pm e_{j}\end{bmatrix}\begin{matrix}\}n \\\} m\end{matrix}\end{array}$  with corresponding eigenvalue $\sigma _{j}$ for $j \le r$.
For $H$, the $2r$ eigenvectors are
$$\frac{1}{\sqrt{2}}\begin{bmatrix}V & 0 \\ 0 & U\end{bmatrix}\begin{bmatrix}e_{j} \\ \pm e_{j}\end{bmatrix}= \frac{1}{\sqrt{2}}\begin{bmatrix}v_{j} \\ \pm u_{j}\end{bmatrix}$$
with corresponding eigenvalue $\sigma _{j}$ for $j\le r$.