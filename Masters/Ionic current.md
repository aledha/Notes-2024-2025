For a given ion, there are two driving forces that contribute to the flux across the membrane: diffusion and the electric force. For a an ion $S$ and intracellular and extracellular concentrations $[S]_{i},[S]_{e}$, the chemical potential inside the membrane is \cite{mathphys, p. 81}
$$
\begin{equation}
G_{S,i}=G^0_{S}+RT\ln([S]_{i})+zFu_{i},
\end{equation}
$$
while the potential outside is
$$
\begin{equation}
G_{S,e}=G^0_{S}+RT\ln([S]_{e})+zFu_{e}.
\end{equation}
$$
At equilibrium, the potentials are equal:
$$
\begin{align}
G^0_{S}+RT\ln([S]_{i})+zFu_{i} & =G^0_{S}+RT\ln([S]_{e})+zFu_{e} \nonumber \\
zFv_S & =RT\ln\left( \frac{[S]_{e}}{[S]_{i}} \right) \nonumber \\
v_S & = \frac{RT}{zF}\ln\left( \frac{[S]_{e}}{[S]_{i}} \right) \nonumber  \\
v_S & =\frac{kT}{zq}\ln\left( \frac{[S]_{e}}{[S]_{i}} \right), %\label{eq:nernst}
\end{align}
$$
where $k$ is Boltzmann's constant, $q$ is the ion charge, and $T$ is the temperature. \ref{eq:nernst} is called the Nernst equilibrium potential \cite{mathphys, p. 81}. If the ion $S$ is free to travel across the membrane and the transmembrane potential is different to $v_S$, there will be a current of $S$ to restore the potential to $v_S$. A simple model is a linear relationship between the current of $S$ and the transmembrane potential \cite{mathphys}
$$
\begin{equation}
I_{S}=g_{S}(v-v_S), %\label{eq:Is}
\end{equation}
$$
where $g_{S}$ is the membrane conductance.

\ref{eq:Is} holds only when the channels for ion $S$ are open, which is generally not the case. The channels are controlled by channel gates that may open or close depending on the voltage. We must adjust \ref{eq:Is} to 
$$
\begin{equation}
I_{S}=p_{S}\overline{g_{S}}(v-v_{S}),
\end{equation}
$$
where $p_{S}$ is the proportion of open channels for $S$ and $\overline{g_{S}}$ is the maximum conductance. 

Let $\alpha_{S}$ be the rate of opening and $\beta_{S}$ be the rate of closing, where both rates may depend on the potential. Then, by the law of mass action, the proportion of open channels is governed by the differential equation \cite{computing}
$$
\begin{equation}
\frac{\text{d}p_{S}}{\text{d}t} =\alpha_{S}(v)(1-p_{S})-\beta_{S}(v)p_{S}.
\end{equation}
$$
---
Most ion channels consist of several subunits such that the channel is open only if all of the subunits are open. For example, the Hodgkin-Huxley model \cite{HH} assumes that the potassium channel consists of four identical subunits controlled by the gating variable $n$:
$$
\begin{align}
I_\text{K} & =\bar{g}_{K}n^4(v-v_\text{K}), \\
\frac{\text{d}n}{\text{d}t}  & =\alpha_{n}(1-n)-\beta_{n}n,
\end{align}
$$
while the sodium channel consists of two different subunits controlled by the gating variables $m$ and $h$:
$$
\begin{align*}
I_\text{Na} & =\bar{g}_\text{Na}m^3h(v-v_\text{Na}), \\
\frac{\text{d}m}{\text{d}t}  & =\alpha_{m}(1-m)-\beta_{m}m, \\
\frac{\text{d}h}{\text{d}t}  & =\alpha_{h}(1-h)-\beta_{h}h.
\end{align*}
$$
The Hodgkin-Huxley model also includes a leakage current that is assumed to always be open:
$$
\begin{equation*}
I_\text{L}=\overline g_\text{L}(v-v_\text{L}).
\end{equation*}
$$
The ionic current is the sum of the sodium, potassium, and leakage current:
$$
\begin{equation}
I_\text{ion}  =I_\text{Na}+I_\text{K}+I_\text{L}.
\end{equation}
$$

The rates of opening and closing $\alpha_{n},\beta_{n},\alpha_{m},\beta_{m},\alpha_{h},$ and $\beta_{h}$ are all functions of the potential $v$ and can be found in \cite{HH}. The gating variables $n$, $m$, and $h$ take values between 0 and 1 and are governed by ordinary differential equations. 

Ionic current models can, in general, be written as
$$
\begin{align}
I_\text{ion} & =I_\text{ion}(v,s), \\
\frac{ \partial s }{ \partial t }  & =f(s,v,t),
\end{align}
$$
where $s$ represents the set of gating variables governed by a system of ordinary differential equations $f(s,v,t)$.

The Hodkin-Huxley model has only three such gating variables, but some models are more complex and include greater physiological detail at the cost of computational ease. The ten Tusscher-Panfilov cell model \cite{ten_tusscher} will be applied in section \ref{sec:} and includes 19 state variables and three cell types. 

In summary, the monodomain model in a domain $H$ are described by the system
$$
\begin{align}
    \nabla \cdot (M\nabla v)+I_{\text{stim}} &= \chi C_{m}\frac{\partial v}{\partial t}+\chi I_{\text{ion}}(v,s), &x\in H, \label{eq:monomain}\\
    \frac{\partial s}{\partial t}&= f(s,v,t),&x\in H,\label{eq:monoode}\\
    n \cdot (M\nabla v)&= 0, &x\in \partial H\label{eq:monobc}.
\end{align}
$$


