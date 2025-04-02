We are interested in modeling the concentration of ions in the cell, specifically the intracellular calcium concentration $[\text{Ca}^{2+}]_{i}$, which is related to the active tension $T_{a}$ with the Land model described in \autoref{}. For an ion $S$, we denote the intracellular and extracellular concentration as $[S]_{i}$ and $[S]_{e}$, respectively. These concentrations are separated by the cell membrane, which prevents direct diffusion. The membrane contains ion channels that allow diffusion of a specific ion, as depicted in \autoref{}. While there are several types of channels, we will discuss $\textit{leakage channels}$ and $\textit{voltage-gated channels}$. Leakage channels are continuously open, while voltage-gated channels opens and closes in response to the transmembrane voltage $v$. The transmembrane voltage is conventionally defined to be the difference of the intracellular potential $v_{i}$ and the extracellular potential $v_{e}$:
$$
\begin{equation}
v=v_{i}-v_{e}.
\end{equation}
$$


![[Pasted image 20250321130135.png|400]]
(figure https://uen.pressbooks.pub/introneuro/chapter/voltage-gated-ion-channels/)


Consider a situation where the membrane is fully permeable to an ion $S$. The chemical potential of the ion inside and outside of the cell is given by cite{mathphys}
$$
\begin{align}
G_{S,i} & =G^0_{S}+RT\ln([S]_{i})+zFv_{i}, \\
G_{S,e} & =G^0_{S}+RT\ln([S]_{e})+zFv_{e},
\end{align}
$$
where $G^0_{S}$ is the standard free energy of $S$, $R$ is the gas constant, $T$ is the temperature, $z$ is the charge of the ion, and $F$ is the Helmholtz free energy. At equilibrium, the chemical potentials must be equal:
$$
\begin{align}
G^0_{S}+RT\ln([S]_{i})+zFv_{i} & =G^0_{S}+RT\ln([S]_{e})+zFv_{e} \\
v_{i}-v_{e} & =\frac{RT}{zF}\ln\left( \frac{[S]_{e}}{[S]_{i}} \right) \\
v_{S} & = \frac{kT}{zq}\ln\left( \frac{[S]_{e}}{[S]_{i}} \right),
\end{align}
$$
where $v_{S}$ is the equilibrium potential, $k$ is Boltzmann's constant with $k=\frac{R}{N_{a}}=\frac{Rq}{F}$, and $N_{a}$ is Avogadro's number. \eqref{eq:} is the $\textit{Nernst-potential}$.

When $v\neq v_{S}$ and the channels for $S$ are open, there will be a flux of $S$ across the membrane, inducing an ionic current $I_{S}$ that restores the transmembrane potential to $v_{S}$. If one assumes that the channel is ohmic, the potential drop due to the ionic current will be $rI_{S}$, where $r$ is the resistance. Then, we can set up a linear relationship between the ionic current and the transmembrane voltage \cite{mathphys}:
$$
\begin{align}
\nonumber
v & =rI_{S}+v_{S} \\
\nonumber 
I_{S} & =\frac{1}{r}(v-v_{S}) \\
%\label{eq:ionic_linear} \\
I_{S} & =g_{S}(v-v_{S}),
\end{align}
$$
where $g_{S}$ is the membrane conductance for the ion $S$.

\eqref{eq:ionic_linear} only holds for open channels, so we must adjust it to account for voltage-gated channels. This can be done by setting $g_{S}=p_{S}\overline{g_{S}}$, where $p_{S}\in[0,1]$ is the proportion of open channels and $\overline {g_{S}}$ is the membrane conductance when all channels are open. Then \eqref{eq:ionic_linear} becomes
$$
\begin{equation}
%\label{eq:ionic_adj}
I_{S}=p_{S}\overline{g_{S}}(v-v_{S}).
\end{equation}
$$
The proportion of open channels $p_{S}$ can be modeled by the ODE
$$
\begin{equation}
\frac{\text{d}p_{S}}{\text{d}t} =\alpha_{S}(v)(1-p_{S})-\beta_{S}(v)p_{S},
\end{equation}
$$
where $\alpha_{S}$ is the rate of opening of channels and $\beta_{S}$ is the rate of closing of channels, and both depend and the transmembrane voltage $v$.



$$
\begin{align}
\frac{ \partial \mathbf{s} }{ \partial t }  & =\mathbf{f}(\mathbf{s},v,t) \\
I_\text{ion} & =I_\text{ion}(v,\mathbf{s})
\end{align}
$$