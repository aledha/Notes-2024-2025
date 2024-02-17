By Alexander Hatle

## Problem 1
![[Pasted image 20240210102209.png|800]]
![[Pasted image 20240210102216.png|800]]
Substituting in $U_{j}^{n}=e^{ijh \xi }$ and $U_{j}^{n+1}=g(\xi )U_{j}^{n}=g(\xi )e^{ijh \xi}$,
$$\begin{align*}
g(\xi )e^{ijh \xi}&= e^{ijh \xi} + \frac{k \kappa }{2h^{2}}e^{ijh \xi}\left(e^{-ih \xi}-2+e^{ih \xi} + g(\xi) (e^{-ih \xi}-2+e^{ih \xi}) \right)-k \gamma e^{ijh \xi } \left[(1-\theta ) +\theta g(\xi )\right]\\
g(\xi )&= 1+ \frac{k \kappa }{2h^{2}}\left(e^{-ih \xi}-2+e^{ih \xi}  \right)(1+g(\xi ))-k \gamma \left[(1-\theta ) +\theta g(\xi )\right]\\
g(\xi )\left(1-\frac{k \kappa }{2h^{2}}\left(e^{-ih \xi}-2+e^{ih \xi}  \right) +\theta k \gamma \right)&= 1+\frac{k \kappa }{2h^{2}}\left(e^{-ih \xi}-2+e^{ih \xi}  \right)-k \gamma(1-\theta ) \\
g(\xi )&= \frac{1+\frac{k \kappa }{2h^{2}}\left(e^{-ih \xi}-2+e^{ih \xi}  \right)-k \gamma(1-\theta )}{1-\frac{k \kappa }{2h^{2}}\left(e^{-ih \xi}-2+e^{ih \xi}  \right) +\theta k \gamma}\\
&= \frac{1+\frac{k \kappa }{h^{2}}\left(\text{cos}(\xi h)-1  \right)-k \gamma(1-\theta )}{1-\frac{k \kappa }{h^{2}}\left(\text{cos}(\xi h)-1  \right) +\theta k \gamma}\\
&= \frac{1-\frac{k \kappa }{h^{2}}\left(1-\text{cos}(\xi h)  \right)-k \gamma(1-\theta )}{1+\frac{k \kappa }{h^{2}}\left(1-\text{cos}(\xi h)  \right) +\theta k \gamma}
\end{align*}$$
Our stability condition is that $\lvert g(\xi ) \rvert \le 1$, or that $-1 \le g(\xi ) \le1$. Let's check each of these separately. Firstly,
$$\begin{align*}\\
g(\xi )&\le 1,\\

 \frac{1-\frac{k \kappa }{h^{2}}\left(1-\text{cos}(\xi h)  \right)-k \gamma(1-\theta )}{1+\frac{k \kappa }{h^{2}}\left(1-\text{cos}(\xi h)  \right) +\theta k \gamma}&\le 1,\\
1- \frac{k \kappa }{h^{2}}\left(1-\text{cos}(\xi h)  \right)-k \gamma(1-\theta )  &\le   1+ \frac{k \kappa }{h^{2}}\left(1-\text{cos}(\xi h)  \right)+\theta k \gamma, \\
-2 \frac{k \kappa }{h^{2}}(1-\text{cos}(\xi h))&\le k \gamma, 
\end{align*}$$
where the LHS is always negative and the RHS is always positive. This is satisfied regardless of $\theta$. 
Let's check the second condition,
$$\begin{align*}
-1 &\le g(\xi ),\\
-1 &\le \frac{1-\frac{k \kappa }{h^{2}}\left(1-\text{cos}(\xi h)  \right)-k \gamma(1-\theta )}{1+\frac{k \kappa }{h^{2}}\left(1-\text{cos}(\xi h)  \right) +\theta k \gamma},\\
-1-\frac{k \kappa }{h^{2}}\left(1-\text{cos}(\xi h)  \right) -\theta k \gamma &\le 1-\frac{k \kappa }{h^{2}}\left(1-\text{cos}(\xi h)  \right)-k \gamma(1-\theta ),\\
-2&\le \theta k \gamma -k \gamma (1-\theta ),\\
-2 &\le k \gamma (2\theta -1).
\end{align*}$$
If $\theta \ge 1/2$, the RHS is positive and the method is unconditionally stable.


![[Pasted image 20240210102225.png|800]]
If $\theta =0$, then
$$g(\xi )= \frac{1-\frac{k \kappa }{h^{2}}\left(1-\text{cos}(\xi h)  \right)-k \gamma}{1+\frac{k \kappa }{h^{2}}\left(1-\text{cos}(\xi h) \right) }.$$
Let's again check that $-1 \le g(\xi )\le1$ separately. Firstly,
$$\begin{align*}
g(\xi )&\le 1,\\
\frac{1-\frac{k \kappa }{h^{2}}\left(1-\text{cos}(\xi h)  \right)-k \gamma}{1+\frac{k \kappa }{h^{2}}\left(1-\text{cos}(\xi h) \right) } &\le 1,\\
1-\frac{k \kappa }{h^{2}}\left(1-\text{cos}(\xi h)  \right)-k \gamma &\le 1+\frac{k \kappa }{h^{2}}\left(1-\text{cos}(\xi h) \right), \\
0 &\le 2\frac{k \kappa }{h^{2}}\left(1-\text{cos}(\xi h) \right), 
\end{align*}$$
which is true regardless. The other inequality is
$$\begin{align*}
-1 &\le g(\xi ),\\
-1 &\le \frac{1-\frac{k \kappa }{h^{2}}\left(1-\text{cos}(\xi h)  \right)-k \gamma}{1+\frac{k \kappa }{h^{2}}\left(1-\text{cos}(\xi h) \right) },\\
-1-\frac{k \kappa }{h^{2}}\left(1-\text{cos}(\xi h) \right)  &\le 1-\frac{k \kappa }{h^{2}}\left(1-\text{cos}(\xi h)  \right)-k \gamma,\\
k \gamma &\le 2,\\
k &\le \frac{2}{\gamma },
\end{align*}$$
which is the condition we were looking for.

<div style="page-break-after: always;"></div>

![[Pasted image 20240210102234.png|800]]
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
We can use the original equation that $u_{tx}=-au_{xx}$, so that the second term vanishes and divide by two to get that
$$u_{t}+au_{x}= \mathcal{O}(h^{2}+k^{2})$$
where $\mathcal{O}(kh)$ vanishes since it is smaller than either $\mathcal{O}(h^{2})$ or $\mathcal{O}(k^{2})$. The local truncation error is
$$\begin{align*}
\tau _{j}^{n}&=  u_{t}+au_{x}-U_{j}^{n+1}- U^{n-1}_{j-2}+\frac{ak}{h}(U_{j}^{n}-U_{j-2}^{n})-U_{j}^{n}+U_{j-2}^{n}\\
&= \mathcal{O}(h^{2}+k^{2}),
\end{align*}$$
and the method is second order accurate in both time and space.

![[Pasted image 20240210102241.png|800]]
The domain of dependance for the the point $(X,T)$ is $\left[X-2\frac{h}{k},X\right]$. Since we want our solution to converge to the true solution $u(X,T)=u(X-aT)$, this point must be in the domain of dependance, i.e.,
$$X-2\frac{h}{k}T\le X-aT  \le X$$
and hence this method satisfies the CFL condition if
$$0 \le  \frac{ak}{h} \le2$$

![[Pasted image 20240210102246.png|800]]

Substituting in $U_{j}^{n-1}=e^{ijh \xi }$ and $U_{j}^{n}=g(\xi )U_{j}^{n-1}=g(\xi )e^{ijh \xi}$,
$$\begin{align*}
g(\xi )^{2}e^{ijh \xi }&= e^{i(j-2)h \xi }- \left(\frac{ak}{h}-1 \right) \left(g(\xi )e^{ijh \xi }-g(\xi )e^{i(j-2)h \xi } \right)\\
g(\xi )^{2}&= e^{-2i h \xi }-\left(\frac{ak}{h}-1 \right) \left(g(\xi )-g(\xi )e^{-2ih \xi } \right)
\end{align*}$$
Setting $\gamma (\xi )=e^{i h \xi }g(\xi )$,
$$\begin{align*}
\gamma (\xi )^{2}e^{-2ih \xi }&= e^{-2ih \xi }- \left(\frac{ak}{h}-1 \right)(\gamma (\xi) e^{-ih\xi }-\gamma (\xi )e^{-3ih \xi })\\
	\gamma (\xi )^{2}&= 1-\left(\frac{ak}{h} -1\right)(e^{ih \xi }-e^{-ih \xi })\gamma (\xi )
\end{align*}$$
Using that $e^{ix}-e^{-ix}=\text{cos}(x)+i \text{sin}(x)-\text{cos}(-x)-i \text{sin}(-x)=2i \text{sin}(x)$,
$$\gamma (\xi )^{2}= 1- 2\left(\frac{ak}{h} -1\right)i \text{sin}(h \xi ) \gamma (\xi ).$$
This is closely related to 
![[Pasted image 20240212105212.png|500]]
which has the stability limit $\lvert \nu  \rvert \le 1$. Translating this to our skewed method, our stability limit becomes
$$\left\lvert \frac{ak}{h}-1 \right\rvert \le 1.$$
The CFL condition is $0\le\frac{ak}{h}\le2$, which in fact satisfies the above stability limit.

<div style="page-break-after: always;"></div>

## Problem 3
See attached code.
Results from problem 3f and 3g:

![[plot_1.png|800]]

![[plot_3.png]]