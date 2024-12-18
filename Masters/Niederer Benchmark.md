The benchmark found in \cite{niederer}, which will be referred to as the Niederer benchmark, is the first cardiac tissue electrophysiology simulation benchmark with the goal to generate a consensus gold-standard converged solution. 

## Problem description
The benchmark aims to be unambiguously defined with minimal definition. Therefore, the simpler monodomain equations \ref{} were used. The domain was defined to a 3-dimensional rectangular slab with dimensions $3\times7\times20 \text{ mm}$ and transversely isotropic. An illustration of the domain is given in \ref{fig:}.

The conductivities are anisotropic, modeling fibers directed in the long ($20\text{ mm}$) direction. The intracellular and extracellular conductivities in the longitudinal direction were defined to be $\sigma_{l,i}=0.17\,\mathrm{Sm^{-1}}$ and $\sigma_{l,e}=0.62\,\mathrm{Sm^{-1}}$, respectively. In the transversal directions ($3\text{ mm and }7\text{ mm}$), the conductivities were $\sigma_{t,i}=0.019\,\mathrm{Sm^{-1}}$ and $\sigma_{t,e}=0.24\,\mathrm{Sm^{-1}}$. Then, the conductivity tensor as it appears in \ref{} is
$$
\begin{equation}
M=\frac{1}{C_{m}\chi}\begin{bmatrix}
\sigma_{t} & 0 & 0 \\
0 & \sigma_{t} & 0 \\
0 & 0 & \sigma_{l}
\end{bmatrix},
\end{equation}
$$
where, as in \ref{}, $\sigma_{t}=\frac{\sigma_{t,i}\sigma_{t,e}}{\sigma_{t,i}+\sigma_{t,e}}$ and $\sigma_{l}=\frac{\sigma_{l,i}\sigma_{l,e}}{\sigma_{l,i}+\sigma_{l,e}}$. Notice that since 
$$
\begin{equation}
\frac{\sigma_{l,e}}{\sigma_{l,i}}\approx3.64\neq \frac{\sigma_{t,e}}{\sigma_{t,i}}\approx12.63,
\end{equation}
$$
the assumption of equal anisotropy rates $M_{e}=\lambda M_{i}$ is not valid. Despite this, the monodomain equations \ref{} are still used in the benchmark as they still seem to give a "good enough" approximation to the bidomain equations. \todo{utdype?}

A stimulation current was defined in the lower corner of the box