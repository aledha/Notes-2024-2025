Alexander Hatle
![[Pasted image 20231022173819.png|800]]
Let the Poisson kernel be
$$P_{t}(x)=c_{n}\frac{t}{\left(t^{2}+\lvert x \rvert ^{2}\right)^{\frac{n+1}{2}}}$$
and the Riesz transform
$$R_{j}f(x)= c_{n} \text{p.v.} \int_{\mathbb{R}^{n}} \frac{y_{j}}{\lvert y \rvert^{n+1}}f(x-y)\text{ d}y$$
where $c_{n}=\Gamma \left(\frac{n+1}{2} \right)\pi ^{-\frac{n+1}{2}}$. The Fourier transform of the Riesz transform is
$$(R_{j}f)^{\wedge}(x)=i \frac{x_{j}}{\lvert x \rvert}\hat f(x)$$

First, we'll need to find the Fourier transform of the Poisson kernel. Exercise 2.2.11 in Classical Fourier Analysis Solution Manual states that
$$\begin{align*}
(e^{-2\pi \lvert x \rvert})^{\wedge}(\xi )&= c_{n} \frac{1}{(1+\lvert \xi  \rvert^{2})^\frac{n+1}{2}}
\end{align*}$$

page 185 solution manual
![[Pasted image 20231102190832.png]]


![[Pasted image 20231022173836.png|800]]
p. 26 stein and weiss


![[Pasted image 20231022173849.png|800]]
![[IMG_7ED8F45BBC0E-1.jpeg|800]]
![[IMG_216F7937336C-1.jpeg|800]]

Want to show that
$$\lVert I_{\alpha} f \rVert_{q} \le C \lVert f \rVert_{p}$$
$(I_{\alpha }f)^{\wedge}(\xi)= (2\pi \lvert \xi  \rvert)^{-a} \hat f(\xi )$





This proof follows closely Stein Chapter 5 p. 120.
$$\mu   \{x \in \mathbb{R}^{n}:\lvert I_\alpha f \rvert \ge \lambda  \}\le C \left(\frac{\lVert f \rVert_{1}}{\lambda } \right)^{\frac{n}{n-\alpha }}$$
We can write the operator as 
$$\begin{align*}
(I_{\alpha }f)(x)&= \frac{\Gamma \left(\frac{n-\alpha }{2} \right)}{\pi ^{\frac{n}{2}}2^{\alpha}  \Gamma (\frac{\alpha }{2})}\int_{\mathbb{R}^{n}}\lvert x-y \rvert^{-n+\alpha }f(y) \text{ d}y \\
&= \frac{\Gamma \left(\frac{n-\alpha }{2} \right)}{\pi ^{\frac{n}{2}}2^{\alpha}  \Gamma (\frac{\alpha }{2})} K*f,
\end{align*}$$
where $K(x)=\lvert x \rvert^{-n+\alpha }$. If we can show that $f\mapsto K*f$ is strong $(p,q)$ and weak $\left(1, \frac{n}{n-\alpha } \right)$, then $f\mapsto I_{\alpha} f$ is as well. 

We can further decompose $K$ into $K=K_{1}+K_{\infty}$, where
$$\begin{align*}
K_{1}(x)&= \begin{cases}
K(x) & \quad\text{for }\lvert x \rvert \le k \\
0 & \quad\text{for }\lvert x \rvert > k 
\end{cases}\\
K_{\infty}(x)&= \begin{cases}
0 & \quad\text{for }\lvert x \rvert \le k \\
K(x) & \quad\text{for }\lvert x \rvert > k .
\end{cases}
\end{align*}$$
for some arbitrary $k>0$.
Now we can write our operator as
$$K*f=K_{1}*f+K_{\infty}*f.$$
We want to show that
$$\mu \{x \in \mathbb{R}^{n}:\lvert K*f \rvert \ge \lambda  \} \le C \left(\frac{\lVert f \rVert_{1}}{\lambda } \right)^{\frac{n}{n-\alpha }}.$$
It suffices to prove the above inequality with $2\lambda$ in the LHS, which can be bounded by
$$\mu \{x \in \mathbb{R}^{n}:\lvert K*f \rvert \ge 2\lambda  \} \le \mu \{x \in \mathbb{R}^{n}:\lvert K_{1}*f \rvert \ge \lambda  \}+\mu \{x \in \mathbb{R}^{n}:\lvert K_{\infty}*f \rvert \ge \lambda  \}$$
Bounding the first term is matter of using Markov's inequality and [Youngs inequality](https://en.wikipedia.org/wiki/Young%27s_convolution_inequality) for convolutions (with $r=1,p=p,q=1$), 
$$\mu \{x \in \mathbb{R}^{n}:\lvert K_{1}*f \rvert \ge \lambda  \}\le \frac{\lVert K_{1}*f \rVert^{p}_{p}}{\lambda ^{p}}\le \frac{\lVert K_{1}\lVert_{1}^{p}  \rVert f \rVert^{p}_{p}}{\lambda ^{p}}$$
where we can assume without loss of generality that $\lVert f \rVert_{p}=1$, as the $L^{p}$ norm is homogeneous. The norm of $K_{1}$ is
$$\lVert K_{1} \rVert_{1}=\int_{\lvert x \rvert \le k}\lvert x \rvert^{-n+\alpha }\text{ d}x=c_{1}k ^{\alpha }.$$
Combining this, we get the bound on the first term,
$$\mu \{x \in \mathbb{R}^{n}:\lvert K_{1}*f \rvert \ge \lambda  \}\le \frac{(c_{1}k^{\alpha })^{p}}{\lambda ^{p}}.$$
The idea for bounding the second term is to choose $k$ such that $\lVert K_{1}*f \rVert_{\infty} \le  \lambda$ such that the second term is zero. Youngs inequality (with $r=\infty,p=p,q=p'$ where $1/p+1/p'=1$) gives
$$\begin{align*}
\lVert K_{\infty}*f \rVert_{\infty} &\le \lVert K_{\infty} \rVert_{p'}\cdot \lVert f \rVert_{p}\\
&= \lVert K_\infty \rVert_{p'}\\
&= \left(\int_{\lvert x \rvert \ge k}(\lvert x \rvert^{-n+\alpha })^{p'} \text{ d}x\right)^{\frac{1}{p'}}\\
&= c_{2}k^{-\frac{n}{q}}
\end{align*}$$
where $\frac{1}{q}= \frac{1}{p}-\frac{\alpha }{n}$.
So if we want $\lVert K_{1}*f \rVert_{\infty} \le  \lambda$ then $c_{2}k^{- \frac{n}{q}}=\lambda$ and such $k=c_{3}\lambda ^{-\frac{q}{n}}$. Then the second term is zero.
$$\begin{align*}
\mu \{x \in \mathbb{R}^{n}:\lvert K*f \rvert \ge 2\lambda  \} &\le \left(c_{1}\frac{k^\alpha }{\lambda } \right)^{p}\\
&\le c_{4} \left(\frac{\left(\lambda ^{-\frac{q}{n}}\right)^{\alpha}}{\lambda }\right)^{p}\\
&\le  c_{4}\left(\lambda ^{-q \left(\frac{1}{p}-\frac{1}{q}\right)-1} \right)^{p}\\
&\le c_{4}\lambda ^{-q}\\
&\le c_{4}\left(\frac{\lVert f \rVert_{p}}{\lambda } \right)^{q}
\end{align*}$$
Taking $p=1$ yields that $q= \frac{n}{n-\alpha}$, showing that $f\mapsto K*f$ is weak $\left(1, \frac{n}{n-\alpha }\right)$.

![[Pasted image 20231022173900.png|800]]
Stein, chapter 3.1.3

We want to prove the identity 
$$\partial_{x_{j}}f=-R_{j}(R_{1}-iR_{2})(\partial_{x_{1}}f+i\partial_{x_{2}}f),$$
which can be done by simple calculation,
$$\begin{align*}
(\partial_{x_{j}}f)^{\wedge}(x)&=  - \frac{ix_{j}}{\lvert x \rvert}\left(\frac{ix_{1}}{\lvert x \rvert}-i \frac{ix_{2}}{\lvert x \rvert} \right)\left(\partial _{x_{1}} f+i \partial _{x_{2}}f\right)^{\wedge}\\
&= \frac{x_{j}}{\lvert x \rvert^{2}}\left(x_{1}-ix_{2} \right)\left(-2 \pi i x_{1}+2\pi x_{2} \right)\hat f\\
&= 2\pi \frac{x_{j}}{\lvert x \rvert^{2}}\left(-ix_{1}^{2} +x_{1}x_{2}-x_{1}x_{2}-ix_{2}^{2}\right)\hat f\\
&= -2\pi ix_{j}\hat f\\
&= (\partial _{x_{j}}f)^{\wedge}(x).
\end{align*}$$
By the $L_{p}$ boundedness of the Riesz transforms, we get that
$$\left\lVert \partial _{x_{j}}f \right\rVert_{p}≲_{p}\lVert \partial _{x_{1}} f+i \partial _{x_{2}}f \rVert_{p},$$
and our desired result,
$$\left\lVert \partial _{x_{1}}f \right\rVert_{p}+\left\lVert \partial _{x_{2}}f \right\rVert_{p}≲_{p}\lVert \partial _{x_{1}} f+i \partial _{x_{2}}f \rVert_{p}.$$

![[Pasted image 20231022173910.png|800]]
maybe see page 80
what does it mean to differentiate dirac delta
Hormander linear pdes vol 1 chapt 2.3 

[[HW8]]