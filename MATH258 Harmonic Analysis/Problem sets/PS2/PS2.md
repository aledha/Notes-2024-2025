Alexander Hatle
![[Pasted image 20231022173819.png|800]]
$$P_{t}(x)=\frac{\Gamma \left(\frac{n+1}{2} \right)}{\pi ^{\frac{n+1}{2}}}\frac{t}{\left(t^{2}+\lvert x \rvert ^{2}\right)^{\frac{n+1}{2}}}$$

$$R_{j}f(x)= c_{n} \text{p.v.} \int_{\mathbb{R}^{n}} \frac{y_{j}}{\lvert y \rvert^{n+1}}f(x-y)\text{ d}y$$
where $c_{n}=\Gamma \left(\frac{n+1}{2} \right)\pi ^{-\frac{n+1}{2}}$.
page 185 solution manual

![[Pasted image 20231022173836.png|800]]
p. 26 stein and weiss


![[Pasted image 20231022173849.png|800]]
![[IMG_7ED8F45BBC0E-1.jpeg|800]]
![[IMG_216F7937336C-1.jpeg|800]]

Want to show that
$$\lVert I_{\alpha} f \rVert_{q} \le C \lVert f \rVert_{p}$$
$(I_{\alpha }f)^{\wedge}(\xi)= (2\pi \lvert \xi  \rvert)^{-a} \hat f(\xi )$






for a proof, see Stein (15, chapter 5) p. 120
and
$$\lvert  \{x \in \mathbb{R}^{n}:\lvert I_\alpha f \rvert \ge \lambda  \}\rvert \le C \left(\frac{\lVert f \rVert_{1}}{\lambda } \right)^{\frac{n}{n-\alpha }}$$
We can write the operator as 
$$\begin{align*}
(I_{\alpha }f)(x)&= \frac{\Gamma \left(\frac{n-\alpha }{2} \right)}{\pi ^{\frac{n}{2}}2^{\alpha}  \Gamma (\frac{\alpha }{2})}\int_{\mathbb{R}^{n}}\lvert x-y \rvert^{-n+\alpha }f(y) \text{ d}y \\
&= \frac{\Gamma \left(\frac{n-\alpha }{2} \right)}{\pi ^{\frac{n}{2}}2^{\alpha}  \Gamma (\frac{\alpha }{2})} K*f,
\end{align*}$$
where $K(x)=\lvert x \rvert^{-n+\alpha }$. If we can show that $f\mapsto K*f$ is weak $\left(1, \frac{n}{n-\alpha } \right)$, then $f\mapsto I_{\alpha} f$ is as well. We can further decompose $K$ into $K=K_{1}+K_{\infty}$, where
$$\begin{align*}
K_{1}(x)&= \begin{cases}
K(x) & \quad\text{for }\lvert x \rvert \le \mu \\
0 & \quad\text{for }\lvert x \rvert > \mu 
\end{cases}\\
K_{\infty}(x)&= \begin{cases}
0 & \quad\text{for }\lvert x \rvert \le \mu \\
K(x) & \quad\text{for }\lvert x \rvert > \mu .
\end{cases}
\end{align*}$$
Now we can write our operator as
$$K*f=K_{1}*f+K_{\infty}*f.$$
We want to show that
$$\lvert \{x \in \mathbb{R}^{n}:\lvert K*f \rvert \ge \lambda  \} \rvert \le C \left(\frac{\lVert f \rVert_{1}}{\lambda } \right)^{\frac{n}{n-\alpha }}.$$


![[Pasted image 20231022173900.png|800]]
Stein, chapter 3.1.3
![[Pasted image 20231102190832.png]]
We want to prove the identity 
$$\partial_{x_{j}}f=-R_{j}(R_{1}-iR_{2})(\partial_{x_{1}}f+i\partial_{x_{2}}f)$$

$$(\partial_{x_{1}}f)^{\wedge}(x)=-2\pi i x_{1}\hat f(x)$$

![[Pasted image 20231022173910.png|800]]
maybe see page 80
what does it mean to differentiate dirac delta
Hormander linear pdes vol 1 chapt 2.3 

[[HW8]]