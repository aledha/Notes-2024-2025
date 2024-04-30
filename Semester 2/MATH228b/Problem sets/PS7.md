#Do 1a then 1c)
![[Pasted image 20240418142535.png]]

![[Pasted image 20240418142542.png]]
![[Pasted image 20240418142548.png]]
![[Pasted image 20240418142600.png]]

![[Pasted image 20240418142608.png]]

![[Pasted image 20240418142657.png]]
Splitting into a system into first order equations,
$$\begin{align*}
\partial _{t}u + \partial _{x}f(u)-k \partial _{x}\sigma &= 0,\\
\partial _{x}u&= \sigma .
\end{align*}$$
Our Galerkin formulation is: Find $u_{h},\sigma _{h} \in V_{h}$ such that
$$\begin{align*}
\int_{0}^{1} (\partial _{t}u_{h}) v \text{ d}x + \int_{0}^{1}(\partial _{x}f(u_{h})-k\partial _{x}\sigma _{h})v \text{ d}x&= 0\quad\forall\quad v \in V_{h},\\
\int_{0}^{1}(\partial _{x}u_{h})\tau \text{ d}x=\int_{0}^{1}\sigma _{h}\tau \text{ d}x \quad\forall\quad \tau \in V_{h}.
\end{align*}$$
Setting $\tau ,v=\phi _{k}^{i}$ and integration by parts,
$$\begin{align*}
\int_{x_{k-1}}^{x_{k}} (\partial _{t}u_{h}) \phi _{i}^{k} \text{ d}x + \left[(f(u_{h})-k \sigma _{h})\phi _{i}^{k} \right]_{x_{k-1}}^{x_{k}}-\int_{x_{k-1}}^{x_{k}}(f(u_{h})-k\sigma _{h})\partial _{x}\phi _{i}^{k} \text{ d}x&= 0\quad\forall\quad i,k,\\
\left[u_{h}\phi _{i}^{k} \right]_{x_{k-1}}^{x_{k}}-\int_{x_{k-1}}^{x_{k}}u_{h}\partial _{x}\phi _{i}^{k} \text{ d}x=\int_{x_{k-1}}^{x_{k}}\sigma _{h}\phi _{i}^{k} \text{ d}x \quad\forall\quad i,k.
\end{align*}$$
$$\begin{align*}
\int_{x_{k-1}}^{x_{k}} (\partial _{t}u_{h}) \phi _{i}^{k} \text{ d}x + \left[\hat f(u_{0}^{k+1},u_{p}^{k})-k \hat \sigma (\sigma _{0}^{k+1},\sigma _{p}^{k}) \right]\cdot \phi _{i}^{k}(x_{k})\\
-\left[\hat f(u_{0}^{k},u_{p}^{k-1})-k \hat \sigma (\sigma _{0}^{k},\sigma _{p}^{k-1}) \right]\cdot \phi _{i}^{k}(x_{k-1})   
-\int_{x_{k-1}}^{x_{k}}(f(u_{h})-k\sigma _{h})\partial _{x}\phi _{i}^{k} \text{ d}x&= 0\quad\forall\quad i,k,\\
\hat u(u_{0}^{k+1},u_{p}^{k})\phi _{i}^{k}(x_{k})-\hat u(u_{0}^{k},u_{p}^{k-1})\phi _{i}^{k}(x_{k-1})-\int_{x_{k-1}}^{x_{k}}u_{h}\partial _{x}\phi _{i}^{k} \text{ d}x=\int_{x_{k-1}}^{x_{k}}\sigma _{h}\phi _{i}^{k} \text{ d}x \quad\forall\quad i,k.
\end{align*}$$
In the LDG method, we set
$$\begin{align*}
\hat u&= \{u_{h} \}+C_{12} [\![ u_{h} ]\!]\\
\hat \sigma &= \{\sigma _{h} \} + C_{11}[\![ u_{h} ]\!]-C_{12}[\![ \sigma _{h} ]\!]
\end{align*}$$
Setting $C_{11}=0$ and $C_{12}=1/2$,

$$\begin{align*}
\hat u&= \{u_{h} \}+\frac{1}{2} [\![ u_{h} ]\!]\\
\hat \sigma &= \{\sigma _{h} \} + -\frac{1}{2}[\![ \sigma _{h} ]\!]
\end{align*}$$



![[Pasted image 20240418142705.png]]