
Plane stress -> $T_{i3}=0, i=1,23$
$$T_{\alpha\beta}=T_{\alpha \beta }(x_{1},x_{2},t)$$
$$E_{\alpha \beta }=\frac{1}{2}(u_{\alpha ,\beta }+u_{\beta \alpha})\tag{1}$$

Cauchy's equation of motion:
$$\text{div}\mathbf T+\rho \mathbf b=\rho \mathbf a$$
$$T_{\alpha \beta ,\beta }+\rho b_{\alpha }=\rho a_\alpha ,\qquad a_\alpha =\ddot u_{\alpha }\tag{2}$$

$$T_{\alpha \beta }=2\mu \left[E_{\alpha \beta }+\frac{\nu }{1-\nu }E_{\rho \rho }\delta _{\alpha \beta} \right]\tag{3}$$
$$\begin{aligned}
E_{\rho \rho }&= E_{11}+E_{22}\\
&= u_{1,1}+u_{2,2}=u_{\rho ,\rho }\\
T_{\alpha \beta}&= 2\mu \left[\frac{1}{2}(u_{\alpha ,\beta}+u_{\beta ,\alpha })+\frac{\nu }{1-\nu }u_{\rho ,\rho} \delta _{\alpha \beta }\right] 
\end{aligned}$$
Use $(1)+(3)$->$(2)$, we get the Navier equations for planar stress
$$\begin{aligned}
T_{\alpha \beta ,\beta }&= 2\mu \left[\frac{1}{2}(u_{\alpha ,\beta \beta }+u_{\beta ,\alpha \beta  })+\frac{\nu }{1-\nu }u_{\rho ,\rho \beta }\delta _{\alpha \beta } \right]\\
T_{\alpha \beta ,\beta }&= 2\mu \left[\frac{1}{2}(u_{\alpha ,\beta \beta }+u_{\beta ,\beta \alpha   })+\frac{\nu }{1-\nu }u_{\rho ,\rho \alpha  } \right]
\end{aligned}$$
$u_{\rho ,\rho \alpha  }$ is just summing over $\rho$, we can sum over $\beta$ instead.
$$\begin{aligned}
T_{\alpha \beta ,\beta }&=  \mu \left[(u_{\alpha ,\beta \beta }+u_{\beta ,\beta \alpha   })+2\frac{\nu }{1-\nu }u_{\beta  ,\beta  \alpha  } \right]\\
&= \mu \left(u_{\alpha ,\beta \beta }+ \frac{1+\nu }{1-\nu }u_{\beta ,\beta \alpha   } \right)
\end{aligned}$$

Equation (2) gives us
$$u_{d,\beta \beta }+\frac{1+\nu }{1-\nu }u_{\beta, \beta \alpha } +\frac{\rho }{\mu }(b_\alpha -\ddot u_\alpha )=0$$