## Anatomy
The main function of the heart is to pump deoxygenated blood into the lungs and pump oxygenated blood to the rest of the body. 

It is divided into four chambers, as depicted in figure (). The two upper chambers are the left and right atria, while the two lower chambers are called the left and right ventricle. The right atrium receives deoxygenated blood from the body, which flows into the right ventricle to then be pumped and distributed to the lungs in order to oxygenate the blood. The left atrium receives oxygenated blood from the lungs and passes it to the left ventricle, which contracts to pump the blood to the rest of the body.

The contraction of the various chambers needs to be intricately choreographed by an estimated 2-3 billion cardiac muscle cells. This is achieved by electrical signals initiated in the sinoatrial node, located above the right atrium. 

The muscle cells are connected by gap junctions that allow flux of ions between cells, leading to an electrical current which effects the transmembrane potential. If the potential reaches a threshold value, the cell undergoes a process called depolarization, which will be described in further detail in (#ref). Stimulation of the cells neighbouring the sinoatrial node will therefore cause a wave of depolarisation to propagate throughout both atria, which in turn signals the muscle cells to contract. The wavefront reaches the ventricles through the atrioventricular node, which delays the propagation of the wavefront slightly. In this way, the atria contract first to pump blood into the relaxed ventricles that then contract after a slight delay. 

The depolarization is an extremely fast process, and is followed by a much slower process known as repolarization, which restores the transmembrane potential to the its resting value. The cycle of depolarization and repolarization is called an action potential. We will see that the speed of the depolarization demands that we have a very small time steps.


## Volume conductor
We start by modeling the body as a volume conductor, where we can express the relation between the electric and magnetic field from one of Maxwell's equations
$$
\nabla \times E +\frac{\partial B}{\partial t}=0.
$$
The temporal variations of the fields are fairly slow compared in the context of volume conductor theory. We can therefor assume that the system is in electromagnetic equilibrium in each instant of time. This assumption is called the *quasi-static assumption*, resulting in the simplification
$$
\nabla \times E=0.
$$
This implies that the electric field may be represented as the gradient of a scalar valued potential $u$:
$$
E=-\nabla u.
$$
The current $J$ in a conductor with an electric field $E$ and with conductivity $M$ is given by the relation
$$
J=ME=-M \nabla u.
$$

If one assumes that there are no current sources or sinks in a small volume $V$, we can set the net flux out of the surface $\partial V$ to zero:
$$\int_{\partial V}\mathbf n \cdot \nabla \cdot (-M \nabla u)\text{ d}S=0,$$

where we can apply the divergence theorem to get
$$
-\int_V \nabla \cdot (-M \nabla u) \text{ d}V=0.
$$

Since $V$ is an arbitrary volume, the integrand must be zero:
$$
\nabla \cdot (M \nabla u)=0.
$$

For 