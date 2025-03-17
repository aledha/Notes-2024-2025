We let $M=\mathbf{I}$, $C_{m}=1$, and $\chi=1$ such that
$$
\begin{align}
\nabla \cdot(M\nabla v)  & =\chi C_{m}\frac{ \partial v }{ \partial t } +\chi I_\text{ion}-\chi I_\text{stim}, \\
\frac{ \partial v }{ \partial t } & =\nabla^2 v -I_\text{ion}+I_\text{stim}
\end{align}
$$
## Backward Euler
We have the system
$$
\begin{align}
\frac{\text{d}v}{\text{d}t}  & =-s, \\
\frac{\text{d}s}{\text{d}t}  & =v. \\
\end{align}
$$
The backwards Euler method on the system yields
$$
\begin{align}
v^{n+1}-v^n & =-\Delta ts ^{n+1} ,\\
s ^{n+1}-s^n  & =\Delta tv^{n+1}.
\end{align}
$$
We can set up the variational formulation by multiplying with test functions $v_{t}$ and $s_{t}$ and integrating over the domain. The variational problem reads: Given $v^n$ and $s^n$, find $v^{n+1},s ^{n+1}\in V_{h}$ such that 
$$
\begin{align}
\int_{\Omega}(v^{n+1}-v^n +\Delta t s ^{n+1}) v_{t} \,\text{d} \mathbf{x}& =0 \qquad\forall v_{t}\in V_{h}, \\
\int_{\Omega}(s^{n+1}-s^n -\Delta t v ^{n+1}) s_{t}\,\text{d} \mathbf{x} & =0 \qquad\forall s_{t}\in V_{h}.
\end{align}
$$
We can rewrite this into the following formulation: Given $\mathbf{y}^n=\begin{bmatrix}v^n \\ s^n\end{bmatrix}$, find $\mathbf{y}^{n+1}=\begin{bmatrix}v^{n+1} \\ s ^{n+1}\end{bmatrix}$ such that
$$
\begin{equation}
\int_{\Omega}F(\mathbf{y}^{n+1},\mathbf{y}_{t})\,\text{d} \mathbf{x}=0 \qquad \forall \mathbf{y}_{t}\in V_{h}\times V_{h},
\end{equation}
$$
where $\mathbf{y}_{t}=\begin{bmatrix}v_{t} \\ s_{t}\end{bmatrix}$ and
$$
\begin{equation}
F\left( \begin{bmatrix}v^{n+1} \\ s ^{n+1}\end{bmatrix}, \begin{bmatrix}v_{t} \\ s_{t}\end{bmatrix} \right) =(v^{n+1}-v^n +\Delta t s ^{n+1}) v_{t}+(s^{n+1}-s^n -\Delta t v ^{n+1}) s_{t}.
\end{equation}
$$

