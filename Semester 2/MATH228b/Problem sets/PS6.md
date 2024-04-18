![[Pasted image 20240413115149.png]]
$$f(\rho )=\rho u_{\text{max}}\left(1-\frac{\rho }{\rho _{\text{max}}} \right)$$
$$F^{R}_{i+\frac{1}{2}}=\frac{1}{2}\left[f(\rho _{i})+f(\rho _{i+1}) \right]- \frac{1}{2}\lvert a_{i+\frac{1}{2}} \rvert (\rho _{i+1}-\rho _{i})$$
where $a_{i+\frac{1}{2}}=u_{\text{max}}\left(1- \frac{\rho _{i}+\rho _{i+1}}{\rho _{\text{max}}}\right)$, and that
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
#look at the signs of the slopes of the characteristics $a(u)=\frac{\text{d}f(u)}{\text{d}u}$



Observe that 
$$f'(\rho )= u_{\text{max}}\left(1-\frac{2\rho }{\rho _{\text{max}}}\right)$$
and that $f$ is maximum for $\rho=\frac{\rho _{\text{max}}}{2}$, where it is $f \left(\frac{\rho _{\text{max}}}{2} \right)=\frac{\rho _{\text{max}}u_{\text{max}}}{4}$. It minimum for $\rho =0,\rho =\rho _{\text{max}}$, where the function is zero. 
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



![[Pasted image 20240413115200.png]]

![[Pasted image 20240413115221.png]]
