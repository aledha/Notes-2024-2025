![[Pasted image 20240322115701.png]]
$$\frac{M}{P}=\exp(a)\exp(-bi )Y=L(i,Y)$$

The quantity theory of money:
$$MV=PY,$$
where we assume that $V$ is constant.
$$g_{M}=\pi +g_{Y},$$
Seigniorage revenue:
$$\begin{align*}
S&=  \frac{\dot M}{P}\\
&= g_{M}L(\overline{r}+\pi , \overline{Y})\\
&= (\pi +g_{Y})L(\overline{r}+\pi ,\overline{Y})
\end{align*}$$
$$\frac{\text{d}S}{\text{d} \pi }=L(\overline{r}+\pi ,\overline{Y})+(\pi +g_{Y})\frac{\partial L(\overline{r}+\pi ,\overline{Y})}{\partial \pi }$$
The first term is positive.
$$\begin{align*}
L(\overline{r}+\pi , \overline{Y})&= \exp(a)\exp(-b \overline{r}-b \pi )\overline{Y}\\
\frac{\partial L(\overline{r}+\pi ,\overline{Y})}{\partial \pi }&= -b \exp(a)\exp(-b \overline{r}-b \pi )\overline{Y}\\
&= -bL(\overline{r}+\pi ,\overline{Y})
\end{align*}$$
$$\frac{\text{d}S}{\text{d}\pi }= (1-b(\pi +g_{Y}))L(\overline{r}+\pi ,Y)$$
Max obtained when
$$\begin{align*}
1-b(\pi +g_{Y})&= 0\\
\pi &= \frac{1}{b}-g_{Y}
\end{align*}$$



![[Pasted image 20240322115708.png]]
Then,
$$\begin{align*}
L(\overline{r}+\pi , \overline{Y})&= \exp(a)\exp(-b \overline{r}-b \pi )X \exp(-c \pi )\\
\frac{\partial L(\overline{r}+\pi ,\overline{Y})}{\partial \pi }&= -(b+c) \exp(a)\exp(-b \overline{r}-b \pi )X \exp(-c \pi )\\
&= -(b+c)L(\overline{r}+\pi ,\overline{Y})
\end{align*}$$
Max is obtained when
$$\frac{\text{d}S}{\text{d}\pi }=(1-(b+c)(\pi +g_{Y}))L(\overline{r}+\pi , \overline{Y})=0,$$
or when 
$$\begin{align*}
1-(b+c)(\pi +g_{Y})&= 0\\
g_{M} &= \frac{1}{b+c}.
\end{align*}$$
We see that a **higher** decrease of the output leads to a **lower** lever of money growth rate that generates the highest level of seigniorage revenue.

![[Pasted image 20240322115714.png]]
In our model, hyperinflations occurs due to setting the target revenue $G$ higher than the maximum seigniorage revenue $S_{\text{max}}$, where 
$$S_{\text{max}}=\frac{\text{log}A-\text{log}m}{b}m.$$
The notes show that 
$$\frac{\dot m}{m}= \frac{\beta }{1-\beta b}\frac{b}{m}(S_{\text{max}}-G).$$
We have the assumption that $\beta < 1/b$, so the only way to make the instantaneous growth of real money balances negative is by setting $G$ higher than $S_{\text{max}}$.

However, if $b$ is decreased, then $S_{\text{max}}$ is increased, and hence harder to set $G$ higher, and therefore making hyperinflations less likely to occur.


![[Pasted image 20240322115734.png]]
![[fredgraph (1).png]]
This graph seems pretty stable up until 2015, suggesting that the money demand has high elasticity with respect to GDP.

![[Pasted image 20240322115742.png]]
![[fredgraph (2).png]]
The red line is supposed to approximate
$$g_{M}-g_{Y}=\pi $$
$$\text{ ln}\left(\frac{M}{P} \right)=a-b(r +\pi )+\text{ ln}Y$$
I'm not sure what this tells us about $b$.