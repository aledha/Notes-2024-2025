# Problem 1
![[Pasted image 20240118132809.png]]

![[Pasted image 20240123133855.png]]
Show that
![[Pasted image 20240123134035.png]]

$$\nabla _{5}^{2}u_{ij}= \frac{1}{h^{2}}\left(u_{i,j-1}+u_{i,j+1}+u_{i+1,j}+u_{i-1,j}-4u_{ij}  \right)$$

  $$\begin{align*}
\nabla _{9}^{2}u_{ij} &= \frac{1}{6h^{2}} \big(4u_{i-1,j}+4u_{i+1,j}+4u_{i,j-1}+4u_{i,j+1} \\
&\quad + u_{i-1,j-1}+u_{i-1,j+1}+u_{i+1,j-1}+u_{i+1,j+1}-20u_{ij} \big)
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
on the first two terms in each of the three lines in (???) to get
$$\nabla _{9}^{2}u_{ij}=\nabla _{5}^{2}u_{ij}+ \frac{1}{6h^{2}}\left(h^{2}\partial _{y}^{2}u_{i-1}(y_{j})+h^{2}\partial _{y}^{2}u_{i+1}(y_{j})-2h^{2}\partial _{y}^{2}u_{i}(y_{j})+\mathcal{O}(h^{4}) \right).$$
Using the same Taylor expansion on $i$ while fixing $j$ yields
$$\nabla _{9}^{2}u_{ij}=\nabla _{5}^{2}u_{ij}+ \frac{1}{6}\left(h^{2}\partial _{x}^{2}\partial _{y}^{2}u(x_{i},y_{i})+\mathcal{O}(h^{4}) \right).$$
The truncation error of the 5-point Laplacian is to be $\frac{1}{12}h^{2}(u_{xxxx}+u_{yyyy})+\mathcal{O}(h^{4})$. Inserting this into the above equation gives the truncation error of the 9-point Laplacian,
$$\tau _{ij}= \frac{1}{12}h^{2}(u_{xxxx}+2u_{xxyy}+u_{yyyy})+\mathcal{O}(h^{4}).$$


# Problem 2
![[Pasted image 20240123134127.png]]

$$\xi (x,y)= \frac{x}{C+\frac{A}{H}y}, \qquad \eta (x,y)= \frac{y}{H}$$
where $C, A,H>0$ are positive constants.
We wish to rewrite the PDE $u_{xx}+u_{yy}=1$ in the new domain. Using the chain rule, we find
$$\begin{align*}
u_{x}&= \xi _{x}u_{\xi }+\eta _{x} u_{\eta }\\
u_{xx}&= \xi _{xx}u_{\xi }+\xi _{x}(\xi _{x}u_{\xi \xi }+\eta _{x}u_{\xi \eta })+\eta _{xx}u_{\eta }+\eta _{x}(\xi _{x} u_{\eta \xi }+\eta _{x}u_{\eta \eta })\\
u_{yy}&= \xi _{yy}u_{\xi }+\xi _{y} (\xi _{y}u_{\xi \xi }+\eta _{y}u_{\xi \eta })+\eta _{yy}u_{\eta }+\eta _{y}(\xi _{y} u_{\eta \xi }+\eta _{y}u_{\eta \eta }).
\end{align*}$$
The terms $\xi _{xx},\eta _{x},\eta _{xx},\eta _{yy}$ are zero so our PDE is
$$\begin{align*}
\xi _{xx}u_{\xi }+ (\xi _{x})^{2}u_{\xi \xi }+\xi _{yy}u_{\xi }+(\xi _{y})^{2}u_{\xi \xi }+\xi _{y}\eta _{y}u_{\xi \eta }+ \eta _{y}\xi _{y}u_{\eta \xi }+(\eta _{y})^{2}u_{\eta \eta}&= 1\\
(\xi _{xx}+\xi _{yy})u_{\xi }+ ((\xi _{x})^{2}+(\xi _{y})^{2})u_{\xi \xi }+2\xi _{y}\eta _{y}u_{\xi \eta }+(\eta _{y})^{2}u_{\eta \eta}&= 1
\end{align*}$$




$$x(\xi ,\eta )= \left(\frac{B}{2}+A \eta \right)\xi ,\qquad y(\xi ,\eta )=H \eta $$


$$- \frac{1}{J^{2}}(a u_{\xi \xi }-2bu_{\xi \eta }+cu_{\eta \eta} +du_{\eta }+eu_{\xi })=1,$$
where
$$\begin{align*}
&a=x_{\eta }^{2}+y_{\eta }^{2} ,\qquad b=x_{\xi }x_{\eta }+y_{\xi }y_{\eta },\qquad c=x_{\xi }^{2}+y_{\xi }^{2},\\
&	d=\frac{y_{\xi }\alpha -x_{\xi }\beta }{J},\qquad e=\frac{x_{\eta }\beta -y_{\eta }\alpha }{J},
\end{align*}$$
and 
$$\begin{align*}
\alpha &= ax_{\xi \xi }-2bx_{\xi \eta }+cx_{\eta \eta},\\
\beta &= ay_{\xi \xi }-2by_{\xi \eta }+cy_{\eta \eta}.
\end{align*}$$
For our problem, we have that $x_{\xi \xi }=x_{\eta \eta}=y_\xi =y_{\xi \xi}=y_{\eta \eta }=0$. The other partial derivatives are
$$x_{\xi }=\frac{B}{2}+A \eta ,\quad x_{\xi \eta }=A, \quad x_{\eta }=A \xi , \quad y_{\eta }=H.$$
Our variables are thus simplified to
$$\begin{align*}
&a=(A \xi )^{2}+H^{2} ,\qquad b=\left(\frac{B}{2}+A \eta  \right)A \xi  ,\qquad c=\left(\frac{B}{2}+A \eta  \right)^{2},\\
&	d=0,\qquad e=\frac{2AH }{J},
\end{align*}$$
and 
$$\begin{align*}
\alpha &= -2A,\\
\beta &= 0.
\end{align*}$$

The Dirichlet boundary condition is simply that $u=0$ on $\Gamma _{D}$, where $\Gamma _{D}=\{(\xi,\eta ):\{\xi =1 \}\cup \{\eta =0 \} \}$

For the Neumann boundary, we have the condition on the directional derivative $\partial _{\mathbf n}u=0$ on $\Gamma _{N}$, where $\Gamma _{N}=\{(\xi ,\eta ):\{\xi =0 \}\cup \{\eta =1 \} \}$. 


$$\mathbf n=(n^{x},n^{y})=\frac{1}{\sqrt{\eta _{x}^{2}+\eta _{y}^{2}}}(\eta _{x},\eta _{y})$$

$$\partial _{\mathbf n}u=u_{x}n^{x}+u_{u}n^{y}=\frac{1}{J}\left[(y_{\eta }n^{x}-x_{\eta }n^{y})u_{\xi }+(-y_{\xi }n^{x}+x_{\xi }n^{y})u_{\eta } \right]$$
The normal vector on the top boundary has the normal vector in the physical space $\mathbf n=(n^{x},n^{y})=(0,1)$. The Neumann condition in $\hat \Omega$ can be written as
$$\partial _{\mathbf n}u=\frac{1}{J}\left[-A \xi u_\xi +\left(\frac{B}{2}+A \eta  \right)u_{\eta }  \right]=0$$

For the left boundary, the normal vector is $\mathbf n=(n^{x},n^{y})=(-1,0)$. The Neumann condition can be written as
$$\partial _{\mathbf n}u= \frac{1}{J} \left[-H u_{\xi } \right]=0$$

In conclusion, the PDE can be expressed in the transferred domain as
$$
\begin{align*}
- \frac{1}{J^{2}}(a u_{\xi \xi }-2bu_{\xi \eta }+cu_{\eta \eta} +eu_{\xi })&=  1  \qquad  \text{in }\hat \Omega \\
u&= 0 \qquad \text{on }\xi =1 \text{ and }\eta =0\\
-A \xi u_\xi +\left(\frac{B}{2}+A \eta  \right)u_{\eta }&= 0\qquad \text{on } \eta =1\\
u_{\xi }&= 0\qquad\text{on } \xi =0
\end{align*}$$


![[Pasted image 20240123134209.png]]

Let's discretize the domain with $u_{ij}=u(\xi _{i},\eta _{j})=u (i/n,j/n)$. The partial derivatives can be approximated by central differences, and it can be shown by Taylor expansion that 
$$\begin{align*}
u_{\xi \xi }&= \frac{u_{i-1,j}-2u_{ij}+u_{i+1,j}}{h^{2}}-\frac{h^{2}}{12}u_{\xi \xi \xi \xi} +\mathcal{O}(h^{4}),\\
u_{\eta \eta }&= \frac{u_{i,j-1}-2u_{ij}+u_{i,j+1}}{h^{2}}-\frac{h^{2}}{12}u_{\eta \eta \eta \eta} +\mathcal{O}(h^{4}),\\
u_{\xi }&= \frac{u_{i+1,j}-u_{i-1,j}}{2h}-\frac{h^{2}}{6}u_{\xi \xi \xi } + \mathcal{O}(h^{4}).
\end{align*}$$
The mixed derivative can be obtained by applying central derivatives to the last term,
$$u_{\xi \eta } = \frac{(u_{i+1,j+1}-u_{i+1,j-1})-(u_{i-1,j+1}-u_{i-1,j-1})}{(2h)^{2}}+ \tau_{ij}.$$
Let's Taylor expand first in the $\eta$-direction, and then in the $\xi$-direction
$$\begin{align*}
u_{i +1,j \pm 1}&= u(\xi + h,\eta  \pm h)\\
	&= u(\xi +h,\eta )\pm hu_{\eta }(\xi +h,\eta ) +\frac{h^{2}}{2}u_{\eta \eta}(\xi +h, \eta ) + \mathcal{O}(h^{3})\\
	&= u +hu_{\xi }+\frac{h^{2}}{2}u_{\xi \xi}\\
&\quad \pm \text{ } h \left(u_{\eta } + h u_{\eta \xi } + \frac{h^{2}}{2} u_{\eta \xi \xi} \right)\\
&\quad + \frac{h^{2}}{2}\left(u_{\eta \eta} +hu_{\eta \eta \xi }  + \frac{h^{2}}{2} u_{\eta \eta \xi \xi }\right).
\end{align*}$$
Similarly, we have 
$$\begin{align*}
u_{i-1,j\pm1}&= u -hu_{\xi }+\frac{h^{2}}{2}u_{\xi \xi} - \frac{h^{3}}{6}u_{\xi \xi \xi}\\
&\quad \pm \text{ } h \left(u_{\eta } - h u_{\eta \xi } + \frac{h^{2}}{2} u_{\eta \xi \xi}- \frac{h^{3}}{6}u_{\eta \xi \xi \xi} \right)\\
&\quad + \frac{h^{2}}{2}\left(u_{\eta \eta} -hu_{\eta \eta \xi }  + \frac{h^{2}}{2} u_{\eta \eta \xi \xi } - \frac{h^{3}}{6}u_{\eta \xi \xi \xi}\right)
\end{align*}$$



The interior of the domain can be described by the scheme

$$- \frac{1}{J^{2}}\left[a_{ij} \left(\frac{u_{i-1,j}-2u_{ij}+u_{i+1,j}}{h^{2}} \right) -2b \partial _{\xi }\left(\frac{u_{i,j+1}-u_{i,j-1}}{2h} \right) +\right]$$

# Problem 3
![[Pasted image 20240123134225.png]]

$$\frac{1}{k}D_{t}^{+}U_{j}^{n}= \frac{\kappa }{2}(D_{x}^{2}U_{j}^{n}+D_{x}^{2}U_{j}^{n+1})-\gamma \left[(1-\theta )U_{j}^{n}+\theta U_{j}^{n+1} \right]$$

$$\frac{u(x,t+k)-u(x,t)}{k}= \frac{u(x-h,t)-2u(x,t)+u(x+h,t)+u(x-h,t+k)-2u(x,t+k)+u(x+h,t+k)}{2h^{2}}- \gamma ((1-\theta )u(x,t)+\theta u(x,t+k))$$
