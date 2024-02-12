By Alexander Hatle

![[Pasted image 20240210102209.png]]
![[Pasted image 20240210102216.png]]
Substituting in $U_{j}^{n}=e^{ijh \xi }$ and $U_{j}^{n+1}=g(\xi )U_{j}^{n}=g(\xi )e^{ijh \xi}$,
$$\begin{align*}
g(\xi )e^{ijh \xi}&= e^{ijh \xi} + \frac{k \kappa }{2h^{2}}e^{ijh \xi}\left(e^{-ih \xi}-2+e^{ih \xi} + g(\xi) (e^{-ih \xi}-2+e^{ih \xi}) \right)-k \gamma e^{ijh \xi } \left[(1-\theta ) +\theta g(\xi )\right]\\
g(\xi )&= 1+ \frac{k \kappa }{2h^{2}}\left(e^{-ih \xi}-2+e^{ih \xi}  \right)(1+g(\xi ))-k \gamma \left[(1-\theta ) +\theta g(\xi )\right]\\
g(\xi )\left(1-\frac{k \kappa }{2h^{2}}\left(e^{-ih \xi}-2+e^{ih \xi}  \right) +\theta k \gamma \right)&= 1+\frac{k \kappa }{2h^{2}}\left(e^{-ih \xi}-2+e^{ih \xi}  \right)-k \gamma(1-\theta ) \\
g(\xi )&= \frac{1+\frac{k \kappa }{2h^{2}}\left(e^{-ih \xi}-2+e^{ih \xi}  \right)-k \gamma(1-\theta )}{1-\frac{k \kappa }{2h^{2}}\left(e^{-ih \xi}-2+e^{ih \xi}  \right) +\theta k \gamma}\\
&= \frac{1+\frac{k \kappa }{h^{2}}\left(\text{cos}(\xi h)-1  \right)-k \gamma(1-\theta )}{1-\frac{k \kappa }{h^{2}}\left(\text{cos}(\xi h)-1  \right) +\theta k \gamma}\\
&= \frac{1-\frac{k \kappa }{h^{2}}\left(1-\text{cos}(\xi h)  \right)-k \gamma(1-\theta )}{1+\frac{k \kappa }{h^{2}}\left(1-\text{cos}(\xi h)  \right) +\theta k \gamma}
\end{align*}$$
Our stability condition is that $\lvert g(\xi ) \rvert \le 1$, or equivalently that



![[Pasted image 20240210102225.png]]
If $\theta =0$, then
$$g(\xi )= \frac{1+\frac{k \kappa }{2h^{2}}\left(e^{-ih \xi}-2+e^{ih \xi}  \right)-k \gamma}{1-\frac{k \kappa }{2h^{2}}\left(e^{-ih \xi}-2+e^{ih \xi}  \right) }$$

![[Pasted image 20240210102234.png]]
$$\begin{align*}
U_{j}^{n+1}&= U^{n-1}_{j-2}-\frac{ak}{h}(U_{j}^{n}-U_{j-2}^{n})+U_{j}^{n}-U_{j-2}^{n}\\
\frac{U_{j}^{n+1}-U_{j}^{n}}{k}+\frac{U^{n}_{j-2}-U^{n-1}_{j-2}}{k}&= -a \frac{U_{j}^{n}-U_{j-2}^{n}}{h}
\end{align*} $$

We can use the Taylor expansions
$$\begin{align*}
u(x,t \pm h)&= u(x,t) \pm ku_{t}(x,t)+\frac{k^{2}}{2}u_{tt}(x,t)+\mathcal{O}(k^{3})\\
u(x-2h,t)&= u(x,t)-2hu_{x}(x,t)+2h^{2}u_{xx}(x,t)+\mathcal{O}(h^{3})
\end{align*}$$
to rewrite the discretization as
$$\begin{align*}
u_{t}(x,t)+\frac{k}{2}u_{tt}(x,t)+u_{t}(x-2h,t)-\frac{k}{2}u_{tt}(x-2h,t)+\mathcal{O}(k^{2})&= -a(2u_{x}(x,t) -2hu_{xx}(x,t)) + \mathcal{O}(h^{2})\\
u_{t}+ \frac{k}{2}u_{tt}+(u_{t}-2hu_{tx}+\mathcal{O}(h^{2}))-\frac{k}{2}(u_{tt}+\mathcal{O}(h))+\mathcal{O}(k^{2})&= -2au_{x}+2hau_{xx}+\mathcal{O}(h^{2})\\
2u_{t}+2h(-u_{tx}-au_{xx})+\mathcal{O}(kh+k^{2})&= -2au_{x}+\mathcal{O}(h^{2})
\end{align*}$$
We can use the original equation to get that $u_{tx}=-au_{xx}$ so that the second term vanishes and divide by two to get that
$$u_{t}+au_{x}= \mathcal{O}(h^{2}+k^{2})$$
where $\mathcal{O}(kh)$ vanishes since it is necessarily smaller than either $\mathcal{O}(h^{2})$ or $\mathcal{O}(k^{2})$. The method has second order accuracy in both time and space.

![[Pasted image 20240210102241.png]]

![[Pasted image 20240210102246.png]]

![[Pasted image 20240210102300.png]]

![[Pasted image 20240210102307.png]]