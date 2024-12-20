The operator splitting scheme can be used on problems of the form
$$
\frac{ \partial y }{ \partial t }=L_{1}(y)+L_{2}(y),
$$

where $L_{1}$ and $L_{2}$ are two operators on $y$. For a parameter $\theta \in [0,1]$, the operator splitting method is described as
\begin{enumerate}
    \item Given an initial condition $y(t_{n})=y^n$, solve $\frac{ \partial y }{ \partial t } =L_{1}(y)$ for $t\in [t_n, t_n+\theta\Delta t]$, and call the solution $y_{\theta}^n$.
    \item With the initial condition $y(t_{n})=y^n_{\theta}$, solve $\frac{ \partial y }{ \partial t } =L_{2}(y)$ for $t\in [t_n, t_n+\Delta t]$, and denote the solution as $y^{n+1}_{\theta}$.
    \item With the initial condition $y(t_{n}+\theta\Delta t)=y^{n+1}_{\theta}$, solve $\frac{ \partial y }{ \partial t } =L_{1}(y)$ for $t\in [t_n+\theta\Delta t, t_n+\Delta t]$. Denote this solution as $y^{n+1}$.
\end{enumerate}

We first consider the case when $\theta=1$. Consider an initial value problem of the form
$$
\begin{align}
\frac{\text{d}u}{\text{d}t}  & =(L_{1}+L_{2})u, \\
u(0) & =u_{0},
\end{align}
$$
where $L_{1}$ and $L_{2}$ are operators on $u$. Choosing a small timestep $\Delta t$, we approximate $u(\Delta t)$ by first solving
$$
\begin{align}
\frac{\text{d}v}{\text{d}t}  & =L_{1}(v) ,\\
v(0) & =u_{0},
\end{align}
$$
for $t \in [0,\Delta t]$, where the solution approximates $v(\Delta t)$. Then, we solve
$$
\begin{align}
\frac{\text{d}w}{\text{d}t}  & =L_{2}(w), \\
w(0) & =v(\Delta t),
\end{align}
$$
for $t\in[0,\Delta t]$. We Taylor expand $u(\Delta t)$:
$$
\begin{equation}
u(\Delta t)=u_{0}+\Delta t \frac{\text{d}u}{\text{d}t} \Big\vert_{0}+\frac{\Delta t^2}{2}\frac{ \text{d} ^2u }{ \text{d} t^2 } \Big\vert_{0}+\mathcal{O}(\Delta t^3)
\end{equation}
$$

If $L_{1}$ and $L_{2}$ do not explicitly depend on $t$, we obtain 
$$
\begin{equation*}
\frac{ \text{d} ^2u }{ \text{d} t^2 } =(L_{1}+L_{2})(L_{1}+L_{2})u=:(L_{1}+L_{2})^2u, 
\end{equation*}
$$
where we introduced the shorthand $(L_{1}+L_{2})(L_{1}+L_{2})\cdots(L_{1}+L_{2})=(L_{1}+L_{2})^n$. Inserting this into the Taylor series