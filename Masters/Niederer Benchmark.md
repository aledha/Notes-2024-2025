The benchmark found in \cite{niederer}, which will be referred to as the Niederer benchmark, is the first cardiac tissue electrophysiology simulation benchmark with the goal to generate a consensus gold-standard converged solution. 

## Problem description
The benchmark aims to be unambiguously defined with minimal definition. Therefore, the simpler monodomain equations \ref{} were used. The domain was defined to a 3-dimensional rectangular slab with dimensions $3\times7\times20 \text{ mm}$ and transversely isotropic. 
A stimulation current was defined in the a cube of dimensions $1.5\times1.5\times1.5 \,\mathrm{mm}$ in the corner with amplitude $50\,000\,\mathrm{\mu Acm^{-3}}$ for $2\text{ ms}$. The metric used to compare the various solvers was the *activation time* of nine pre-defined points in the domain. The activation time of a point is defined as the first time where the transmembrane voltage in that point is larger than zero. A schematic of the domain, stimulation cube and the nine points P1-P9 is shown in \ref{fig:}.

The cell model used for \ref{} was the ten Tusscher & Panfilov model \cite{}. This is a model of human epicardial myocytes that is represented by 19 ordinary differential equations.

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

The surface area to volume ratio was $\chi=1400\,\mathrm{cm^{-1}}$ and the membrane capacitance was $C_{m}=1 \,\mathrm{\mu Fcm^{-2}}$. Cell model initial state variables are given in table \ref{table:}.






{"h=0.5, dt=0.05": {"P1": 1.3, "P2": 51.2, "P3": 35.3, "P4": 59.05, "P5": 14.2, "P6": 49.65, "P7": 34.4, "P8": 56.85, "P9": 26.2}}
{"h=0.2, dt=0.05": {"P1": 1.35, "P2": 29.4, "P3": 33.6, "P4": 40.5, "P5": 9.1, "P6": 29.7, "P7": 33.65, "P8": 40.25, "P9": 18.95}}
{"h=0.5, dt=0.01": {"P1": 1.23, "P2": 50.89, "P3": 34.07, "P4": 58.08, "P5": 14.0, "P6": 49.38, "P7": 33.18, "P8": 55.91, "P9": 25.67}}
{"h=0.2, dt=0.01": {"P1": 1.24, "P2": 28.65, "P3": 31.29, "P4": 38.39, "P5": 8.83, "P6": 28.92, "P7": 31.32, "P8": 38.14, "P9": 17.83}}
{"h=0.5, dt=0.005": {"P1": 1.22, "P2": 50.85, "P3": 33.91, "P4": 57.96, "P5": 13.98, "P6": 49.335, "P7": 33.025, "P8": 55.785, "P9": 25.6}}
{"h=0.2, dt=0.005": {"P1": 1.23, "P2": 28.555, "P3": 30.99, "P4": 38.12, "P5": 8.79, "P6": 28.81, "P7": 31.005, "P8": 37.87, "P9": 17.68}}

