The operator splitting scheme can be used on problems of the form
$$
\frac{ \partial y }{ \partial t }=L_{1}(y)+L_{2}(y),
$$

where $L_{1}$ and $L_{2}$ are two operators on $y$. For a parameter $\theta \in [0,1]$, the operator splitting method is described as
1. Given an initial condition $y(t_{n})=y^n$, solve $\frac{ \partial y }{ \partial t } =L_{1}(y)$ for $t_{n}\leq t\leq t_{n}+\theta\Delta t$, and call the solution $y_{\theta}^n$.
2. With the initial condition $y(t_{n})=y^n_{\theta}$, solve $\frac{ \partial y }{ \partial t } =L_{2}(y)$ for $t_{n}\leq t\leq t_{n}+\Delta t$, and denote the solution as $y^{n+1}_{\theta}$.
3. With the initial condition $y(t_{n}+\theta\Delta t)=y^{n+1}_{\theta}$, solve $\frac{ \partial y }{ \partial t } =L_{1}(y)$ for $t_{n}+\theta\Delta t \leq t\leq t_{n}+\Delta t$. Denote this solution as $y^{n+1}$.

It can be shown that if $\theta=0.5$, operator splitting is second order accurate. Otherwise, it is first order accurate. \cite{}

We want to apply operator splitting on the system \ref{}
$$
\begin{align}
\frac{\lambda }{1+\lambda }\nabla \cdot (M_{i}\nabla v)+\chi I_{\text{stim}} &= \chi C_{m}\frac{\partial v}{\partial t}+\chi I_{\text{ion}}(v,s), &x\in H,\\
\frac{\partial s}{\partial t}&= f(s,v,t),&x\in H,\\
n \cdot (M_{i}\nabla v)&= 0, &x\in \partial H.
\end{align}
$$
\ref{} can be written as
$$
\frac{ \partial v }{ \partial t } =- \frac{1}{C_{m}}I_\text{ion}(v,s)+ \frac{1}{\chi C_{m}} \frac{\lambda}{1+\lambda}\nabla \cdot(M_{i}\nabla v)+ \frac{1}{C_{m}}I_\text{stim}.
$$
We now choose the operators for $v$ as 
$$
\begin{align}
L_{1,v}(v,s) & =- \frac{1}{C_{m}}I_\text{ion}(v,s), \\
L_{2,v}(v,s) & = \frac{1}{\chi C_{m}} \frac{\lambda}{1+\lambda}\nabla \cdot(M_{i}\nabla v)+ \frac{1}{C_{m}}I_\text{stim},
\end{align}
$$

while the operators for $s$ are simply chosen as $L_{1,s}(v,s)=f(s,v,t)$ and $L_{2,s}(v,s)=0$. Now we apply the scheme described above.


1. First, given $v(t_{n})=v^{n}$ and $s(t^{n})=s^{n}$, solve
$$
\begin{align}
\frac{\partial v}{\partial t}&= -\frac{1}{C_{m}}I_{\text{ion}}(v,s),\\
\frac{\partial s}{\partial t}&= f(v,s,t),
\end{align}
$$
	for $t_{n}<t \le t_{n}+\theta \Delta t$. Denote the solutions as $v_{\theta }^{n}$ and $s_{\theta }^{n}$.
2. Then, with the initial condition $v(t_{n})=v_{\theta }^{n}$, solve
	$$
\frac{\partial v}{\partial t}=\frac{1}{\chi C_{m}}\frac{\lambda }{1+\lambda }\nabla \cdot(M_{i}\nabla v)+\frac{1}{C_{m}}I_\text{stim},
$$
	for $t_{n}<t \le t_{n}+\Delta t$. The solution is denoted as $v_{\theta }^{n+1}$.
3. Finally, with the initial conditions $v(t_{n}+\theta \Delta t)=v_{\theta }^{n+1}$ and $s(t_{n}+\theta \Delta t)=s^{n}_{\theta }$, solve the system
$$
\begin{aligned}
\frac{\partial v}{\partial t}&= -\frac{1}{C_{m}}I_{\text{ion}}(v,s),\\
\frac{\partial s}{\partial t}&= f(v,s),
\end{aligned}
$$
	for $t_{n}+\theta \Delta t <t \le t_{n}+\Delta t$. The solutions are $v^{n+1}$ and $s ^{n+1}$. 

Notice that since $L_{2,s}(v,s)=0$, we omit it in step 2, and we use the solution $s_{\theta}^n$ from step 1 as the initial condition for step 3.