So far, we have looked at 
## 1 Newton's law
$$\ddot \chi _{*}=-\nabla V(\chi _{*})$$

## 2 Lagrangian mechanics
Find $\chi _{*}$ that minimises
$$\int_{0}^{t}L(\chi ,\dot \chi )\text{ d}s,$$
where $L(x,v)= \frac{1}{2}\lvert v \rvert^{2}-V(x)$

## 3 Hamilton Jacobi Equation
$$\partial_{t}u+H(x,Du)=0,$$
where $H(x,p)=L^{*}(x,v)=\sup_{v\in \mathbb{R}}\{p \cdot v -L(x,v) \}$

## 4 Hamiltonian dynamics
$$\begin{align*}
\dot \chi ^{j}_{*}&= \partial_{p_{j} }H(\chi _{*},\mathbb p_{*})\\
\dot {\mathbb p}_{*}^{j}&= - \partial_{x^{j}}H(\chi _{*}, \mathbb p_{*})
\end{align*}$$

# Relationships
* $2 \quad\implies\quad 3$  comes from the idea to form the minimiser
	   $u=\inf_{\chi \in \mathcal{A}(t,x)}\int_{0}^{t}L(\chi (s),\dot \chi (s))\text{ d}s$ where $\mathcal{A}$ is the admissible set.
* $3 \quad\implies\quad 2$: if $u$ solves HJE, then $\dot \chi _{*}^{j}=D_{p_{j}}H(\chi _{*},Du(\chi _{*}))$ 
* $3 \quad\Leftrightarrow\quad 4$ By use of Method of Characteristics.


# Back to our original problem
We have our initial value problem. With $H$ strictly convex ($D^{2}H(x,p>0$),
$$\begin{cases}
\partial_{t}u+H(x,Du)&=0 \quad &  \text{in }(0,\infty)_{t}\times \mathbb{R}^{d} \\
u&= g & \text{on } \{t=0 \}\times \mathbb{R}^{d}
\end{cases}\tag{2}$$

Note that an alternative way to write $u$ is
$$u(t,x)=\inf_{x \in \mathcal{A(t,x)}}\left\{ \int_{0}^{t}L(\chi (s), \dot \chi (s)) \text{ d}s+ g(\chi (0)) \right\}$$
where $L(x,v)=H^{*}(x,v)=\sup_{p \in \mathbb{R}^{d}}\{p \cdot v-H(x,p) \}$

```ad-summary
title: Definition: Hopf-Lax formula
For a $L=L(v)$ ($L$ independant of $x$) which implies $H=H(p)$, we define
$$u(t,x):= \inf_{y \in \mathbb{R}^{d}}\left\{ L\left(\frac{x-y}{t}\right)+g(t) \right\}$$

```
This is when $\chi (s)= \frac{sx+(t-s)y}{t}y$. 
Moreover, for any $\chi \in \mathcal{A}(t,x)$ with $\chi (0)=y$.

We have gotten rid of the integral. We can show that this new term is bounded by Jensens inequality
$$L \left(\frac{x-y}{t} \right) \le \frac{1}{t}\int _{0}^{t}L(\dot \chi (s))\text{ d}s$$
$$\frac{1}{t}\int_{0}^{t} \dot \chi (s) \text{ d}s= \frac{\chi (t)-\chi (0)}{t}=\frac{x-y}{t}$$
## Properties of Hopf-Lax
1. If $g$ is Lipschitz, then $u(t,x)$ is Lipschitz. (With a different constant)
2. For all $t$ and for almost every $x$, $u$ is differentiable at $(t,x)$ and at such a point, $\partial_{t}u+H(Du)=0$.
	I.e., $u$ is a weak solution to HJE.
3. $u$ is **unique** among a suitable class of weak solutions.
These properties are hard to prove, will do this next semester.