There are three types of muscle cells; skeletal muscle, cardiac muscle, and smooth muscle. 
Each muscle cell consists of several cylindrical structures called *myofibrils*, which consists of individual contractile units call *sarcomeres*. The sarcomeres, depicted in figure \ref{}, consists of thin filaments and thick filaments. The thin filaments contain the proteins *actin*, *tropomyosin*, and *troponin C*,  while the thick filaments contain the protein *myosin*. For a muscle to contract, myosin must bind to actin to form whats known as a *crossbridge*, which bends in order to pull the thin filament along the thick filament. The bending of the crossbridge is called a *power stroke*. 

The tropomyosin form the backbone of a double-stranded helix that both the actin and troponin are bound to. Troponin blocks the binding sites on the actin, preventing the forming of a crossbridge. When the intracellular calcium concentration is high, troponin binds to calcium ions and allow the forming of a crossbridge.

The cell membrane has several ion channels that are voltage dependent. When the action potential reaches a cell, the calcium ion channels are opened, which results in a higher intracellular concentration of calcium. 

There are three main stages in muscle activation: the action potential (which will be discussed in Section \ref{sec:}), the calcium ion transient, and the contraction \cite{mathphys}.

![[Pasted image 20250123154453.png]]
(figure ref Finsberg)
![[Pasted image 20250123155544.png]]
(figure ref mathphys)


## Land model
Denote $\text{CaTRPN}$ as the fraction of troponin C units bound to calcium. The relationship between $\text{CaTRPN}$ and the concentration of intracellular free calcium ($[\mathrm{Ca^{2+}}]_{i}$) is modeled as 
$$
\begin{equation}
\frac{\text{d}\text{CaTRPN}}{\text{d}t} =k_\text{TRPN} \left( \left( \frac{[\mathrm{Ca^{2+}}]_{\text{i}}}{[\mathrm{Ca^{2+}}]_\text{i,T50}} \right)^{\eta _\text{TRPN}}(1-\text{CaTRPN})-\text{CaTRPN} \right),
\end{equation}
$$
where $k_\text{TRPN}$ and $\eta _\text{TRPN}$ are constants, and $[\mathrm{Ca^{2+}}]_\text{i,T50}$ represents the calcium sensitivity as
$$
\begin{equation}
[\mathrm{Ca^{2+}}]_\text{i,T50}=[\mathrm{Ca^{2+}}]_\text{i,T50}^{\text{ref}}+\beta_{1}(\min(\lambda,1.2)-1)
\end{equation}
$$

The Land model details the active tension as
$$
\begin{equation}
T_{a}=h(\lambda)\frac{T_{ref}}{rs}((1+\zeta_{s})S+\zeta_{w}W),
\end{equation}
$$
where $T_\text{ref}$ and $rs$ are constants and
$$
\begin{align}
h(\lambda) & =\max(0,h'(\min(\lambda,1.2))), \\
h'(\lambda) & =1+\beta_{0}(\lambda+\min(\lambda,0.87)-1.87),
\end{align}
$$
where $\beta_{0}$ is also a constant.  $W$ and $S$ represent the fraction of myosin binding sites pre- and post-powerstroke, respectively. $\zeta_{s}$ and $\zeta_{w}$ represent the distortion of crossbridges in the $S$ and $W$ states, respectively.

The distortions are modeled as
$$
\begin{align}
\frac{\text{d}\zeta_{s}}{\text{d}t}  & =A_{s}\frac{\text{d}\lambda}{\text{d}t} -c_{s}\zeta_{s}, \\
\frac{\text{d}\zeta_{w}}{\text{d}t}  & =A_{w}\frac{\text{d}\lambda}{\text{d}t} -c_{w}\zeta_{w},
\end{align}
$$
where $A_{s}$, $c_{s}$, $A_{w}$, and $c_{w}$ are constants.

For myosin to bind to actin, the binding site must be in an unblocked state. 
The transition between the fraction of myosin binding sites pre- and post-powerstroke are modeled by
$$
\begin{align}
\frac{\text{d}W}{\text{d}t}  & =k_\text{uw}U-k_\text{wu}W-k_\text{ws}W-\gamma _\text{wu}W, \\
\frac{\text{d}S}{\text{d}t}  & =k_\text{ws}W-k_\text{su}S-\gamma _\text{su}S,
\end{align}
$$
where 