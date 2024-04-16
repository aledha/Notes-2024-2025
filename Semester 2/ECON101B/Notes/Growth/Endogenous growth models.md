
## Speed of technical change
* Why does firms want to research?
	* Patents, competition, government aided, surplus of resources
* Why does people do research?
	* Wages, prizes and culture, accessibility, random

### Implication of IRS
* Size of economy is important
* Specialization can overcome diminishing returns
	* **Learning by doing:** First product is usually expensive, take long to build. Following products better, cheaper and faster.
	* New types of goods
* Permanent difference in growth rates
	* No convergence of incomes in the long run?
	* Poverty traps


#### Example
Assume that 
* population is fixed to $L$.
* Complete patience for all households: $\beta =1$
* $\sum_{t=1}^{\infty}\text{log}(c_{t})$
	* call $u(c_{t})=\text{log}(c_{t})$
		$\begin{align*}u'(c_{t})&= \beta (1+r)u'(c_{t+1})\\ \frac{c_{t+1}}{c_{t}}&= 1+r\\ \Delta \% c&= r  \end{align*}$
* **Balanced growth path** (BGP)
	* =All variables growth rates constant over time

* Two types of producers: final and intermediate
	* Final: $y_{t}=L^{1-\alpha }\int_{0}^{M_{t}}(x_{i})^{\alpha }\text{ d}i$
		* where $x_{i}$ is the intermediate good, $y_{t}$ is the final good, $L$ is the working population, $\alpha \in [0,1]$ is what?? diminished returns, $M_t$ is the number of intermediate inputs
* Assume **symmetric equilibrium**: in the eq, number of intermediate goods converge to the same.
	All intermediate goods: $X_{t}=\int_{0}^{M_{t}}x_{i}\text{ d}i$
	Number of stuff $x=X_{t}/M_{t}$
Then, we can simplify the production function:
$$\begin{align*}
x_{i}=x_{j}=x&= \frac{X_{t}}{M_{t}}\\
y_{t}&= L^{1-\alpha }\int_{0}^{M_{t}}(x_{i})^{\alpha }\text{ d}i\\
&= L^{1-\alpha }\left(\frac{X_{t}}{M_{t}} \right)^{\alpha }\int_{0}^{M_{t}}\text{ d}i\\
y_{t}&= L^{1-\alpha }\left(\frac{X_{t}}{M_{t}} \right)^{\alpha }M_{t}
\end{align*}$$
The **GDP** is the final goods minus the intermediate goods:
$$GDP_{t}=Y_{t}-X_{t}$$

Assume that the intermediate producers have **exclusive rights** to produce their goods:
$$\text{Profits}=\Pi _{i}=p_{i}x_{i}-x_{i}\cdot 1$$
	Last term: Assume that price of $Y=1$. One final good => one unit of intermediate good.
$$p_{i}=\partial _{x_{i}}y_{t}=\alpha L^{1-\alpha }x_{i}^{\alpha -1}$$
Insert into profits, whats the level of output to max profits?
$$\begin{align*}
\Pi _{i}&= \alpha L^{1-\alpha }x_{i}^{\alpha }-x_{i}\\
\partial _{x_{i}}\Pi _{i}&= \alpha ^{2}L^{1-\alpha }x^{\alpha -1}_{i}-1=0\\
x_{i}^{*}&= \alpha ^{\frac{2}{1-\alpha }}L
\end{align*}$$
	since this is independent of $i$, $x$ must be the same for all $i$. Also time independant since $L$ is const.
Inserted back in, we get
$$\Pi _{t}=\frac{1-\alpha }{\alpha }\alpha ^\frac{2}{1-\alpha }L$$
$$\begin{align*}
Y_{t}&=  L^{1-\alpha }\left(\frac{X_{t}}{M_{t}} \right)^{\alpha }\\
&= L^{1-\alpha }(\alpha ^{\frac{2}{1-\alpha }}L)^\alpha M_{t}\\
&= \alpha ^{\frac{2\alpha }{1-\alpha }}L \cdot M_{t}
\end{align*}$$
Assume
$$\partial _{t}M_{t}=\lambda \cdot R$$
	where $R$ is research spending, $\lambda$ is conversion rate between spending and creating new technologies.
Note that $R$ is a one-time cost while $\Pi$ is constant profit stream. Total sum:
$$\frac{\Pi _{t}}{1+r}+\frac{\Pi _{t}}{(1+r)^{2}}+\dots =\frac{\Pi ^{t}}{r}$$
$$\left(\frac{1}{r}\Pi ^{t} \right)\cdot \partial _{t}M_{t}=\frac{1}{r}\Pi _{t}\lambda R$$
Free entry in R&D implies that R&D should have zero profits in equilibrium. 
$$\Pi ^{*}\lambda =r$$
what is the growth rate of output?
$$\begin{align*}
g_{Y}&= \frac{\partial _{t}Y_{t}}{Y_{t}}=\frac{\Delta Y_{t}}{Y_{t}}
\end{align*}$$
$$GDP_{t} ≈Y_{t}≈C_{t}$$
	(proportional)
$$g_{GDP}=g_{Y}=g_{C}$$
$$g_{Y}=g_{C}=r=\Pi^{*}\lambda =\lambda \cdot \alpha ^{\frac{2}{1-\alpha }}\cdot \frac{1-\alpha }{\alpha } \cdot L$$
This economy grows not by growth of $x_{i}$, but number of new technologies and varieties $M_{t}$.

### Allowing choice of work
Now we allow people to choose to work in either **R&D** ($L_{R}$) or **production** ($L_{G}$)
$$L=L_{R}+L_{G}=\text{fixed}$$
$$Y_{t}=L_{G}^{1-\alpha }\int_{0}^{M_{t}}(x_{i})^{\alpha }\text{ d}i$$
Intermediate goods will be priced as
$$P_{i}=\partial _{x_{i}}Y_{T}=\alpha L^{1-\alpha }_{G}x_{i}^{\alpha -1}$$
$$x_{i}^{*}=\alpha ^\frac{2}{1-\alpha }L_{G}=\text{fixed over time}$$
$$\Pi ^{*}= \alpha L^{1-\alpha }_{G}(x_{i}^{*})^{\alpha} -x_{i}^{*}= \frac{1-\alpha }{\alpha }\alpha ^{\frac{2}{1-\alpha }}L_{G}$$
$$\begin{align*}
GDP_{t}&= Y_{t}-X_{t}=Y_{t}-\int_{0}^{M_{t}}x_{i}^{*}\text{ d}i\\
&= M_{t}(L_{G}^{1-\alpha }(x^{*})^{\alpha }-x^{*})
\end{align*}$$
	only $M_{t}$ varies with time. 
Research sector:
$$\Delta M_{t}= \partial _{t}M_{t}=M_{t}\cdot \lambda L_{R}$$
	number of new ideas= existing ideas* productivity of workers * number of workers in R&D
$$g_{M}= \frac{\Delta M_{t}}{M_{t}}=\lambda \cdot L_{R}$$
wages in production sector:
$$W_{t}= \partial _{L_{G}}Y_{t}=(1-\alpha )\frac{Y_{t}}{L_{G}}$$
in equilibrium: wages in R&D = wages in production
$\frac{\Pi ^{*}}{r}$
Cost of new technology = $L_{R}\cdot W_{t}$
Zero profits in R&D:
$$\begin{align*}
\frac{\Pi ^{*}}{r}M_{t}\lambda L_{R}&= L_{R}\cdot W_{t}\\
r&= \frac{\Pi ^{*}\lambda M_{t}}{W_{t}}
\end{align*}$$
$$W_{t}=(1-\alpha )M_{T}(L_{G}^{1-\alpha }(x^{*})^{\alpha }-x^{*})$$
end up with
$$g_{M}=g_{Y}=\Delta \%C=g_{C}=r= \alpha \lambda L_{G}$$
$$\lambda L_{R}=g=r=\alpha \lambda L_{G}$$
	and $L_{R}+L_{G}=L$. 
Solving these two,
$$g= \frac{\alpha \lambda }{1+\alpha }L$$
Growth function of
* Efficiency of research workers $\lambda$
* Total working population $L$
**Scale effect:** Bigger economy => bigger growth

Let population grow over time
$$Y_{t}= \left(\frac{L_{t}}{M_{t}^{\phi }} \right)^{1-\alpha }\int _{0}^{M_{t}}(x_{i})^{\alpha }\text{ d}i$$
We added $\frac{1}{M_{t}^{\phi }}$ since more varieties spreads your attention. $\phi >0$.

We can assume that 
$$\Delta M_{t}=\partial _{t}M_{t}=\lambda _{t}RM_{t}^{-(1-\phi )}$$
Higher $M_{t}$:
	Good: IRS
	Bad: crowd out attention
	as knowledge gets specialized, harder to find revolutionary ideas

Some algebra and we find that the growth rate is given by
$$g=(z-\phi )n>n$$
where $n= \frac{\Delta L_{t}}{L_{t}}$, **semi-endogones growth**
	independent of a lot
	not endo since if population does not grow, economy does not grow
