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

\section{Monolithic Solution Methods}

In this section, we wish to develop a \emph{monolithic} scheme for solving the electromechanical problem. This is a scheme that solves the mechanical model and electrophysiology model simultaneously rather than separately. The major obstacle in solving everything simultaneously is the ODE system describing the cell model and the Land model. We must obtain a variational formulation of the ODE system to couple the monodomain equation and the mechanical model into a large nonlinear system. We start by describing a monolithic scheme for electrophysiology in \autoref{subsec:mono ep}, then extend it to electromechanics in \autoref{subsec:mono em}.

\subsection{Electrophysiology} \label{subsec:mono ep}
We wish to derive a variational formulation of the GRL scheme applied to the ODE system
$$
\begin{align}
%\label{eq:mono v ode}
    \frac{ \text{d} v }{ \text{d} t }  & =-\frac{1}{C_{m}}I_\text{ion}(\mathbf{s},v), \\
%\label{eq:mono s ode}
    \frac{ \text{d} \mathbf{s} }{ \text{d} t }  & =\mathbf{f}(\mathbf{s},v,t).
\end{align}
$$
Applying the GRL scheme as described in \autoref{sec:solving odes} to \eqref{eq:mono v ode} gives $$
\begin{equation}
%\label{eq:GRL v}
	v^{n+1}=v^{n}+g(\mathbf{s}^{n},v^{n}),
\end{equation}
$$
where $g(\mathbf{s}^n,v^n)=\frac{a}{b}(e^{ b\Delta t }-1)$ with $a=-\frac{1}{C_{m}}I_\text{ion}(v^n,\mathbf{s}^n)$ and $b=-\frac{1}{C_{m}} \frac{ \partial I_\text{ion}(\mathbf{s}^n,v^n) }{ \partial v }$. 

Applying the GRL scheme to \eqref{eq:mono s ode} gives the similar expression$$
\begin{equation}
%\label{eq:GRL s}
	\mathbf{s}^{n+1}=\mathbf{s}^{n}+\mathbf{h}(\mathbf{s}^{n},v^{n}),
\end{equation}
$$
where $h_{i}(\mathbf{s}^{n},v^{n})=\frac{a_{i}}{b_{i}}(e^{ b_{i}\Delta t }-1)$ with $a_{i}=f_{i}(\mathbf{s}^n,v^{n})$ and $b_{i}=\frac{ \partial f_{i}(\mathbf{s}^n,v^n) }{ \partial s_{i} }$.

To obtain a mixed Galerkin formulation of \eqref{eq:GRL v} and \eqref{eq:GRL s}, we multiply by the test functions $\phi \in V_{h}$, $\boldsymbol{\psi}\in[S_{h}]^d$ and integrate over the domain. The Galerkin formulation is: Given $v^n\in V_{h}$ and $\mathbf{s}^n\in [S_{h}]^d$, find  $v^{n+1}\in V_{h}$ and $\mathbf{s}^{n+1}\in [S_{h}]^d$ such that $$
\begin{align}
	%\label{eq:GRL galerkin v}
	\int_{\Omega}v^{n+1}\phi \,\text{d} \mathbf{X} & =\int_{\Omega}(v^{n}+g(\mathbf{s}^{n},v^{n}))\phi \,\text{d} \mathbf{X}, & \forall \phi \in V_{h}, \\
%\label{eq:GRL galerkin s}
	\int_{\Omega}\mathbf{s}^{n+1}\cdot \boldsymbol{\psi}\,\text{d} \mathbf{X} & =\int_{\Omega}(\mathbf{s}^{n}+\mathbf{h}(\mathbf{s}^{n},v^{n}))\cdot \boldsymbol{\psi} \,\text{d} \mathbf{X}, & \forall \boldsymbol{\psi}\in[S_{h}]^d.
\end{align}
$$
Then, we define the residuals for the ODE system as $$
\begin{align}
	%\label{eq:R_v}
R_{v}(v^{n+1},\phi;\mathbf{s}^n,v^n) & =\int_{\Omega}v^{n+1}\phi \,\text{d} \mathbf{X}  -\int_{\Omega}(v^{n}+g(\mathbf{s}^{n},v^{n}))\phi \,\text{d} \mathbf{X}, \\
%\label{eq:R_s} 
R_{\mathbf{s}}(\mathbf{s}^{n+1},\boldsymbol{\psi};\mathbf{s}^n,v^n) & =\int_{\Omega}\mathbf{s}^{n+1}\cdot \boldsymbol{\psi}\,\text{d} \mathbf{X} -\int_{\Omega}(\mathbf{s}^{n}+\mathbf{h}(\mathbf{s}^{n},v^{n}))\cdot \boldsymbol{\psi} \,\text{d} \mathbf{X},
\end{align}
$$
and the residual for the monodomain equation as $$
\begin{equation}
%\label{eq:R_m}
	R_{m}(v^{n+1},\phi;v^n)=a(v^{n+1},\phi)-L(\phi;v^n),
\end{equation}
$$
where $a$ and $L$ are the bilinear and linear forms defined in \eqref{eq:ep bilinear}-\eqref{eq:ep linear}. Combining \eqref{eq:R_v}-\eqref{eq:R_m} gives us the monolithic Galerkin formulation for the electrophysiology problem: Given $(\mathbf{s}^n,v^n)\in[S_{h}]^d\times V_{h}$, find $(\mathbf{s}^{n+1},v^{n+1})\in[S_{h}]^d\times V_{h}$ such that
$$
\begin{equation}
%\label{eq:mono ep galerkin}
	\begin{pmatrix}
R_{m}(v^{n+1},\phi;v^n) \\
R_{v}(v^{n+1},\phi;\mathbf{s}^n,v^n) \\
R_{\mathbf{s}}(\mathbf{s}^{n+1},\boldsymbol{\psi};\mathbf{s}^n,v^n) 
\end{pmatrix}=\boldsymbol{0},\qquad \forall(\boldsymbol{\psi}^n,\phi^n)\in[S_{h}]^d\times V_{h}.
\end{equation}
$$

\subsection{Electromechanics} \label{subsec:mono em}
Now, the state vector $\mathbf{s}$ contains the cell model ODEs and Land model ODEs.
$$
\begin{align}
%\label{eq:mono v ode}
    \frac{ \text{d} v }{ \text{d} t }  & =-\frac{1}{C_{m}}I_\text{ion}(\mathbf{s},v), \\
%\label{eq:mono s ode}
    \frac{ \text{d} \mathbf{s} }{ \text{d} t }  & =\mathbf{f}(\mathbf{s},v,\mathbf{u}).
\end{align}
$$
The residuals $R_{m}$ and $R_{v}$ remain unaffected from the coupling, but $R_{s}$ takes the form $$
\begin{equation}
%\label{eq:R_s em}
	R_{s}(\mathbf{s}^{n+1},\boldsymbol{\psi};\mathbf{s}^n,v^n,\mathbf{u}^n) =\int_{\Omega}\mathbf{s}^{n+1}\cdot \boldsymbol{\psi}\,\text{d} \mathbf{X} -\int_{\Omega}(\mathbf{s}^{n}+\mathbf{h}(\mathbf{s}^{n},v^{n},\mathbf{u}^n))\cdot \boldsymbol{\psi} \,\text{d} \mathbf{X},
\end{equation}
$$
where $h_{i}(\mathbf{s}^{n},v^{n},\mathbf{u}^n)=\frac{a_{i}}{b_{i}}(e^{ b_{i}\Delta t }-1)$, with $a_{i}=f_{i}(\mathbf{s}^n,v^{n},\mathbf{u}^n)$ and $b_{i}=\frac{ \partial f_{i}(\mathbf{s}^n,v^n,\mathbf{u}^n) }{ \partial s_{i} }$.

The residuals describing the displacement are the same as the formulations \eqref{eq:mech galerkin 1}-\eqref{eq:mech galerkin 2}: $$
\begin{align}
    %\label{eq:mono mech u} 
R_{\mathbf{u}}(\mathbf{u}^{n+1},p^{n+1},\mathbf{s}^{n+1}, \delta \mathbf{u}) & =D_{\delta\mathbf{u}}\Pi(\mathbf{u}^{n+1},p^{n+1},\mathbf{s}^{n+1}), \\
    %\label{eq:mono mech p} 
R_{p}(\mathbf{u}^{n+1},p^{n+1},\mathbf{s}^{n+1}, \delta p) & =D_{\delta p}\Pi(\mathbf{u}^{n+1},p^{n+1},\mathbf{s}^{n+1}).
\end{align}
$$
Note the dependency on $\mathbf{s}^{n+1}$ in equations \eqref{eq:mono mech u}-\eqref{eq:mono mech p}. This comes from active tension $T_{a}(\mathbf{s},\mathbf{u})$ in the Land model.  

The monolithic Galerkin formulation for the electromechanical problem is: Given $(\mathbf{s}^n,v^n,\mathbf{u}^n)\in[S_{h}]^d\times V_{h}\times U_{h}$, find $(\mathbf{s}^{n+1},v^{n+1},\mathbf{u}^{n+1},p^{n+1})\in[S_{h}]^d\times V_{h}\times U_{h}\times P_{h}$ such that $$
\begin{equation}
%\label{eq:mono em galerkin}
	\begin{pmatrix}
R_{m}(v^{n+1},\phi;v^n) \\
R_{v}(v^{n+1},\phi;\mathbf{s}^n,v^n) \\
R_{\mathbf{s}}(\mathbf{s}^{n+1},\boldsymbol{\psi};\mathbf{s}^n,v^n,\mathbf{u}^n)  \\
R_{\mathbf{u}}(\mathbf{u}^{n+1},p^{n+1},\mathbf{s}^{n+1}, \delta \mathbf{u}) \\
R_{p}(\mathbf{u}^{n+1},p^{n+1},\mathbf{s}^{n+1}, \delta p)
\end{pmatrix}=\boldsymbol{0},\qquad \forall(\boldsymbol{\psi}^n,\phi^n,\delta \mathbf{u}, \delta p)\in[S_{h}]^d\times V_{h}\times U_{h}\times P_{h}.
\end{equation}
$$
