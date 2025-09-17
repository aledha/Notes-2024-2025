By Alexander Hatle
# Problem 1
![[Pasted image 20240118132809.png]]

We want to show that 
![[Pasted image 20240123134035.png|500]]
The 5-point Laplacian is

$$\nabla _{5}^{2}u_{ij}= \frac{1}{h^{2}}\left(u_{i,j-1}+u_{i,j+1}+u_{i+1,j}+u_{i-1,j}-4u_{ij}  \right),$$
and the 9-point Laplacian is
$$\begin{align*}
\nabla _{9}^{2}u_{ij} &= \frac{1}{6h^{2}} \big(4u_{i-1,j}+4u_{i+1,j}+4u_{i,j-1}+4u_{i,j+1} \\
&\quad + u_{i-1,j-1}+u_{i-1,j+1}+u_{i+1,j-1}+u_{i+1,j+1}-20u_{ij} \big).
\end{align*}$$
Following the hint, we can rewrite this in terms of the 5-point Laplacian plus a finite difference approximation,
$$\begin{align*}
	\nabla _{9}^{2}u_{ij}&= \nabla _{5}^{2}u_{ij}\\
&+ \frac{1}{6h^{2}} \big(u_{i-1,j-1}+u_{i-1,j+1}-2u_{i-1,j}\\
&\qquad \qquad +u_{i+1,j-1}+u_{i+1,j+1}-2u_{i+1,j}  \\
&\qquad \qquad -2(u_{i,j-1}+u_{i,j+1}-2u_{ij})  \big)
\end{align*}$$
Now, we can fix $i$ and use the Taylor expansion
$$u_{i,j\pm1}=u_{i,j} \pm h \partial _{y}u_{i}(y_{j})+\frac{1}{2}h^{2}\partial _{y}^{2}u_{i}(y_{j}) \pm \frac{1}{6}h^{3}\partial _{y}^{3}u_{i}(y_{j})+\mathcal{O}(h^{4})$$
on the first two terms in each of the three lines in the above equation to get
$$\nabla _{9}^{2}u_{ij}=\nabla _{5}^{2}u_{ij}+ \frac{1}{6h^{2}}\left(h^{2}\partial _{y}^{2}u_{i-1}(y_{j})+h^{2}\partial _{y}^{2}u_{i+1}(y_{j})-2h^{2}\partial _{y}^{2}u_{i}(y_{j})+\mathcal{O}(h^{4}) \right).$$
Using the same Taylor expansion on $i$ while fixing $j$ yields
$$\nabla _{9}^{2}u_{ij}=\nabla _{5}^{2}u_{ij}+ \frac{1}{6}\left(h^{2}\partial _{x}^{2}\partial _{y}^{2}u(x_{i},y_{i})+\mathcal{O}(h^{4}) \right).$$
The truncation error of the 5-point Laplacian is to be $\frac{1}{12}h^{2}(u_{xxxx}+u_{yyyy})+\mathcal{O}(h^{4})$. Inserting this into the above equation gives the truncation error of the 9-point Laplacian,
$$\tau _{ij}= \frac{1}{12}h^{2}(u_{xxxx}+2u_{xxyy}+u_{yyyy})+\mathcal{O}(h^{4}).$$

![[Pasted image 20240202194132.png]]
See attached file. My result:
![[Pasted image 20240202194153.png|500]]

<div style="page-break-after: always;"></div>

# Problem 2

![[Pasted image 20240123134127.png]]
A mapping from the original domain to the unit square is
$$\xi (x,y)= \frac{x}{\frac{B}{2}+\frac{A}{H}y}, \qquad \eta (x,y)= \frac{y}{H}$$
where $B, A,H>0$ are positive constants. The inverse mapping is
$$x(\xi ,\eta )= \left(\frac{B}{2}+A \eta \right)\xi ,\qquad y(\xi ,\eta )=H \eta .$$
The equation in the new domain becomes
$$- \frac{1}{J^{2}}(a u_{\xi \xi }-2bu_{\xi \eta }+cu_{\eta \eta} +du_{\eta }+eu_{\xi })=1,$$
where
$$\begin{align*}
&a=x_{\eta }^{2}+y_{\eta }^{2} ,\qquad b=x_{\xi }x_{\eta }+y_{\xi }y_{\eta },\qquad c=x_{\xi }^{2}+y_{\xi }^{2},\\
&	d=\frac{y_{\xi }\alpha -x_{\xi }\beta }{J},\qquad e=\frac{x_{\eta }\beta -y_{\eta }\alpha }{J},
\end{align*}$$
and 
$$\begin{align*}
\alpha &= ax_{\xi \xi }-2bx_{\xi \eta }+cx_{\eta \eta},\\
\beta &= ay_{\xi \xi }-2by_{\xi \eta }+cy_{\eta \eta},\\
J &= x_{\xi }y_{\eta }-x_{\eta }y_{\xi } 
\end{align*}$$
For our mapping, we have that $x_{\xi \xi }=x_{\eta \eta}=y_\xi =y_{\xi \xi}=y_{\eta \eta }=0$. The other partial derivatives are
$$x_{\xi }=\frac{B}{2}+A \eta ,\quad x_{\xi \eta }=A, \quad x_{\eta }=A \xi , \quad y_{\eta }=H.$$
The variables can be simplified to
$$\begin{align*}
&a=(A \xi )^{2}+H^{2} ,\qquad b=\left(\frac{B}{2}+A \eta  \right)A \xi  ,\qquad c=\left(\frac{B}{2}+A \eta  \right)^{2},\\
&	d=0,\qquad e=\frac{2AHb }{J},
\end{align*}$$
and 
$$\begin{align*}
\alpha &= -2Ab,\\
\beta &= 0,\\
J&= \frac{BH}{2}+AH \eta .
\end{align*}$$

The Dirichlet boundary condition is simply that $u=0$ on $\Gamma _{D}$, where $\Gamma _{D}=\{(\xi,\eta ):\{\xi =1 \}\cup \{\eta =0 \} \}$

For the Neumann boundary, we have the condition on the directional derivative $\partial _{\mathbf n}u=0$ on $\Gamma _{N}$, where $\Gamma _{N}=\{(\xi ,\eta ):\{\xi =0 \}\cup \{\eta =1 \} \}$. 
The normal derivative in the domain space can be expressed as
$$\partial _{\mathbf n}u=u_{x}n^{x}+u_{u}n^{y}=\frac{1}{J}\left[(y_{\eta }n^{x}-x_{\eta }n^{y})u_{\xi }+(-y_{\xi }n^{x}+x_{\xi }n^{y})u_{\eta } \right]$$
The normal vector on the top boundary has the normal vector in the physical space $\mathbf n=(n^{x},n^{y})=(0,1)$. The Neumann condition in $\hat \Omega$ is
$$\partial _{\mathbf n}u=\frac{1}{J}\left[-A \xi u_\xi +\left(\frac{B}{2}+A \eta  \right)u_{\eta }  \right]=0.$$

For the left boundary, the normal vector is $\mathbf n=(n^{x},n^{y})=(-1,0)$. The Neumann condition is
$$\partial _{\mathbf n}u= \frac{1}{J} \left[-H u_{\xi } \right]=0.$$

In conclusion, the PDE can be expressed in the new domain as
$$
\begin{align*}
- \frac{1}{J^{2}}(a u_{\xi \xi }-2bu_{\xi \eta }+cu_{\eta \eta} +eu_{\xi })&=  1  \qquad  \text{in }\hat \Omega, \\
u&= 0 \qquad \text{on }\xi =1 \text{ and }\eta =0,\\
-A \xi u_\xi +\left(\frac{B}{2}+A   \right)u_{\eta }&= 0\qquad \text{on } \eta =1,\\
u_{\xi }&= 0\qquad\text{on } \xi =0.
\end{align*}$$


![[Pasted image 20240123134209.png]]

Let's discretize the domain with $u_{ij}=u(\xi _{i},\eta _{j})=u (ih,jh)$. The partial derivatives can be approximated by central differences, and it can be shown by Taylor expansion that 
$$\begin{align*}
u_{\xi \xi }&= \frac{u_{i-1,j}-2u_{ij}+u_{i+1,j}}{h^{2}}-\frac{h^{2}}{12}u_{\xi \xi \xi \xi} +\mathcal{O}(h^{4}),\\
u_{\eta \eta }&= \frac{u_{i,j-1}-2u_{ij}+u_{i,j+1}}{h^{2}}-\frac{h^{2}}{12}u_{\eta \eta \eta \eta} +\mathcal{O}(h^{4}),\\
u_{\xi }&= \frac{u_{i+1,j}-u_{i-1,j}}{2h}-\frac{h^{2}}{6}u_{\xi \xi \xi } + \mathcal{O}(h^{4}).
\end{align*}$$
A second order mixed derivative can be obtained by applying central differences in the $\eta$-direction on the last line,
$$u_{\xi \eta } = \frac{(u_{i+1,j+1}-u_{i+1,j-1})-(u_{i-1,j+1}-u_{i-1,j-1})}{(2h)^{2}}+ \tau_{ij}.$$
Let's Taylor expand first in the $\eta$-direction, and then in the $\xi$-direction
$$\begin{align*}
u_{i +1,j \pm 1}&= u(\xi + h,\eta  \pm h)\\
	&= u(\xi +h,\eta )\pm hu_{\eta }(\xi +h,\eta ) +\frac{h^{2}}{2}u_{\eta \eta}(\xi +h, \eta ) + \frac{h^{3}}{6}u_{\eta \eta \eta}(\xi +h,\eta )+\mathcal{O}(h^{4})\\
	&= u +hu_{\xi }+\frac{h^{2}}{2}u_{\xi \xi}+\frac{h^{3}}{6}u_{\xi \xi \xi}  \\
&\quad \pm \text{ } h \left(u_{\eta } + h u_{\eta \xi } + \frac{h^{2}}{2} u_{\eta \xi \xi} \right)\\
&\quad + \frac{h^{2}}{2}\left(u_{\eta \eta} +hu_{\eta \eta \xi }  \right)\\
&\quad \pm \frac{h^{3}}{6}\left(u_{\eta \eta \eta }\right) + \mathcal{O}(h^{4}),
\end{align*}$$
where every term with $h^{4}$ or higher is collected in the $\mathcal{O}(h^{4})$ term. The difference between these two is
$$u_{i+1,j+1}-u_{i+1,j-1}=2h \left(u_{\eta }+hu_{\eta \xi }+\frac{h^{2}}{2} u_{\eta \xi \xi} \right)+\frac{h^{3}}{3}u_{\eta \eta \eta }+\mathcal{O}(h^{4})$$

Similarly, we have 
$$\begin{align*}
u_{i-1,j\pm1}&= u -hu_{\xi }+\frac{h^{2}}{2}u_{\xi \xi} - \frac{h^{3}}{6}u_{\xi \xi \xi}\\
&\quad \pm \text{ } h \left(u_{\eta } - h u_{\eta \xi } + \frac{h^{2}}{2} u_{\eta \xi \xi} \right)\\
&\quad + \frac{h^{2}}{2}\left(u_{\eta \eta} -hu_{\eta \eta \xi } \right)\\
	&\quad \pm \frac{h^{3}}{6}u_{\eta \eta \eta } +\mathcal{O}(h^{4}).
\end{align*}$$
Where the difference is
$$u_{i-1,j+1}-u_{i-1,j-1}=2h \left(u_{\eta } - h u_{\eta \xi } + \frac{h^{2}}{2} u_{\eta \xi \xi} \right) + \frac{h^{3}}{3}u_{\eta \eta \eta }+\mathcal{O}(h^{4})$$
Finally, we obtain that
$$\frac{(u_{i+1,j+1}-u_{i+1,j-1})-(u_{i-1,j+1}-u_{i-1,j-1})}{(2h)^{2}}=\frac{4h^{2}u_{\eta \xi} +\mathcal{O}(h^{4})}{4h^{2}}=u_{\eta \xi }+\mathcal{O}(h^{2}),$$
and that the truncation error is $\tau _{ij}=\mathcal{O}(h^{2})$.


The interior of the domain can be described by the scheme
$$\begin{align*}
- \frac{1}{J^{2}}\Bigg[a_{ij} \left(\frac{u_{i-1,j}-2u_{ij}+u_{i+1,j}}{h^{2}} \right) -2b_{ij} \left(\frac{(u_{i+1,j+1}-u_{i+1,j-1})-(u_{i-1,j+1}-u_{i-1,j-1})}{(2h)^{2}} \right) + \\
c_{ij} \left(\frac{u_{i,j+1}-2u_{ij}+u_{i,j-1}}{h^{2}} \right) + e_{ij} \left(\frac{u_{i+1,j}-u_{i-1,j}}{2h} \right)\Bigg]=1
\end{align*}$$
Collecting terms,
$$\begin{align*}
(-2a_{ij}-2c_{ij})u_{ij}+\left(a_{ij}-\frac{h}{2}e_{ij}\right)u_{i-1,j}+\left(a_{ij}+\frac{h}{2}e_{ij}\right)u_{i+1,j}+\\
c_{ij}u_{i,j+1}+c_{ij}u_{i,j-1}-\frac{b_{ij}}{2}u_{i+1,j+1}+\frac{b_{ij}}{2}u_{i+1,j-1}+\frac{b_{ij}}{2}u_{i-1,j+1}-\frac{b_{ij}}{2}u_{i-1,j-1}=-(Jh)^{2}.
\end{align*}$$
The Neumann boundary condition on $\{\xi =0 \}$ can be approximated with
$$u_\xi ≈\frac{1}{h}\left(-\frac{3}{2}u_{1,j}+2u_{2,j}- \frac{1}{2}u_{3,j} \right)=0$$
To show that this is $\mathcal{O}(h^{2})$, we will use Taylor expansions centered at $i=1$,
$$\begin{align*}
u_{2,j}&= u+hu_{\xi }+ \frac{h^{2}}{2}u_{\xi \xi }+\mathcal{O}(h^{3}),\\
u_{3,j}&= u+2hu_{\xi }+2h^{2}u_{\xi \xi }+\mathcal{O}(h^{3}),
\end{align*}$$
and see that 
$$\begin{align*}
\frac{1}{h}\left(-\frac{3}{2}u_{0,j}+2u_{1,j}- \frac{1}{2}u_{2,j} \right)&= \frac{1}{h}\left(2\left(hu_{\xi }+\frac{h^{2}}{2}u_{\xi \xi }\right)- \frac{1}{2}\left(2hu_{\xi }+2h^{2}u_{\xi \xi } \right) \right) +\mathcal{O}(h^{2}),\\
&= u_{\xi }+\mathcal{O}(h^{2}),
\end{align*}$$
i.e., that this approximation is second order accurate.

The Neumann condition on $\{\eta =1 \}$ is similar. For the $u_\xi$ term we can simply use a central difference approximation. For $u_\eta$ we can use
$$u_{\eta }=\frac{1}{h}\left(\frac{3}{2}u_{i,n+1} - 2u_{i,n}+ \frac{1}{2} u_{i,n-1}\right)+ \tau _{i,n+1}.$$
Taylor expanding around $j=n+1,$
$$\begin{align*}
u_{i,n}&= u-hu_{\eta  }+ \frac{h^{2}}{2}u_{\eta \eta }+\mathcal{O}(h^{3}),\\
u_{i,n-1}&= u-2hu_{\eta  }+2h^{2}u_{\eta \eta }+\mathcal{O}(h^{3}),
\end{align*}$$
such that 
$$\begin{align*}
\tau _{ij}&= \frac{1}{h}\left(-2\left(-hu_{\eta }+ \frac{h^{2}}{2}u_{\eta \eta}\right)+ \frac{1}{2}(-2hu_{\eta }+2h^{2}u_{\eta \eta}) \right)+\mathcal{O}(h^{2})-u_{\eta }\\
\tau _{ij}&=\mathcal{O}(h^{2}).
\end{align*}$$
The scheme at the top boundary is therefore
$$\begin{align*}
-A \xi u_\xi +\left(\frac{B}{2}+A  \right)u_{\eta }&= 0,\\
≈-A \xi _{i}\frac{u_{i+1,n+1}-u_{i-1,n+1}}{2h}+ \left(\frac{B}{2}+A \right) \frac{1}{h} \left(\frac{3}{2}u_{i,n+1}-2u_{i,n}+\frac{1}{2}u_{i,n-1} \right)&= 0.
\end{align*}$$
![[Pasted image 20240202193540.png]]
See attached Julia file. Here is my result:
![[Pasted image 20240202193905.png|500]]

![[Pasted image 20240202193950.png]]
See attached Julia file. My result:
![[Pasted image 20240202194033.png|800]]

<div style="page-break-after: always;"></div>

# Problem 3

![[Pasted image 20240123134225.png]]
The method described can be written as
$$\frac{u(x,t+k)-u(x,t)}{k}=\frac{u(x-h,t)-2u(x,t)+u(x+h,t)+u(x-h,t+k)-2u(x,t+k)+u(x+h,t+k)}{2h^{2}}- \gamma ((1-\theta )u(x,t)+\theta u(x,t+k))$$
Taylor expansions:
$$\begin{align*}
	u(x,t+k)&= u+ku_{t}+ \frac{1}{2}k^{2}u_{tt} + \mathcal{O}(k^{3})\\
	u(x\pm h,t)&= u \pm hu_{x}+ \frac{1}{2}h^{2}u_{xx} \pm \frac{1}{6}h^{3}u_{xxx} + \mathcal{O}(h^{4})\\
u(x \pm h,t+k)&= u(x,t+k)\pm h u_{x}(x,t+k)+ \frac{1}{2}h^{2}u_{xx}(x,t+k)\pm  \frac{1}{6}h^{3}u_{xxx}(x,t+k) +\mathcal{O}(h^{4})
\end{align*}$$
Applying these expansions to the equation above,
$$\frac{ku_{t}(x,t)+ \frac{1}{2}k^{2}u_{tt}(x,t)+\mathcal{O}(k^{3})}{k}=  \kappa \cdot \frac{h^{2}u_{xx}(x,t) +h^{2}u_{xx}(x,t+k)+ \mathcal{O}(h^{4})}{2h^{2}}-\gamma \left[(1-\theta )u(x,t)+\theta \left(u(x,t)+ku_{t}(x,t)+\mathcal{O}(k^{2})\right) \right]$$
Using that $\partial _{x}^{2}(u(x,t+k))=\partial _{x}^{2}(u(x,t)+k \partial_{t}u(x,t)+ \mathcal{O}(k^{2})),$
$$u_{t}+ \frac{k}{2}u_{tt}= \frac{\kappa }{2}\left(2u_{xx} +ku_{xxt}+\mathcal{O}(k^{2})\right)+\mathcal{O}(h^{2})- \gamma \left[u+\theta k u_{t}  \right]+\mathcal{O}(k^{2}).$$
Since $u_{xx}= \frac{u_{t}+\gamma u}{\kappa }$, 
$$\begin{align*}
u_{t}+ \frac{k}{2}u_{tt}&=\kappa u_{xx}+ \frac{k \kappa }{2}\left(\frac{u_{tt}+\gamma u_{t}}{\kappa } \right)-\gamma u-\gamma \theta ku_{t}+\mathcal{O}(h^{2})+\mathcal{O}(k^{2})\\
u_{t}&= \kappa u_{xx} - \gamma u +\left(\frac{1}{2}-\theta  \right)\gamma k u_{t}+ \mathcal{O}(h^{2}+k^{2}).
\end{align*}$$
Observe that if $\theta = \frac{1}{2}$, the last term involving vanishes, and we get a $\mathcal{O}(h^{2}+k^{2})$ truncation error. Otherwise, we introduce on $\mathcal{O}(k)$ error and the local truncation error becomes $\mathcal{O}(h^{2}+k)$.
