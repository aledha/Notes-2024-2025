In this section, we will derive a simplified electro-mechanical cardiac model that is significantly numerically cheaper to compute than the full three-dimensional model \eqref{eq:}.

We use the Ten Tusscher \cite{} cell model, the monodomain equations, and the Land model \cite{}, to describe the electrophysiological (EP) activity in a domain $\Omega$, as well as the coupling to the mechanical model. These can be summarized as
$$
\begin{align}
\nabla \cdot(\mathbf{M}\nabla v) & =\chi C_{m}\frac{ \partial v }{ \partial t } +\chi I_\text{ion}(v,s), & \mathbf{x}\in \Omega , \\
\frac{ \partial s }{ \partial t } & =f(s,v,\lambda,t), & \mathbf{x}\in \Omega, \\
\mathbf{n}\cdot(\mathbf{M}\nabla v) & =0, &\mathbf{x}\in \partial\Omega ,
\end{align}
$$
where $s$ is a collection of cell states and $v$ is the transmembrane potential. The Land model is included in system of ordinary differential equations \eqref{eq:}, such that $T_{a}$ can be computed from a selection of the cell states $s$. \eqref{eq:} and \eqref{eq:} must, in general, be solved at every point in the domain.

With the assumption of a uniform electrical activation $I_\text{stim}$ and constant $\lambda$ for each time $t$, we want to show that if $v$ and $s$ are spatially constant at $t=0$, they will remain spatially constant for every time $t$. 

Assume that $v$ and $s$ are constant at $t=0$. Then it is easy to see that $\frac{ \partial s }{ \partial t }$ is constant at $t=0$. We also get that $\nabla v=\boldsymbol{0}$ at $t=0$, which reduces the monodomain equation \eqref{eq:} to
$$
\begin{equation}
\frac{ \partial v }{ \partial t } =-\frac{1}{C_{m}}I_\text{ion}(v,s)\quad \text{for } t=0,
\end{equation}
$$
which also is constant across $\Omega$. Since $\frac{ \partial s }{ \partial t }$ and $\frac{ \partial v }{ \partial t }$ are spatially constant at $t=0$, they will remain constant at all times $t$. Further, \eqref{eq:} holds for all times $t$, and since $\nabla v=\boldsymbol{0}$ for all $t$, the boundary condition \eqref{eq:} is always satisfied. 

The numerical benefits from these assumptions are major. The nonlinear partial differential equation \eqref{eq:} is reduced to one ordinary differential equation \eqref{eq:}, and the system of ordinary differential equations \eqref{eq:} needs only to be solved at one point rather than every point/node in the domain. This is useful in analyzing stability properties of the full three-dimensional model. 

---
Using the simplified model described above, we can solve for an active tension $T_{a}$. Now, we wish to derive a scheme to solve for the stretch ratio $\lambda$.

Let $\Omega$ be a cuboidal slab, with fiber direction $\mathbf{f}_{0}=\begin{bmatrix}1&0&0\end{bmatrix}^T$. We assume that the slab is transversely isotropic and incompressible, which leads to a diagonal deformation matrix of the form
$$
\begin{equation}
\mathbf{F}=\begin{bmatrix}
\lambda & 0 & 0 \\
0 & \frac{1}{\sqrt{ \lambda }} & 0 \\
0 & 0 & \frac{1}{\sqrt{ \lambda }} 
\end{bmatrix},
\end{equation}
$$
and $J=\det \mathbf{F}=1$. The right Cauchy-Green deformation tensor becomes
$$
\begin{equation}
\mathbf{C}=\begin{bmatrix}
\lambda^2 & 0 & 0 \\
0 & \frac{1}{\lambda} & 0 \\
0 & 0 & \frac{1}{\lambda} 
\end{bmatrix}.
\end{equation}
$$
Then, the invariants simplify to
$$
\begin{align}
I_{1} & =\mathrm{Tr}\mathbf{C}=\lambda^2+2\lambda^{-1}, \\
I_{4\mathbf{f}_{0}} & =\mathbf{f}_{0}\cdot(\mathbf{C}\mathbf{f}_{0})=\lambda^2.
\end{align}
$$
Substitution into the passive and active strain-energy functions gives
$$
\begin{equation}
\Psi_{p}(I_{1},I_{4\mathbf{f}_{0}})  = \frac{a}{2b}\bigg(e^{ b(\lambda^2 +2\lambda^{-1}-3) }-1\bigg)  + \frac{a_{f}}{2b_{f}}\bigg(e^{ b_{f}(\lambda^2-1)^2_{+}}-1\bigg).
\end{equation}
$$
The passive first Piola-Kirchoff stress components are
$$
\begin{align}
(\mathbf{P}_{p})_{11} & =\frac{ \partial \Psi_{p} }{ \partial \lambda } +Jp(\mathbf{F}^{-T})_{11} \\
 & = \frac{a}{2}(2\lambda -2\lambda^{-2})e^{ b\left( \lambda^2 +2\lambda^{-1}-3 \right) }+ a_{f}(\lambda^2-1)_{+}2\lambda e^{ b_{f}(\lambda^2-1)^2_{+} }+\frac{Jp}{\lambda} \\
  & =a(\lambda-\lambda^{-2})e^{ b(\lambda^2+2\lambda^{-1}-3) }+2\lambda a_{f}(\lambda^2-1)_{+}e^{ b_{f}(\lambda^2-1)_{+}^2 }+p\lambda^{-1},\\
(\mathbf{P}_{p})_{22}=(\mathbf{P}_{p})_{33} & =\frac{ \partial \Psi_{p} }{ \partial \left( \frac{1}{\sqrt{ \lambda }} \right) }  + Jp(\mathbf{F}^{-T})_{22}\\
 & =\frac{ \partial \lambda }{ \partial \left( \frac{1}{\sqrt{ \lambda }} \right) } \frac{ \partial \Psi_{p} }{ \partial \lambda } +Jp(\mathbf{F}^{-T})_{22} \\
 & = (-2\lambda^{3/2})\left[ a(\lambda-\lambda^{-2})e^{ b(\lambda^2+2\lambda^{-1}-3) }+2\lambda a_{f}(\lambda^2-1)_{+}e^{ b_{f}(\lambda^2-1)_{+}^2 } \right] +p\sqrt{ \lambda },
\end{align}
$$
where we have used the chain rule and
$$
\begin{equation}
\frac{ \partial \lambda }{ \partial\left(  \frac{1}{\sqrt{ \lambda }} \right) } =\frac{ \partial \gamma^{-2} }{ \partial \gamma } =-2\gamma^{-3}=-2\lambda^{3/2}.
\end{equation}
$$
The active Cauchy stress tensor is given by
$$
\begin{equation}
\boldsymbol{\sigma}_{a}=\text{diag}\{T_{a}, \eta T_{a},\eta T_{a}\},
\end{equation}
$$
and is also related to the first Piola-Kirchoff stress by
$$
\begin{equation}
\mathbf{P}_{a}=J\boldsymbol{\sigma}_{a}\mathbf{F}^{-T}\implies \boldsymbol{\sigma}_{a}=\mathbf{P}_{a}\mathbf{F}^T.
\end{equation}
$$

We assume that the slab is unloaded, and we ignore body and inertia forces, such that the active and passive stresses balances at all points:
$$
\begin{equation}
\mathbf{P}=\mathbf{P}_{p}+\mathbf{P}_{a}=0.
\end{equation}
$$
Combination of \eqref{} gives
$$
\begin{equation}
\text{diag}\{T_{a},\eta T_{a},\eta T_{a}\}=-\frac{1}{J}\mathbf{P}_{p}\mathbf{F}^T
\end{equation}
$$
Taking the above equation for the first component gives 
$$
\begin{align}
T_{a} & =-\left[ a(\lambda-\lambda^{-2})e^{ b(\lambda^2+2\lambda^{-1}-3) }+2\lambda a_{f}(\lambda^2-1)_{+}e^{ b_{f}(\lambda^2-1)_{+}^2 }+p\lambda^{-1} \right] \lambda \\
 & =-a(\lambda^2-\lambda^{-1})e^{ b(\lambda^2+2\lambda^{-1}-3) }-2\lambda^2 a_{f}(\lambda^2-1)_{+}e^{ b_{f}(\lambda^2-1)_{+}^2 }-p,
\end{align}
$$
and taking the second (and third) component gives
$$
\begin{align}
\eta T_{a} & = - \left[ (-2\lambda^{3/2})\left[ a(\lambda-\lambda^{-2})e^{ b(\lambda^2+2\lambda^{-1}-3) }+2\lambda a_{f}(\lambda^2-1)_{+}e^{ b_{f}(\lambda^2-1)_{+}^2 } \right] +p\sqrt{ \lambda } \right] \frac{1}{\sqrt{ \lambda }} \\
 & =2a(\lambda^2-\lambda^{-1})e^{ b(\lambda^2+2\lambda^{-1}-3) }+4\lambda^2 a_{f}(\lambda^2-1)_{+}e^{ b_{f}(\lambda^2-1)_{+}^2 }-p.
\end{align}
$$
We will further assume that the tension is only activated in the fiber direction such that $\eta=0$. Given an active tension $T_{a}$, we could calculate the corresponding values for $\lambda$ and $p$ by finding the roots of the expressions
$$
\begin{align}
L_{1}(\lambda,p;T_{a}) & =T_{a}+a(\lambda^2-\lambda^{-1})e^{ b(\lambda^2+2\lambda^{-1}-3) }+2\lambda^2 a_{f}(\lambda^2-1)_{+}e^{ b_{f}(\lambda^2-1)_{+}^2 }+p, \\
L_{2}(\lambda,p) & =2a(\lambda^2-\lambda^{-1})e^{ b(\lambda^2+2\lambda^{-1}-3) }+4\lambda^2 a_{f}(\lambda^2-1)_{+}e^{ b_{f}(\lambda^2-1)_{+}^2 }-p.
\end{align}
$$
With these assumptions, we can describe the electrophysiological and mechanical activity in $\Omega$ with the equations
$$
\begin{align}
\frac{ \partial s }{ \partial t }  & =f(s,v,\lambda,t), \\
\frac{ \partial v }{ \partial t }  & =-\frac{1}{C_{m}}I_\text{ion}(v,s), \\
L_{1}(\lambda,p;T_{a}) & =0, \\
L_{2}(\lambda,p)  & =0.
\end{align}
$$

### One way coupling
One simple implementation is to assume that the right-hand sides of the cell model ODEs are independent of $\lambda$: $f(v,s,\lambda)=f(v,s)$. Then, the values computed from the cell model affect the mechanics equations, but the values computed from mechanics equations do not affect the cell model. This can be implemented by setting $\lambda=1$ and $\frac{\text{d}\lambda}{\text{d}t}=0$ for all $t$.

The algorithm for solving this can be described as
1. Solve 

The roots of $L_{1}$ and $L_{2}$ will be found by a Newton solver.