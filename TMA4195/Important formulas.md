## Perturbation theory
[[TMA4195/Exercises/Exercise 4#Q1|Exercise 4]] 
```ad-note
title: Matching Condition
collapse: open
When $Y(\eta)$ is the inner solution and $y(x)$ is the outer solution:
$$\lim_{\eta  \to \infty}Y(\eta )= \lim_{x \to 0}y(x)$$
```

```ad-note
title: Uniform solution
collapse: open
Sum up the inner and outer solution and subtract the limit:
$$y^u= y(x)+Y\left(\frac{x}{\varepsilon }\right)-\lim_{x \to 0}y(x)$$

```

```ad-note
title: Stability of equilibrium points
1. If $\det J(\mathbf x_{e})<0\quad\implies\quad$ unstable
2. If $\det J(\mathbf x_{e})>0$
	1. $\text{trace} J(\mathbf x_{e})>0\quad\implies\quad$ unstable
	2. $\text{trace} J(\mathbf x_{e})<0\quad\implies\quad$ asymptomatically stable
	3. $\text{trace} J(\mathbf x_{e})=0\quad\implies\quad$ stable

When $n=1$, the equilibrium point is stable if $f'(u)<0$.

```
