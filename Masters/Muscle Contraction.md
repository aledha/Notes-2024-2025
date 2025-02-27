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
The Land model \cite{} of human cardiac compression is a one-way coupling between the electrophysiology model with the mechanical model. It relates the intracellular calcium concentration $[\mathrm{Ca^{2+}}]_{\text{i}}$ with the active tension force $T_{a}$.

Denote $\text{CaTRPN}$ as the fraction of troponin C units bound to calcium. The relationship between $\text{CaTRPN}$ and the concentration of intracellular free calcium is modeled as 
$$
\begin{equation}
\frac{\text{d}\text{CaTRPN}}{\text{d}t} =k_\text{TRPN}T \left( \left( \frac{[\mathrm{Ca^{2+}}]_{\text{i}}}{[\mathrm{Ca^{2+}}]_\text{i,T50}} \right)^{\eta _\text{TRPN}}(1-\text{CaTRPN})-\text{CaTRPN} \right),
\end{equation}
$$
where $k_\text{TRPN}$ and $\eta _\text{TRPN}$ are parameters, and $[\mathrm{Ca^{2+}}]_\text{i,T50}$ represents the calcium sensitivity as
$$
\begin{equation}
[\mathrm{Ca^{2+}}]_\text{i,T50}=[\mathrm{Ca^{2+}}]_\text{i,T50}^{\text{ref}}+\beta_{1}(\min(\lambda,1.2)-1),
\end{equation}
$$
where $[\mathrm{Ca^{2+}}]_\text{i,T50}^{\text{ref}}$ and $\beta_{1}$ are also parameters. 

Denote $B$ as the fraction of actin binding sites that are blocked by troponin C, and $U$ as the fraction of actin binding sites that are unblocked and have not formed a crossbridge. A higher value of $\text{CaTRPN}$ would decrease the fraction of blocked sites $B$, which is modeled as
$$
\begin{equation}
\frac{\text{d}B}{\text{d}t} =k_\text{b}\text{CaTRPN}^{-\eta _\text{Tm}/2}U-k_\text{u}\text{CaTRPN}^{\eta_{Tm/2}}B,
\end{equation}
$$
where $k_\text{b}$, $\eta _\text{Tm}$, and $k_\text{u}$ are constants.

Denote $W$ and $S$ as the fraction of myosin binding sites pre- and post-powerstroke, respectively. The transition between the fraction of myosin binding sites pre- and post-powerstroke are modeled by
$$
\begin{align}
\frac{\text{d}W}{\text{d}t}  & =k_\text{uw}U-k_\text{wu}W-k_\text{ws}W-\gamma _\text{wu}W, \\
\frac{\text{d}S}{\text{d}t}  & =k_\text{ws}W-k_\text{su}S-\gamma _\text{su}S,
\end{align}
$$
where $k_\text{uw}$, $k_\text{wu}$, $k_\text{ws}$, and $k_\text{su}$ are constants. $\gamma _\text{wu}$ and $\gamma _\text{su}$ are the unbinding rates, which depends on $\zeta_{w}$ and $\zeta_{s}$, the distortions of crossbridges in the $S$ and $W$ states, respectively, as
$$
\begin{align}
\gamma _\text{wu} & =\gamma_{w} \lvert \zeta_{w} \rvert,  \\
\gamma _\text{su} & =\begin{cases}
\gamma_{s}(-\zeta _{s}-1) & \text{for } \zeta_{s}+1<0, \\
\gamma_{s}\zeta_{s}& \text{for } \zeta_{s}+1>0, \\
0 & \text{otherwise},
\end{cases}
\end{align}
$$
where $\gamma_{w}$ and $\gamma_{s}$ are constants. The distortions are modeled as
$$
\begin{align} 
\frac{\text{d}\zeta_{s}}{\text{d}t}  & =A_{s}\frac{\text{d}\lambda}{\text{d}t} -c_{s}\zeta_{s}, \\
\frac{\text{d}\zeta_{w}}{\text{d}t}  & =A_{w}\frac{\text{d}\lambda}{\text{d}t} -c_w\zeta_{w},
\end{align}
$$
where $A_{s}$, $c_{s}$, $A_{w}$, and $c_{w}$ are also constants.

The Land model models the active tension as
$$
\begin{equation}
%\label{eq:activetension}
T_{a}=h(\lambda)\frac{T_{ref}}{rs}((1+\zeta_{s})S+\zeta_{w}W),
\end{equation}
$$
where $T_\text{ref}$ and $rs$ are constants and
$$
\begin{align}
%\label{eq:hlambda}
h(\lambda) & =\max(0,h'(\min(\lambda,1.2))), \\
%\label{eq:hmarklambda} 
h'(\lambda) & =1+\beta_{0}(\lambda+\min(\lambda,0.87)-1.87),
\end{align}
$$
where $\beta_{0}$ is constant.


