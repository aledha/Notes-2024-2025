I did not submit this. 
## Notes
![[Pasted image 20231016114240.png|700]]





![[Pasted image 20231016113810.png|800]]

![[Pasted image 20231016113822.png|800]]
$$\Bigg\{\begin{align*}
(\partial _{t}-\Delta  )G(t,x,s,y)  &=\delta _{0}((t,x)-(s,y)) \quad&\text{in }\mathbb{R}_{t}\times(0,\infty )_{x} \\
G(t,x,s,y)  &=0 \quad&\text{on }\mathbb{R}_{t}\times \{0,\infty \}_{x}\\
G(t,x,s,y)  &=0 \quad&\text{in }(t,x)\in (-\infty,s)\times(0,\infty)_{x}
\end{align*}$$
If we set $G(t,x,s,y)=E_{+}(t-s,x-y)- E_{+}(t-s,y)= \mathbb 1_{(0,\infty)}(t-s) \frac{1}{(4\pi (t-s))^{\frac{d}{2}}}e^{- \frac{\lvert x-y \rvert^{2}}{4(t-s)}}-\mathbb 1_{(0,\infty)}(t-s) \frac{1}{(4\pi (t-s))^{\frac{d}{2}}}e^{- \frac{\lvert y \rvert^{2}}{4(t-s)}}$,
the third equation is solved. Further, both for $x=0$ and $x\to\infty$, we have that $G(t,0,s,y)=0$
$$(\partial _{t}-\partial _{x}^{2})G=(\partial _{t}-\partial _{x}^{2})\left[\mathbb 1_{(0,\infty)}(t-s) \frac{1}{(4\pi (t-s)))^{\frac{1}{2}}} \left(e^{- \frac{\lvert x-y \rvert^{2}}{4(t-s)}}-e^{- \frac{\lvert y \rvert^{2}}{4(t-s)}} \right)\right] $$
$$\partial _{t}G=\delta _{0}(t-s) \frac{e^{- \frac{\lvert x-y \rvert^{2}}{4(t-s)}}-e^{- \frac{\lvert y \rvert^{2}}{4(t-s)}} }{(4\pi (t-s))^{\frac{1}{2}}}+\mathbb 1_{(0,\infty)}(t-s) 
\frac{ 
\left(\frac{\lvert x-y \rvert^{2} }{4(t-s)^{2}}e^{- \frac{\lvert x-y \rvert^{2}}{4(t-s)}}-\frac{\lvert y \rvert^{2} }{4(t-s)^{2}}e^{- \frac{\lvert y \rvert^{2}}{4(t-s)}} \right) (4 \pi (t-s))^{\frac{1}{2}}-\left(e^{- \frac{\lvert x-y \rvert^{2}}{4(t-s)}}-e^{- \frac{\lvert y \rvert^{2}}{4(t-s)}}\right) \frac{1}{2}(4\pi (t-s))^{-\frac{1}{2}}
}
{}$$

$$\begin{align*}
\int\int G(t,x,s,y)(-\partial_{t}-\partial _{x}^{2} )\phi (t,x)\text{ d}t \text{ d}x&=\lim_{\epsilon  \to 0} \int\int_{s+\epsilon }^{\infty}  \frac{e^{- \frac{\lvert x-y \rvert^{2}}{4(t-s)}}-e^{- \frac{\lvert y \rvert^{2}}{4(t-s)}} }{(4\pi (t-s))^{\frac{1}{2}}}(-\partial_{t}-\partial _{x}^{2} )\phi (t,x)\text{ d}t \text{ d}x\\
&= \lim_{\epsilon  \to 0}\int\int_{s+\epsilon }^{\infty}
\end{align*}$$



![[Pasted image 20231016113832.png|800]]

![[Pasted image 20231016113841.png|800]]