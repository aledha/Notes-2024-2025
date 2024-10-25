Alexander Hatle
![[Pasted image 20241014142841.png|800]]
$$T_{ik,k} +\rho b_{i}=\rho a_{i}\tag{2.89}$$
$$\begin{aligned}
\mathbf T&= -p \mathbf I\\
T_{ij}&= -p \delta _{ij}
\end{aligned} \tag{2.86}$$
Then, $(2.89)$ becomes
$$\begin{aligned}
\frac{\partial }{\partial x_{k}}(-p \delta _{ik})+\rho b_{i}&= \rho a_{i}\\
-\frac{\partial p}{\partial x_{k}}\delta _{ik}+\rho b_{i}&= \rho a_{i}
\end{aligned}$$
Since the body is at rest, $a_{i}=0$, so
$$-\frac{\partial p}{\partial x_{k}}\delta _{ik}+b_{i} g= 0.$$
Denote $x_{1}=z$ as the height. If we assume that the pressure is constant at a given height $z$, then $\frac{\partial p}{\partial x_{2}}=\frac{\partial p}{\partial x_{3}}=0$. Taking the above equation for $k=1$, and using that $b_{1}=g$ gives
$$\begin{aligned}
-\frac{\partial p}{\partial z}+\rho g&= 0\\
\frac{\partial p}{\partial z}&= \rho g\\
p(z)&= p_{0}+z \rho g.
\end{aligned}$$

![[Pasted image 20241014153535.png|800]]
$$p_{0}=p(z)+z \rho g$$
Using the given values,
$$\begin{aligned}
p_{0}&= p(1.2\text{ m})+1.2 \text{ m}\cdot 1000 \,\mathrm{kgm^{-3}}\cdot 9.81 \, \mathrm{ ms^{-2}}\\
p_{0}&= p(1.2 \text{ m})+11772 \, \mathrm{ kgm^{-1}s^{-2}}\\
p_{0}&= p(1.2 \text{ m})+ 11.772 \text{ kPa}.
\end{aligned}$$
Now we can estimate the pressure in the veins as
$$\begin{aligned}
p_{v,0}&= p_{vh}+11.772\text{ kPa}\\
&=1\text{ kPa} + 11.772 \text{ kPa}\\
&= 12.772 \text{ kPa},\\
p_{a,0}&= p_{ah}+ 11.772 \text{ kPa}\\
&= 10 \text{ kPa}+11.772 \text{ kPa}\\
&= 21.772 \text{ kPa}.
\end{aligned}$$
---

![[Pasted image 20241014154648.png|800]]
Assuming that $\epsilon _{2}=\epsilon _{3}=-\frac{\sigma _{1}\nu }{\eta }$.

From the $x_{i},x_{j}$ and $x_{k}$ directions, we get the strain contributions
$$\epsilon _{i}= \frac{\sigma _{i}}{\eta }-\frac{\sigma _{j}\nu }{\eta }-\frac{\sigma _{k}\nu }{\eta },$$
for $i≠j≠k$. We can rewrite it as
$$\begin{aligned}
\epsilon _{i}&=  \frac{\sigma _{i}}{\eta }+\frac{\sigma _{i}\nu }{\eta }-\frac{\sigma _{i}\nu }{\eta }-\frac{\sigma _{j}\nu }{\eta }-\frac{\sigma _{k}\nu }{\eta }\\
&= \frac{1+\nu }{\eta }\sigma _{i}-\frac{\nu }{\eta }(\sigma _{i}+\sigma _{j}+\sigma _{k})\\
&= \frac{1+\nu }{\eta }\sigma _{i}-\frac{\nu }{\eta }\text{tr } \mathbf T.
\end{aligned}$$
![[Pasted image 20241014163549.png|800]]
We have
$$\begin{aligned}
E_{ii}&= \epsilon _{i}\\
&= \frac{1+\nu }{\eta }\sigma _{i}-\frac{\nu }{\eta }\text{tr } \mathbf T\\
&= \frac{1+\nu }{\eta }T_{ii}-\frac{\nu }{\eta }\text{tr } \mathbf T,
\end{aligned}$$
and 
$$E_{ij}=\frac{1+\nu }{\eta }T_{ij},\quad\text{for }i≠j.$$
As $\frac{1+\nu }{\eta }$ is the same for both expressions, and $\frac{\nu }{\eta }\text{tr }T$ does not depend on the index, we can write the whole expression as
$$\mathbf E= \frac{1+\nu }{\eta }\mathbf T-\frac{\nu }{\eta }\text{tr}(\mathbf T) \mathbf I,$$
or in index notation as
$$E_{ij}=\frac{1+\nu }{\eta }T_{ij}-\frac{\nu }{\eta }T_{kk}\delta _{ij}.$$
![[Pasted image 20241014164810.png|800]]
$$T_{ij}=\frac{\eta }{1+\nu }\left(E_{ij}+\frac{\nu }{1-2\nu }E_{kk}\delta _{ij} \right)\tag{4}$$

Using the result from the previous task,
$$\begin{aligned}
E_{ij}&= \frac{1+\nu }{\eta }T_{ij}-\frac{\nu }{\eta }T_{kk}\delta _{ij}\\
E_{ij}+\frac{\nu }{\eta }T_{kk}\delta _{ij}&= \frac{1+\nu }{\eta }T_{ij}\\
T_{ij}&= \frac{\eta }{1+\nu }\left(E_{ij}+\frac{\nu }{\eta }T_{kk}\delta _{ij} \right)\\
T_{ij}&= \frac{\eta }{1+\nu }\left(E_{ij}+\frac{\nu }{\eta }(T_{11}+T_{22})\delta _{ij} \right).
\end{aligned}$$

$$\begin{aligned}
E_{11}&= \frac{1+\nu }{\eta }T_{11}-\frac{\nu }{\eta }(T_{11}+T_{22})\\
E_{11}+E_{22}&= \frac{1+\nu }{\eta }(T_{11}+T_{22})-\frac{2\nu }{\eta }(T_{11}+T_{22})\\
&= \frac{1-\nu }{\eta }(T_{11}+T_{22})\\
T_{11}+T_{22}&= \frac{\eta }{1-\nu }(E_{11}+E_{22})
\end{aligned}$$

Then,
$$\begin{aligned}
T_{ij}&= \frac{\eta }{1+\nu }\left(E_{ij}+\frac{\nu}{\eta }\frac{\eta }{1-\nu }(E_{11}+E_{22}) \right)\\
&= \frac{\eta }{1+\nu }\left(E_{ij}+\frac{\nu }{1-\nu } (E_{11}+E_{22})\right)\\
T_{\alpha \beta}&= \frac{\eta }{1+\nu }\left(E_{\alpha \beta}+\frac{\nu }{1-\nu } E_{\rho \rho }\right)
\end{aligned}$$

---
![[Pasted image 20241019221251.png|800]]
Using equation $(4)$,
$$\begin{aligned}
T_{ij}&= \frac{\eta }{1+\nu }\left(E_{ij}+\frac{\nu }{1-2\nu }E_{kk}\delta _{ij} \right)\\
T_{ij,j}&= \frac{\eta }{1+\nu }\left(E_{ij,j}+\frac{\nu }{1-2\nu }E_{kk,j}\delta _{ij} \right).
\end{aligned}$$
Substituting into the Cauchy equations, we get
$$\begin{aligned}
\frac{\eta }{1+\nu }\left(E_{ij,j}+\frac{\nu }{1-2\nu }E_{kk,j}\delta _{ij} \right)+ \rho b_{i}&= \rho \ddot u_{i}\\
\frac{\eta }{1+\nu }\left(\frac{1}{2}(u_{i,j}+u_{j,i})_{j}+\frac{\nu }{1-2\nu }\frac{1}{2}(u_{k,k}+u_{k,k})_{j}\delta _{ij} \right)+ \rho b_{i}&= \rho \ddot u_{i}\\
\frac{\eta }{1+\nu }\left(\frac{1}{2}(u_{i,jj}+u_{j,ij})+\frac{\nu }{1-2\nu }u_{k,kj}\delta _{ij} \right)+ \rho b_{i}&= \rho \ddot u_{i}\\
\frac{\eta }{1+\nu }\left(\frac{1}{2}(u_{i,jj}+u_{j,ij})+\frac{\nu }{1-2\nu }u_{k,kj}\delta _{ij} \right)&= \rho (\ddot u_{i}-b_{i})\\
\frac{1}{2}(u_{i,jj}+u_{j,ij})+\frac{\nu }{1-2\nu }u_{k,kj}\delta _{ij} &= \frac{1+\nu }{\eta }\rho (\ddot u_{i}-b_{i})\\
\frac{1}{2}(u_{i,jj}+u_{j,ij})+\frac{\nu }{1-2\nu }u_{k,ki} &= \frac{1+\nu }{\eta }\rho (\ddot u_{i}-b_{i})\\
\frac{1}{2}(u_{i,jj}+u_{j,ij})+\frac{\nu }{1-2\nu }u_{j,ji} &= \frac{1+\nu }{\eta }\rho (\ddot u_{i}-b_{i})\\
u_{i,jj}+u_{j,ij}+\frac{2\nu }{1-2\nu }u_{j,ji} &= \frac{2+2\nu }{\eta }\rho (\ddot u_{i}-b_{i})\\
u_{i,jj}+\frac{1-2\nu +2\nu }{1-2\nu }u_{j,ji} &= \frac{2+2\nu }{\eta }\rho (\ddot u_{i}-b_{i})\\
u_{i,jj}+\frac{1 }{1-2\nu }u_{j,ji} &= \frac{2+2\nu }{\eta }\rho (\ddot u_{i}-b_{i})
\end{aligned}$$



---
![[Pasted image 20241015154535.png|800]]
Stress power is deformation work per unit time. In an elastic material, the energy is stored in the deformation of the material, while in inelastic materials, it may be partly transferred into heat energy. Equation (4.73) from the compendium says that
$$\omega =T_{ij}D_{ij} \tag{4.73}$$
![[Pasted image 20241015155421.png|800]]
Using equation (4.73),
$$\omega =\frac{\partial \phi }{\partial E_{ij}}D_{ij},$$
where $\dot {\mathbf E}=\mathbf D$, so
$$\omega = \frac{\partial \phi }{\partial E_{ij}}\dot E_{ij}$$


![[Pasted image 20241016132055.png|800]]
The first Piola-Kirchoff stress $\mathbf T_{0}$ is can be related to the Cauchy stress tensor $\mathbf T$ as
$$\mathbf T_{0}=J \mathbf T \mathbf F^{-T},\tag{4.98}$$
where $J=\det \mathbf F$.
The second Piola-Kirchoff stress tensor $\mathbf S$ can be related as
$$\begin{aligned}
\mathbf S&= \mathbf F^{-1}\mathbf T_{0}\\
&= J\mathbf F^{-1} \mathbf T \mathbf F^{-T}\\
\end{aligned}\tag{4.99}$$

![[Pasted image 20241016132104.png|800]]
$$\begin{aligned}
\mathbf S^{T}&= \left(J \mathbf F^{-1}\mathbf T \mathbf F^{-T} \right)^{T}\\
&= J \mathbf F^{-1}\mathbf T^{T}\mathbf F^{-T}\\
&= J\mathbf F^{-1}\mathbf T\mathbf F^{-T}\\
&= \mathbf S.
\end{aligned}$$
