![[Pasted image 20240125232326.png]]
![[Pasted image 20240205110655.png]]
We observe that there is a very strong positive correlation between the two variables. This is not consistent with the consumption smoothing, as the aggregate consumption graph is following the volatility of the real GDP graph.


![[Pasted image 20240125232340.png]]
The savings function of a consumer in period 1 of 2 can be expressed as
$$\begin{align*}\\
s_{1}&= y_{1}-c_{1}\\
	c_{1}&= \frac{1}{1+\beta } \left(y_{1}+\frac{y_{2}}{1+r} \right)
\\
s_{1}&= \frac{\beta }{1+\beta }y_{1}- \left(\frac{1}{1+\beta } \right)\frac{y_{2}}{1+r}
\end{align*}$$
The function for consumption in period 1 depends on the discount factor $\beta$ because of the tangency condition, i.e., that the consumer mest be indifferent to consuming the present value of $c_{2}$ or $\beta$ times $c_{1}$, leading to the formula $\frac{c_{2}}{1+r}=\beta c_{1}$.

For a higher $\beta$ (more willingness to wait to consume), the consumer saves a higher proportion of their income in the first period, and considers less their income in the second period. Savings will increase with a higher beta.
For smaller $\beta$, the opposite is true. If the consumer is completely unwilling to wait ($\beta =0$), they will have negative savings,
$$s_{1}=-\frac{y_{2}}{1+r},$$
i.e., that the consumer will loan to spend their income in both periods.

![[Pasted image 20240125232350.png]]
We have the constraints
$$\begin{align*}
c_{1}+s_{1}&= y_{1}\\
c_{2}+s_{2}&= y_{2}+s_{1}(1+r)\\
\vdots\\
c_{n+1}+s_{n+1}&= y_{n+1}+s_{n}(1+r)\\
\vdots \\
c_{T}&= y_{T}+s_{T-1}(1+r)
\end{align*}$$
$s_{n+1}=y_{n+1}-c_{n+1}+s_{n}(1+r)$
$$\begin{align*}
s_{1}&= y_{1}-c_{1}\\
s_{2}&= y_{2}-c_{2}+(1+r)(y_{1}-c_{1})\\
s_{3}&= y_{3}-c_{3}+(1+r)(y_{2}-c_{2})+(1+r)^{2}(y_{1}-c_{1})\\
\vdots \\
s_{T-1}&= y_{T-1}-c_{T-1}+(1+r)(y_{T-2}-c_{T-2})+\dots +(1+r)^{T-2}(y_{1}-c_{1})\\
c_{T}&= y_{T}+(1+r)(y_{T-1}-c_{T-1})+(1+r)^{2}(y_{T-2}-c_{T-2})+\dots +(1+r)^{T-1}(y_{1}-c_{1})
\end{align*}$$
Dividing by $(1+r)^{T-1}$,
$$c_{1}+\frac{c_{2}}{1+r}+\frac{c_{3}}{(1+r)^{2}}+\dots +\frac{c_{T}}{(1+r)^{T-1}}=y_{1}+\frac{y_{2}}{1+r}+\frac{y_{3}}{(1+r)^{2}}+\dots +\frac{y_{T}}{(1+r)^{T-1}}$$


![[Pasted image 20240125232408.png]]
### a)
We have the two budget constraints,
$$\begin{align*}
c_{1}+s_{1}&= y_{1}= 2\\
c_{2}-s_{1}(1+r)&= y_{2}=4
\end{align*}$$
these reduce to
$$\begin{align*}
s_{1}&= 2-c_{1}\\
s_{1}&= \frac{c_{2}-4}{1+r}
\end{align*}$$
$$\begin{align*}
2-c_{1}&= \frac{c_{2}-4}{1+r}\\
c_{1}+\frac{c_{2}}{1+r}&= 2+\frac{4}{1+r}
\end{align*}$$
The tangency condition is $c_{2}=\beta (1+r)c_{1}$. Plugging this in, we get
$$\begin{align*}
c_{1}+\frac{\beta (1+r)c_{1}}{1+r}&= 2+ \frac{4}{1+r}\\
c_{1}&= \frac{1}{1+\beta }\left(2+ \frac{4}{1+r} \right)
\end{align*}$$
### b)
Assuming $\beta =1+r=1$. Then,
$$\begin{align*}
c_{1}&= \frac{1}{2} (2+4)=3\\
c_{2}&= c_{1}=3\\
s_{1}&= 2-c_{1}=-1.
\end{align*}$$
### c) 
Assuming $\beta =0, \quad 1+r=1$,
$$\begin{align*}
c_{1}&= 2+4=6\\
c_{2}&= 0\\
s_{1}&= 2-6=-4
\end{align*}$$

### d)
The first consumer is richer in the beginning of the second period, since they have only borrowed 1 unit, while the second consumer borrowed everything from the second period and consumed it in the first. This relates to $\beta$ in the sense that the second consumer had no willingness to wait to consume, while the first consumer was ambivalent to consume in the first and second period.


![[Pasted image 20240125232416.png]]
The consumer must be indifferent to 
$$\begin{align*}
MU(c_{1})&= \beta (1+r)MU(c_{2})\\
\frac{1}{c_{1}}&= 1\\
c_{1}&= 1
\end{align*}$$
The ITCB reduces to
$$\begin{align*}
c_{1}+c_{2}&= y_{1}+y_{2}\\
c_{2}&= 2+4-1 =5
\end{align*}$$
The consumer wants to consume more in the second period because they don't have diminishing returns on their consumption in that period.

![[Pasted image 20240125232430.png]]

For $1+r=1$
$$\begin{align*}
	c_{1}&= \frac{1}{2}\left(2+ \frac{4}{1} \right)=3\\
c_{2}&= c_{1}=3\\
s_{1}&= -1
\end{align*}$$

for $1+r=2$,
$$\begin{align*}
	c_{1}&= \frac{1}{2}\left(2+ \frac{4}{2} \right)=2\\
c_{2}&= 2c_{1}=4\\
s_{1}&= 2-2=0
\end{align*}$$

When the interest rate rises, the consumer borrows less from the second period.