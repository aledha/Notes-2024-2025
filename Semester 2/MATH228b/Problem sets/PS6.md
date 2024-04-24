![[Pasted image 20240413115149.png]]
$$f(\rho )=\rho u_{\text{max}}\left(1-\frac{\rho }{\rho _{\text{max}}} \right)$$
Roe's scheme is
$$F^{R}_{i+\frac{1}{2}}=\frac{1}{2}\left[f(\rho _{i})+f(\rho _{i+1}) \right]- \frac{1}{2}\lvert a_{i+\frac{1}{2}} \rvert (\rho _{i+1}-\rho _{i})$$
where $a_{i+\frac{1}{2}}=u_{\text{max}}\left(1- \frac{\rho _{i}+\rho _{i+1}}{\rho _{\text{max}}}\right)$, and we have that that
$$f(\rho _{i+1})-f(\rho _{i})=a_{i+\frac{1}{2}}(\rho _{i+1}-\rho _{i}).$$
We can write Roe's scheme as 
$$\begin{align*}
F^{R}_{i+\frac{1}{2}}&= \begin{cases}
\frac{1}{2}\left[f(\rho _{i})+f(\rho _{i+1}) \right]-\frac{1}{2}\left[f(\rho _{i+1})-f(\rho _{i}) \right] & \quad\text{for }a_{i+\frac{1}{2}}\ge0 \\
\frac{1}{2}\left[f(\rho _{i})+f(\rho _{i+1}) \right]+\frac{1}{2}\left[f(\rho _{i+1})-f(\rho _{i}) \right] & \quad\text{for }a_{i+\frac{1}{2}}<0
\end{cases}\\
&= \begin{cases}
f(\rho _{i})  & \quad\text{for }\rho _{i}+\rho _{i+1}<\rho _{\text{max}}\\
f(\rho _{i+1}) & \quad\text{for }\rho _{i}+\rho _{i+1}>\rho _{\text{max}}
\end{cases}
\end{align*}$$


Notice that $f$ is maximum for $\rho=\frac{\rho _{\text{max}}}{2}$, where it is $f \left(\frac{\rho _{\text{max}}}{2} \right)=\frac{\rho _{\text{max}}u_{\text{max}}}{4}$. It minimum for $\rho =0,\rho =\rho _{\text{max}}$, where the function is zero. 
$f(\rho)$ is strictly increasing in the interval $\rho \in \left[0,\frac{\rho _\text{max}}{2} \right]$ and strictly decreasing in the interval $\rho \in \left[\frac{\rho _{\text{max}}}{2},\rho _\text{max} \right]$.
So the Godunov scheme,
$$F^{G}_{i+\frac{1}{2}}=\begin{cases}
\min_{\rho \in [\rho _{i},\rho _{i+1}]}f(\rho ) & \quad\text{for }\rho _{i}<\rho _{i+1} \\
\max_{\rho \in [\rho _{i},\rho _{i+1}]}f(\rho ) & \quad\text{for }\rho _{i}>\rho _{i+1}
\end{cases}$$
can be simplified in this case to
$$F^{G}_{i+\frac{1}{2}}=\begin{cases}
f(\rho _{i}) & \quad\text{for }\rho _{i}<\rho _{i+1}<\frac{\rho _{\text{max}}}{2} \\
f(\rho _{i+1}) & \quad\text{for }\frac{\rho _{\text{max}}}{2}<\rho _{i}<\rho _{i+1} \\
f(\rho _{i}) & \quad\text{for } \rho _{i+1}<\rho _{i}<\frac{\rho _{\text{max}}}{2} \\
f(\rho _{i+1}) & \quad\text{for }\frac{\rho _{\text{max}}}{2}<\rho _{i+1}<\rho _{i} \\
\min_{\rho \in \{\rho _{i},\rho _{i+1} \}}f(\rho ) & \quad\text{for }\rho _{i}<\frac{\rho _{\text{max}}}{2}<\rho _{i+1} \\
\frac{\rho _\text{max}u_{\text{max}}}{4} & \quad\text{for }\rho _{i+1}<\frac{\rho _{\text{max}}}{2}<\rho _{i}
\end{cases}$$
$$F^{G}_{i+\frac{1}{2}}=\begin{cases}
f(\rho _{i}) & \quad\text{for }\rho _{i},\rho _{i+1}<\frac{\rho _{\text{max}}}{2} \\
f(\rho _{i+1}) & \quad\text{for }\frac{\rho _{\text{max}}}{2}<\rho _{i},\rho _{i+1} \\

\min_{\rho \in \{\rho _{i},\rho _{i+1} \}}f(\rho ) & \quad\text{for }\rho _{i}<\frac{\rho _{\text{max}}}{2}<\rho _{i+1} \\
\frac{\rho _\text{max}u_{\text{max}}}{4} & \quad\text{for }\rho _{i+1}<\frac{\rho _{\text{max}}}{2}<\rho _{i}
\end{cases}$$
For Roe's scheme, I got this result at $t=2$.
![[Pasted image 20240419143650.png|500]]
For Godunov's scheme,
![[Pasted image 20240419143822.png|500]]
Here, the shock has dissipated, in contrast to Roe's.

Let's see if the shock in Roe's scheme is entropy violating.
The shock speed is
$$\begin{align*}
s&= \frac{f(\rho _{R})-f(\rho _{L})}{\rho _{R}-\rho _{L}}\\
&= \frac{0.2(1-0.2)-0.8(1-0.8)}{0.2-0.8}\\
&= 0
\end{align*}$$
The slopes of the characteristics are
$$a(\rho )=f'(\rho )= u_{\text{max}}\left(1-\frac{2\rho }{\rho _{\text{max}}}\right)$$
and that 
$$\begin{align*}
a(\rho _{L}= 0.8)&= 1-1.6=-0.6,\\
a(\rho _{R}=0.2)&= 1-0.4=0.6,
\end{align*}$$
meaning that the slopes of characteristics are emerging from the shock. The entropy condition,
$$a(\rho _{L})>s>a(\rho _{R}),$$
is violated.
Godunov doesn't have a shock, and is entropy satisfying. W will therefore use this scheme for the rest of the problem set.

<div style="page-break-after: always;"></div>

![[Pasted image 20240413115200.png]]
[Animation of last iteration](https://drive.google.com/file/d/13oy6XAvb-zheJepCYCIiQXS0ts3Mzbq1/view?usp=sharing). The flow converged after 3 iterations, and I got the average flow $\dot q≈0.125$.

<div style="page-break-after: always;"></div>

![[Pasted image 20240413115221.png]]

![[Pasted image 20240419145201.png|500]]
We see a minimum at $\tau =1$, which seems intuitive. Here is an animation of that case: [animation](https://drive.google.com/file/d/1Kk77yCSMiNDTyVFpn93IOWACP54vyhBy/view?usp=sharing).
It seems as the optimal delay is either $\tau =0$, $\tau =\frac{T}{10}$ or $\tau =\frac{9T}{10}$.