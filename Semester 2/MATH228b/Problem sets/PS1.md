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


![[Pasted image 20240123134209.png]]

# Problem 3
![[Pasted image 20240123134225.png]]