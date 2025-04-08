Operator splitting is a numerical technique to solve problems of the form
$$
\begin{equation}
\frac{ \partial y }{ \partial t } =L_{1}(y)+L_{2}(y),
\end{equation}
$$
where $L_{1},L_{2}$ are operators on $y$. 

For a parameter $\theta \in[0,1]$ and a time step $\Delta t$, denote $t_{n}=n\Delta t$, $t_{n+\theta}=n\Delta t+\theta \Delta t$, and $y^{n}=y(t_{n})$.

1. With $y^{n}$ as an initial condition, solve $\frac{ \partial y }{ \partial t }=L_{1}(y)$ for $t\in[t_{n},t_{n+\theta}]$ and denote the solution as $y_{\theta}^{n}$.
2. With $y^{n}_{\theta}$ as an initial condition, solve $\frac{ \partial y }{ \partial t }=L_{2}(y)$ for $t\in[t_{n},t_{n+1}]$ and denote the solution as $y_{\theta}^{n+1}$.
3. With $y^{n+1}_{\theta}$ as an initial condition, solve $\frac{ \partial y }{ \partial t }=L_{1}(y)$ for $t\in[t_{n+\theta},t_{n+1}]$ and denote the solution as $y^{n+1}$.