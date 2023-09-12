We will take a look at **Electrostatics** and Maxwell's equations.
For $E: \mathbb{R}^{3}\to \mathbb{R}^{3}, \quad \rho:\mathbb{R}^{3}\to \mathbb{R}$
$$\begin{align*}
\nabla \cdot E=\rho \quad\text{on }\mathbb{R}^{3}\\
\nabla \times E=0 \quad\text{on }\mathbb{R}^{3}
\end{align*}$$

There exists a $\phi$ such that $E=\nabla \phi$. Then we arrive at Poissons equations
$$\nabla \cdot E=\nabla \cdot (\nabla \phi )=\rho$$
$$\Delta \phi =\rho \tag{3}$$
The physicists way to solve $(3)$ is to interpolate $\rho$ with many point charges,
$$\rho (x)\stackrel{\text{not rigorous}}{=} \sum_{y \in \mathbb{R}^{d}}^{}\rho (y)\cdot  \underbrace{\delta _{y}(x)}_{\text{Point charge at y}}$$
Then our problem becomes
$$\Delta E=\delta _{y}(x)$$