## Known solution
We wish to generate an analytical solution for the electrophysiological problem described by $$
\begin{align}
    %\label{eq:anal mono} 
\nabla \cdot(\mathbf{M}\nabla v)  & =\chi\left( C_{m}\frac{ \text d v }{ \text d t } +I_\text{ion}(\mathbf{s},v) -I_\text{stim}\right) , & \quad \mathbf{X}\in \Omega, \\
    %\label{eq:anal ode} 
\frac{ \text d \mathbf{s} }{ \text d t }  & =\mathbf{f}(\mathbf{s},v,t)  & \mathbf{X}\in \Omega, \\
    %\label{eq:anal monobc} 
\mathbf{n}\cdot(\mathbf{M}\nabla v) & =0,\quad & \mathbf{X}\in \text d \Omega.
\end{align}
$$
Let $\Omega$ be the unit square, and set $\mathbf{M}=\mathbf{I}$ and $\chi=C_{m}=1$. The monodomain equation \eqref{eq:anal mono} reduces to $$
\begin{equation}
%\label{eq:anal mono reduced}
	\nabla^2v=\frac{ \text d v }{ \text d t } +I_\text{ion}(\mathbf{s},v)-I_\text{stim}.
\end{equation}
$$
We let $v$ be analytically defined as $$
\begin{equation}
%\label{eq:anal v}
	v(x,y,t)=\cos(2\pi x)\cos(2\pi y)\sin t.
\end{equation}
$$
The simplest form of the state vector $\mathbf{s}$ is for it to contain one element, so we set $$
\begin{equation}
%\label{eq:anal s}
	\mathbf{s}(x,y,t)=-\cos(2\pi x)\cos(2\pi y)\cos t.
\end{equation}
$$
Notice that $$
\begin{align}
	\frac{ \text d v }{ \text d t }  & = -\mathbf{s}, \\
\frac{ \text d \mathbf{s} }{ \text d t }  & =v.
\end{align}
$$
If we set $I_\text{ion}(\mathbf{s},v)=\mathbf{s}$, the first two terms on the right hand side in equation \eqref{eq:anal mono reduced} cancel such that $$
\begin{equation}
%\label{eq:anal istim deldel v}
	I_\text{stim}=-\nabla^2v.
\end{equation}
$$
The spatial derivatives of $v$ are $$
\begin{align} 
%\label{eq:anal del v}
	\nabla v & =-2\pi\begin{bmatrix}
\sin(2\pi x)\cos(2\pi y)\sin t \\
\cos(2\pi x)\sin(2\pi y)\sin t
\end{bmatrix}, \\
%\label{eq:anal deldel v} 
\nabla^2v & =-8\pi^2\cos(2\pi x)\cos(2\pi y)\sin t.
\end{align}
$$
Notice from equation \eqref{eq:anal del v} that the boundary condition \eqref{eq:anal monobc} is always satisfied. Substituting \eqref{eq:anal deldel v} into \eqref{eq:anal istim deldel v} gives us the expression $$
\begin{equation}
%\label{eq:anal istim}
	I_\text{stim}=8\pi^2\cos(2\pi x)\cos(2\pi y)\sin t.
\end{equation}
$$
For a given $\Delta x$, we discretize the domain with the nodes $x_{i}=i\Delta x$ and $y_{i}=i\Delta x$ for $i=0,\dots,N$, where $N=\frac{1}{\Delta x}$. The domain can then be divided into $N^2$ non-overlapping squares with the nodes as the corners. Fitting two triangles in each square gives us triangulation $\mathcal{T}_{h}$ of the domain. We set the function spaces as $V_{h}=\mathcal{L}_{1}(\mathcal{T}_{h})$ and $S_{h}=Q_{4}(\mathcal{T}_{h})$. 

Let $\Delta t$ be the time step. By interpolating the initial conditions $v(x,y,0)$ and $\mathbf{s}(x,y,0)$ into $V_{h}$ and $S_{h}$, respectively, we can repeatedly solve the nonlinear monolithic system \eqref{eq:ep mono galerkin} for the next iterations of $v$ and $\mathbf{s}$.
## Backward Euler

$$
\begin{align}
%\label{eq:results GRL v}
	v^{n+1} & =v^{n}+g(\mathbf{s}^{n},v^{n}), \\
%\label{eq:results GRL s}
	\mathbf{s}^{n+1} & =\mathbf{s}^{n}+\mathbf{h}(\mathbf{s}^{n},v^{n}),
\end{align}
$$
where $g(\mathbf{s}^n,v^n)=\frac{a_{v}}{b_{v}}(e^{ b_{v}\Delta t }-1)$ with $a_{v}=-\frac{1}{C_{m}}I_\text{ion}(v^n,\mathbf{s}^n)$ and $b_{v}=-\frac{1}{C_{m}} \frac{ \text d I_\text{ion}(\mathbf{s}^n,v^n) }{ \text d v }$, and $\mathbf{h}(\mathbf{s}^{n},v^{n})=\frac{a_{s}}{b_{s}}(e^{ b_{s}\Delta t }-1)$ with $a_{s}=f(\mathbf{s}^n,v^{n})$ and $b_{s}=\frac{ \text d \mathbf{f}(\mathbf{s}^n,v^n) }{ \text d \mathbf{s} }$. Notice that $$
\begin{equation}
%\label{eq:}
	b_{v}=-\frac{1}{C_{m}} \frac{ \text d s }{ \text d v }=0=\frac{ \text d v }{ \text d \mathbf{s} }=b_{s},
\end{equation}
$$
such that $$
\begin{align*}
	g(s^n,v^n) & =a_{v} \Delta t, \\
\mathbf{h} (s^n,v^n) & =a_{s}\Delta t.
\end{align*}
$$
This leads to the simple forward Euler (FE) scheme. 

We consider the backward Euler (BE) scheme applied to the system \eqref{eq:anal v ode}-\eqref{eq:anal s ode} gives
$$
\begin{align}
v^{n+1}-v^n & =-\Delta t\mathbf{s} ^{n+1} ,\\
\mathbf{s} ^{n+1}-\mathbf{s}^n  & =\Delta tv^{n+1}.
\end{align}
$$
We can set up the variational formulation by multiplying with test functions $\phi$ and $\boldsymbol \psi$ and integrating over the domain. The Galerkin formulation for the ODE scheme reads: Given $v^n$ and $s^n$, find $v^{n+1}\in V_{h}$ and $\mathbf{s} ^{n+1}\in S_{h}$ such that 
$$
\begin{align}
%\label{eq:anal Rv} 
R_{v}(v^{n+1},\mathbf{s}^{n+1},\phi;v^n)=\int_{\Omega}(v^{n+1}-v^n +\Delta t s ^{n+1}) \phi \,\text{d} \mathbf{x}& =0 \qquad\forall \phi\in V_{h}, \\
%\label{eq:anal Rs}
R_{\mathbf{s}}(v^{n+1},\mathbf{s}^{n+1},\boldsymbol{\psi};\mathbf{s}^n)=\int_{\Omega}(\mathbf{s}^{n+1}-\mathbf{s}^n -\Delta t v ^{n+1}) \boldsymbol \psi\,\text{d} \mathbf{x} & =0 \qquad\forall \boldsymbol \psi\in S_{h}.
\end{align}
$$
Combining the residuals \eqref{eq:anal Rv}-\eqref{eq:anal Rs} with the residual for the monodomain equation \eqref{eq:R_m} gives us the monolithic nonlinear Galerkin formulation for this problem: Given $(\mathbf{s}^n,v^n)\in[S_{h}]^d\times V_{h}$, find $(\mathbf{s}^{n+1},v^{n+1})\in S_{h}\times V_{h}$ such that$$
\begin{equation}
%\label{eq:anal mono galerkin}
	\begin{pmatrix}
R_{m}(v^{n+1},\phi;v^n) \\
R_{v}(v^{n+1},\phi;\mathbf{s}^n,v^n) \\
R_{\mathbf{s}}(\mathbf{s}^{n+1},\boldsymbol{\psi};\mathbf{s}^n,v^n) 
\end{pmatrix}=\boldsymbol{0},\qquad \forall(\boldsymbol{\psi}^n,\phi^n)\in[S_{h}]^d\times V_{h}.
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
where $g(\mathbf{s}^n,v^n)=\frac{a}{b}(e^{ b\Delta t }-1)$ with $a=-\frac{1}{C_{m}}I_\text{ion}(v^n,\mathbf{s}^n)$ and $b=-\frac{1}{C_{m}} \frac{ \text d I_\text{ion}(\mathbf{s}^n,v^n) }{ \text d v }$. 

Applying the GRL scheme to \eqref{eq:mono s ode} gives the similar expression$$
\begin{equation}
%\label{eq:GRL s}
	\mathbf{s}^{n+1}=\mathbf{s}^{n}+\mathbf{h}(\mathbf{s}^{n},v^{n}),
\end{equation}
$$
where $h_{i}(\mathbf{s}^{n},v^{n})=\frac{a_{i}}{b_{i}}(e^{ b_{i}\Delta t }-1)$ with $a_{i}=f_{i}(\mathbf{s}^n,v^{n})$ and $b_{i}=\frac{ \text d f_{i}(\mathbf{s}^n,v^n) }{ \text d s_{i} }$.

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
where $h_{i}(\mathbf{s}^{n},v^{n},\mathbf{u}^n)=\frac{a_{i}}{b_{i}}(e^{ b_{i}\Delta t }-1)$, with $a_{i}=f_{i}(\mathbf{s}^n,v^{n},\mathbf{u}^n)$ and $b_{i}=\frac{ \text d f_{i}(\mathbf{s}^n,v^n,\mathbf{u}^n) }{ \text d s_{i} }$.

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

$\mathbf{s}_\text{ep}$ and $\mathbf{s}_\text{mech}$
$$
\begin{align}
	\frac{ \partial \mathbf{s}_\text{ep} }{ \partial t }  & =\mathbf{f}_\text{ep}(\mathbf{s}_\text{ep},\mathbf{s}_\text{mech},t), \\
 \frac{ \partial \mathbf{s}_\text{mech} }{ \partial t }  & =\mathbf{f}_\text{mech}(\mathbf{s}_\text{ep},\mathbf{s}_\text{mech},t)
\end{align}
$$