Alexander Hatle

![[Pasted image 20240402132322.png]]

Applying the divergence theorem and applying the boundary conditions, we get the following Galerkin formulation:
Given a triangulation $T_{h}$, we can describe the space of continuous piece-wise linear functions as
$$V_{h}=\{v \in C^{0}(\Omega  ):\quad v|_{K}\in \mathbb P_{1}(K)\quad\forall K \in T_{h} \}$$
Find $u_{h}\in V_{h}$ such that, for every $v \in V_{h}$,
$$\begin{align*}
\int_{\Omega }v(-\nabla ^{2}u_{h}-k^{2}u_{h})\text{ d}\mathbf x&= 0, \\
\int_{\Omega }\nabla v \cdot \nabla u_{h} \text{ d}\mathbf x-\oint_{\Gamma }v  (\mathbf n \cdot \nabla u_{h}) \text{ d}s-k^{2}\int_{\Omega }vu_{h}\text{ d}\mathbf x&= 0, \\
\int_{\Omega }\nabla v \cdot \nabla u_{h}\text{ d}\mathbf x-k^{2}\int_{\Omega }vu_{h}\text{ d}\mathbf x- \int_{\Gamma _\text{out}}v(-iku_{h})\text{ d}s-\int_{\Gamma _\text{in}}vik(2-u_{h}) \text{ d}s&=0,\\
\int_{\Omega }\nabla v \cdot \nabla u_{h}\text{ d}\mathbf x-k^{2}\int_{\Omega }vu_{h}\text{ d}\mathbf x+ik \left(\int_{\Gamma _{\text{out}}}vu_{h}\text{ d}s +\int_{\Gamma _{\text{in}}}vu_{h}\text{ d}s \right)&= 2ik \int_{\Gamma _{\text{in}}} v \text{ d}s . 
\end{align*}$$

![[Pasted image 20240402132407.png]]
Using a nodal basis, $V_{h}=\text{span}\{\phi _{1},\dots ,\phi _n \}$, we can write any $v \in V_{h}$ as $v(x)=\sum_{i=1}^{n}v_{i}\phi _{i}(x)$, where $v_{i}$ are scalars. 
$$\begin{align*}
\int_{\Omega }\nabla \phi _{j} \cdot \nabla \left(\sum_{i=1}^{n}u_{h,i}\phi _{i} \right)\text{ d}\mathbf x-k^{2}\int_{\Omega }\phi _{j}\left(\sum_{i=1}^{n}u_{h,i}\phi _{i} \right)\text{ d}\mathbf x&\\
+ik \left(\int_{\Gamma _{\text{out}}}\phi _{j} \left(\sum_{i=1}^{n}u_{h,i}\phi _{i} \right)\text{ d}s +\int_{\Gamma _{\text{in}}}\phi _{j}\left(\sum_{i=1}^{n}u_{h,i}\phi _{i} \right)\text{ d}s\right)&= 2ik \int_{\Gamma _{\text{in}}} \phi _{j} \text{ d}s \tag{G} \qquad\text{for }j=1,\dots,n
\end{align*}$$
where we can switch the order of summation and integration,
$$\begin{align*}
\sum_{i=1}^{n}\Bigg[\int_{\Omega }\nabla \phi _{j}\cdot \nabla \phi _{i} \text{ d}\mathbf x-k^{2}\int_{\Omega }\phi _{j}\phi _{i}\text{ d}\mathbf x \text{ }+&\\
ik \left(\int_{\Gamma _\text{out}}\phi _{j}\phi _{i}\text{ d}s+\int_{\Gamma _\text{in}}\phi _{j}\phi _{i}\text{ d}sx \right)\Bigg]u_{h,i} &= 2ik \int_{\Gamma _{\text{in}}}\phi _{j}\text{ d}s \qquad\text{for }j=1,\dots,n
\end{align*}$$
which can be written as the linear system,
$$(K-k^{2}M+ik(B_{\text{in}}+B_{\text{out}}))\mathbf u=2ik\mathbf b_{\text{in}},$$
where
$$\begin{align*}
K_{ij}&= \int_{\Omega }\nabla \phi _{j}\cdot \nabla \phi _{i} \text{ d}\mathbf x, \qquad &M_{ij}&=  \int_{\Omega }\phi _{j}\phi _{i}\text{ d}\mathbf x,\\
(B_{\text{in}})_{ij}&= \int_{\Gamma _\text{in}} \phi _{j}\phi _{i}\text{ d}s, &(B_{\text{out}})_{ij}&=  \int_{\Gamma _{\text{out}} }\phi _{j}\phi _{i}\text{ d}s,\\
(\mathbf b_{\text{in}})_{j}&= \int_{\Gamma _{\text{in}}}\phi _{j}\text{ d}s.
\end{align*}$$
Notice that these are real matrices/vectors that do not depend on the wave number $k$.

![[Pasted image 20240402132412.png]]
$$\begin{align*}
H(\mathbf u)&= \mathbf u^{H}B_\text{out}\mathbf u\\
&= \sum_{j=1}^{n} \overline{u_{h,j}}\left(\sum_{i=1}^{n}\int_{\Gamma _{\text{out}}}\phi _{j}(\mathbf x)\phi _{i}(\mathbf x)\text{ d}s \cdot u_{h,i} \right)\\
&= \int_{\Gamma _\text{out}}\left(\sum_{j=1}^{n}\overline{u_{h,j}\phi_{j} (\mathbf x)} \right)\cdot \left(\sum_{i=1}^{n}u_{h,i}\phi_{i} (\mathbf x) \right)\text{ d}s\\
&= \int_{\Gamma _\text{out}}\overline{u_{h}(\mathbf x)}\cdot u_{h}(\mathbf x) \text{ d}s\\
	&= \int_{\Gamma _\text{out}}\lvert u_{h}(\mathbf x) \rvert^{2} \text{ d}s
\end{align*}$$


![[Pasted image 20240402132420.png]]
We simply need to check each of equations in the Helmholtz problem (1)-(4).
The first equation is
$$\begin{align*}
-\nabla^{2} u_{\text{exact}}-k^{2}u_{\text{exact}}\tag{1}&= 0 \qquad \text{in }\Omega ,\\
-(-ik)^{2}e^{-ikx}-k^{2}e^{-ikx}&= 0,\\
(k^{2}-k^{2})e^{-ikx}&= 0,
\end{align*}$$
which is clearly satisfied.
The wall boundary condition reads,
$$\mathbf n \cdot \nabla u_{\text{exact}}=0 \quad\text{on } \{ 0 \le x \le5, y=0 \text{ or }y=1\}\tag{2}.$$
The normal vector is $\mathbf n=(0,\pm 1)$ for the lower and upper boundary, respectively. 
On the bottom boundary we have,
$$\begin{align*}
\mathbf n \cdot  (\nabla u_{\text{exact}})(x,0)&= (0,1)\cdot (-ike^{-ikx},0)\\
&= 0,
\end{align*}$$
and the top boundary is similar,
$$\begin{align*}
\mathbf n \cdot  (\nabla u_{\text{exact}})(x,5)&= (0,-1)\cdot (-ike^{-ikx},0)\\
&= 0.
\end{align*}$$

The out-boundary condition is
$$\begin{align*}
\mathbf n \cdot \nabla u_{\text{exact}}+ik u_{\text{exact}}&= 0 \quad\text{on }\{x= 5,0\le y \le5\}\tag{3},\\
(1,0)\cdot (-ike^{-5ik},0)+ike^{-5ik}&= 0,\\
-ike^{-5ik}+ike^{-5ik}&= 0,
\end{align*}$$
which is satisfied.

The in-boundary condition is
$$\begin{align*}
\mathbf n \cdot \nabla u_{\text{exact}}+ik u_{\text{exact}}&= 2ik \quad\text{on }\{x= 0,0\le y \le5\},\tag{4}\\
(-1,0)\cdot (-ike^{-0\cdot ik},0)+ike^{-0\cdot ik}&= 2ik,\\
ik+ik&= 2ik,
\end{align*}$$
which is satisfied.

Since $u_\text{exact}=e^{-ikx}$ satisfies (1)-(4) for the domain (7)-(10), it is an exact solution to the Helmholtz problem.

![[Pasted image 20240402132426.png]]


![[Pasted image 20240402132433.png]]
$$\begin{align*}
K_{ij}&= \int_{\Omega }\nabla \phi _{j}\cdot \nabla \phi _{i} \text{ d}\mathbf x, \qquad &M_{ij}&=  \int_{\Omega }\phi _{j}\phi _{i}\text{ d}\mathbf x,\\
(B_{\text{in}})_{ij}&= \int_{\Gamma _\text{in}} \phi _{j}\phi _{i}\text{ d}s, &(B_{\text{out}})_{ij}&=  \int_{\Gamma _{\text{out}} }\phi _{j}\phi _{i}\text{ d}s,\\
(\mathbf b_{\text{in}})_{j}&= \int_{\Gamma _{\text{in}}}\phi _{j}\text{ d}s.
\end{align*}$$

For assembly, we will apply a stamping method. Consider an element $T^{k}$ with local nodes $\mathbf x_{1}^{k},\mathbf x_{2}^{k},\mathbf x_{3}^{k}$ and local basis functions $\mathcal{H}_{1}^{k},\mathcal{H}_{2}^{k},\mathcal{H}_{3}^{k}$, where $\mathcal{H}^{k}_{\alpha }=c_{\alpha }^{k}+c_{x,\alpha }^{k}x+ c_{y,\alpha }^{k}y$.
$$\begin{align*}
K^{k}_{\alpha \beta} &= \int_{T^{k}}\partial _{x}\mathcal{H^{k}_{\alpha }}\cdot \partial _{x}\mathcal{H^{k}_{\beta  }}+\partial _{y}\mathcal{H^{k}_{\alpha }}\cdot \partial _{y}\mathcal{H^{k}_{\beta  }}\text{ d}\mathbf x\\
&= \text{Area}^{k}(c_{x,\alpha }^{k}c_{x,\beta }^{k}+c_{y,\alpha }^{k}c_{y,\beta }^{k}).
\end{align*}$$

$$M_{\alpha \beta  }^{k}=\int_{T^{k}}\mathcal{H}_{\alpha }^{k}(\mathbf x) \cdot \mathcal{H}^{k}_{\beta }(\mathbf x)\text{ d}\mathbf x$$
Compute on reference triangle. no, use prob 4

![[Pasted image 20240402132439.png]]
should be second order

![[Pasted image 20240402132447.png]]

![[Pasted image 20240402132453.png]]

![[Pasted image 20240402132457.png]]

# Problem 4

![[Pasted image 20240402175556.png]]
See attached file.
![[Pasted image 20240402175603.png]]

I'm assuming that the RHS $f=1$.
Our Galerkin formulation is
$$\begin{align*}
\int_{\Omega }\left(\sum_{j=1}^{n}\hat u_{j}\nabla \phi _{j} \right)\cdot \nabla \phi _{i}\text{ d}\mathbf x&= \int_{\Omega } \phi _{i} \text{ d}\mathbf x,\\
A \mathbf u&= \mathbf b,
\end{align*}$$
with 
$$\begin{align*}
A_{ij}&= \int_{\Omega }\nabla \phi _{j}\cdot \nabla \phi _{i}\text{ d}\mathbf x\\
b_{i}&= \int_{\Omega }\phi _{i}\text{ d}x
\end{align*}$$
$$\mathcal{H}^{k}_{\alpha }=c_{\alpha }^{k}+c_{x,\alpha }^{k}x+ c_{y,\alpha }^{k}y+c_{xy,\alpha}^{k}xy+c_{x^{2},\alpha }^{k}x^{2}+c_{y^{2},\alpha}^{k}y^{2}$$
$$\begin{bmatrix}1 & x_{1}^{k} & y_{1}^{k} & x_{1}^{k}y_{1}^{k} & (x_{1}^{k})^{2} & (y_{1}^{k})^{2} \\ 1 & x_{2}^{k} & y_{2}^{k} & x_{2}^{k}y_{2}^{k} & (x_{2}^{k})^{2} & (y_{2}^{k})^{2} \\ 1 & x_{3}^{k} & y_{3}^{k} &x_{3}^{k}y_{3}^{k} &  (x_{3}^{k})^{2} & (y_{3}^{k})^{2} \\ 1 & x_{4}^{k} & y_{4}^{k} &x_{4}^{k}y_{4}^{k} &  (x_{4}^{k})^{2} & (y_{4}^{k})^{2} \\ 1 & x_{5}^{k} & y_{5}^{k} &x_{5}^{k}y_{5}^{k} &  (x_{5}^{k})^{2} & (y_{5}^{k})^{2} \\ 1 & x_{6}^{k} & y_{6}^{k} &x_{6}^{k}y_{6}^{k} &  (x_{6}^{k})^{2} & (y_{6}^{k})^{2}\end{bmatrix}
\begin{bmatrix}c_{1 }^{k} & c_{2}^{k} & c_{3}^{k} & c_{4}^{k} & c_{5}^{k} & c_{6}^{k} \\ c_{x,1 }^{k} & c_{x,2}^{k} & c_{x,3}^{k} & c_{x,4}^{k} & c_{x,5}^{k} & c_{x,6}^{k} \\ c_{y,1 }^{k} & c_{y,2}^{k} & c_{y,3}^{k} & c_{y,4}^{k} & c_{y,5}^{k} & c_{y,6}^{k} \\ c_{xy,1 }^{k} & c_{xy,2}^{k} & c_{xy,3}^{k} & c_{xy,4}^{k} & c_{xy,5}^{k} & c_{xy,6}^{k} \\ c_{x^{2},1 }^{k} & c_{x^{2},2}^{k} & c_{x^{2},3}^{k} & c_{x^{2},4}^{k} & c_{x^{2},5}^{k} & c_{x^{2},6}^{k} \\ c_{y^{2},1 }^{k} & c_{y^{2},2}^{k} & c_{y^{2},3}^{k} & c_{y^{2},4}^{k} & c_{y^{2},5}^{k} & c_{y^{2},6}^{k}\end{bmatrix}=I$$
Or that $C =V^{-1}$.
Now that we have the coefficients for the local basis functions, we can consider element-wise contriutions to $A$ and $b$. The elementary matrix for an element $T^{k}$ is
$$\begin{align*}
A^{k}_{\alpha \beta }&= \int_{T^{k}}\partial _{x}\mathcal{H}_{\alpha }^{k} \cdot \partial _{x}\mathcal{H^{k}_{\beta  }}+\partial _{y}\mathcal{H}^{k}_{\alpha }\cdot \partial _{y}\mathcal{H^{k}_{\beta  }}\text{ d}\mathbf x,\\
&= \int_{T^{k}}(c_{x,\alpha }^{k}+c_{xy,\alpha}^{k}y+2c_{x^{2},\alpha  }^{k}x)(c_{x,\beta }^{k}+c_{xy,\beta}^{k}y+2c_{x^{2},\beta }^{k}x)\\
&\qquad \quad  + (c_{y,\alpha }^{k}+c_{xy,\alpha}^{k}x+2c_{y^{2},\alpha  }^{k}y)(c_{y,\beta }^{k}+c_{xy,\beta}^{k}x+2c_{y^{2},\beta }^{k}y) \text{ d}\mathbf x,\\
&= :\int_{T^{k}}a_{\alpha \beta}(\mathbf x)\text{ d}\mathbf x,
\end{align*}$$
where we can use the quadrature rule 
![[Pasted image 20240405112128.png|800]]
to approximate the integral as
$$\begin{align*}
A_{\alpha \beta}^{k}&≈\frac{1}{3}A_{k}\sum_{i=1}^{3}a_{\alpha \beta}(\mathbf x_{i}^{g}) \quad\text{for }\alpha ,\beta =1,\dots,6.
\end{align*}$$
This is actually exact since the quadrature is second order accurate and $a_{\alpha \beta}(\mathbf x)\in \mathbb P_{2}(K)$.
The elementary load can be approximated similarly,
$$\begin{align*}
b_{\alpha }^{k}&= \int_{T^{k}}\mathcal{H^{k}_{\alpha }}(\mathbf x) \text{ d}\mathbf x\\
&≈ \frac{1}{3}A_{k}\sum_{i=1}^{3}\mathcal{H^{k}_{\alpha }}(\mathbf x_{i}^{g})
\end{align*}$$



![[Pasted image 20240402175610.png]]
third order