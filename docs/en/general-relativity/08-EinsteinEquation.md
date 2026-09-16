# Connecting Matter and Curvature

## Introduction

In the previous document, [“Real Curvature Revealed by Going Around Once”](./07-CurvatureFromParallelTransport.md), we found the connection from the metric and calculated curvature from the connection.

When we carried a vector around a small closed curve, the Riemann curvature tensor appeared in its mismatch. We then contracted indices to form

$$
R_{\mu\nu}={R^\rho}_{\mu\rho\nu},
\qquad
R=g^{\mu\nu}R_{\mu\nu}
$$

the Ricci tensor and curvature scalar.

So far, however, these calculations started from a given metric.

---

Alice: “We now have a tool for measuring curvature. But what determines how spacetime curves around a star?”

Bob: “The star’s mass should matter. But in special relativity, we considered energy and momentum together as well. We will probably need them here too.”

---

We now turn to finding the metric from the state of matter. The physical law that connects these two is the Einstein equation.

## The Clocks and Rulers of a Freely Falling Observer

Before writing down matter’s energy and momentum, let us decide who measures them and with what clocks and rulers.

First, imagine dropping an entire small laboratory somewhere air resistance can be ignored. Both the observer inside and a small ball released from their hand fall together. If we look only over a sufficiently small region and for a short time, a ball initially at rest relative to the observer appears to float nearby.

In a laboratory on the ground, the ball falls toward the floor. But if the laboratory falls too, that kind of falling is no longer seen between the observer and the ball.

Motion without support from a floor or rope and without forces other than gravity, such as air resistance or rocket thrust, is called **free fall**. Here we consider small observers and objects whose own effect on spacetime and effects due to their size can be ignored.

Free fall does not mean only falling straight toward the ground. A satellite orbiting Earth with its engine off is also in free fall if air resistance and similar effects are ignored.

---

Alice: “On the ground, though, a person standing still looks more like someone who is not experiencing any force.”

Bob: “You can stand because the floor is pushing on your feet. In a laboratory falling together with you, that support is no longer needed.”

---

An accelerometer carried by the observer distinguishes these cases. An accelerometer supported by a floor on the ground does not read zero, whereas an ideally freely falling accelerometer does. Appearing to accelerate in ground-based coordinates is not the same as the observer being pushed.

In Chapter 6, we described the path of an object subject to no forces other than gravity as a spacetime geodesic. Free fall in curved spacetime is motion along such a geodesic. Even if its path looks curved from the ground, the object follows spacetime geometry without changing its own direction of travel.

Now suppose that a freely falling observer measures matter’s energy and momentum at a particular time and place. Take the spacetime point specified by that time and place as the coordinate origin, align the time axis with the observer’s clock, and align the three spatial axes with the observer’s mutually perpendicular rulers. At that point, we can choose coordinates in which the observer is at rest and the metric and connection are

$$
g_{\mu\nu}=\eta_{\mu\nu}=\operatorname{diag}(-1,1,1,1)
=\begin{pmatrix}
-1 & 0 & 0 & 0\\
0 & 1 & 0 & 0\\
0 & 0 & 1 & 0\\
0 & 0 & 0 & 1
\end{pmatrix},
\qquad
\Gamma^\rho_{\mu\nu}=0
$$

This is called a **local inertial coordinate system** adapted to that observer. At this point, relations between clocks and rulers have the same form as in special relativity, so components of energy and momentum can be read just as in special-relativistic measurements.

The word “local” is important. Even though these conditions hold at that point, they do not make spacetime flat throughout the laboratory. Special relativity is a good approximation over a sufficiently small region, but curvature effects appear when the region or observation time is enlarged.

For example, two small balls falling side by side toward Earth gradually approach one another because each heads toward Earth’s center. This relative acceleration between freely falling objects is called a tidal effect. As we saw in Chapter 7, setting the Christoffel symbols to zero at one point cannot remove this effect if curvature remains.

The freely falling observer used from here on measures the state of matter at a point in curved spacetime with their own clocks and rulers. The matter being measured does not itself have to be in free fall alongside that observer.

## What Enters a Small Box

![Alice and Bob observe a floating ball and a clock in a freely falling laboratory](../../../images/general-relativity/08/alice-bob-free-fall.png)

In the local inertial coordinates adapted to the freely falling observer just described, consider a very small imaginary box around the origin. It is not a wall that confines matter, but a boundary introduced to count what enters and leaves. Particles and light can cross its surfaces in either direction.

As before, let the time coordinate be $x^0=w=ct$ and the spatial coordinates be $x^1=x,x^2=y,x^3=z$. The indices $i,j$, which take the values $1,2,3$, denote spatial directions.

First, let $\Delta V$ be the box’s volume and $\Delta E$ the energy it contains, both measured by the observer at the same time. Energy per unit volume,

$$
\varepsilon=\frac{\Delta E}{\Delta V}
$$

is called **energy density**. The energy counted here includes the particles’ rest energy.

Particles in the box also have momentum. If $\Delta p_{\mathrm{total}}^i$ is the $i$-direction component of its total, then

$$
\pi^i=\frac{\Delta p_{\mathrm{total}}^i}{\Delta V}
$$

is the **momentum density**. Here $\pi^i$ denotes momentum density, not the number pi.

Energy density is one quantity, but momentum density has components in three directions. For example, if equal numbers of particles with equal-sized momenta move left and right, their momenta cancel. Their energies, however, add together.

Below, we assume that small differences between individual particles can be averaged out, so densities can be treated as smooth quantities. We also take the box small enough that curvature effects can be ignored.

## Density Alone Does Not Tell Us the Next Moment

Knowing the densities inside the box alone does not tell us its state at the next moment. Light entering from the right increases its energy, while particles leaving to the left carry away both energy and momentum.

So let us consider quantities carried through the box’s surfaces. For a surface perpendicular to the $j$ direction, write $F^j$ for the energy carried net in the positive $j$ direction per unit time and unit area. This is the **energy flux**. Flow in the opposite direction is counted as negative.

For momentum, we must also specify which component of momentum is being carried. Write the $i$-direction momentum carried through a surface perpendicular to the $j$ direction per unit time and unit area as

$$
\Pi^{ij}
$$

The first index $i$ denotes the component of momentum carried, and the second index $j$ denotes the direction through the surface.

For example, $\Pi^{21}$ is $y$-direction momentum carried through a surface perpendicular to the $x$ direction. A particle moving diagonally can cross the surface in the $x$ direction while also carrying $y$-direction momentum.

![A particle crosses a surface perpendicular to the x direction at an angle and carries y-direction momentum](../../../images/general-relativity/08/momentum-flux-21.svg)

The figure is viewed along the $z$ axis, with $x$ to the right and $y$ upward. The surface perpendicular to the $x$ direction appears as a vertical line. The blue arrow shows the particle’s velocity, and the orange arrow shows the $y$ component $p^2$ of its momentum. Even though the orange arrow points upward, the particle carrying it crosses the surface to the right. $\Pi^{21}$ counts the $y$-direction momentum passing through this surface per unit time and unit area.

---

Alice: “Energy flows in three directions, but momentum flux has two indices.”

Bob: “That is because we need to specify not only where it is carried, but also which component of momentum is being carried.”

---

## Counting Particles Moving at the Same Velocity

Let us check the relationship between density and flux with a simple collection of particles. Suppose particles of mass $m$ all move at the same speed in the same direction. That is, every particle has the same velocity vector $\boldsymbol v=(v^1,v^2,v^3)$. This does not mean that the three components $v^1,v^2,v^3$ are equal to one another.

For example, the collection could consist entirely of particles moving with $(v^1,v^2,v^3)=(2,3,0)\,\mathrm{m/s}$.

Let $n$ be the particle number density measured by this observer, $E$ the energy of one particle, and $p^i$ its momentum. Then

$$
\varepsilon=nE,
\qquad
\pi^i=np^i
$$

We simply multiply the number of particles in a unit volume by the amount per particle.

Next, consider a surface of area $\Delta A$ perpendicular to the $j$ direction. First suppose $v^j>0$. During a short time $\Delta t$, the particles that cross this surface are those that were in a region of thickness $v^j\Delta t$ in front of it. The volume of that region is

$$
\Delta V_{\mathrm{pass}}=v^j\Delta t\,\Delta A
$$

so the number of particles that cross is

$$
\Delta N=n v^j\Delta t\,\Delta A
$$


![Particles that cross a surface in a short time are in the region of thickness v^j Δt in front of it. The figure shows the case of velocity perpendicular to the surface.](../../../images/general-relativity/08/particles-crossing.svg)

---

Alice: “We are counting particles crossing a surface, yet we use a volume.”

Bob: “Yes. We consider the region where particles that reach the surface during that time started. Multiplying that volume by the particle number density gives the number that cross.”

---

Since each particle carries energy $E$, the energy flux—energy carried net in the positive $j$ direction per unit time and unit area—is

$$
F^j=\frac{E\Delta N}{\Delta t\,\Delta A}=nEv^j
$$

Similarly, since each particle carries $i$-direction momentum $p^i$,

$$
\Pi^{ij}=\frac{p^i\Delta N}{\Delta t\,\Delta A}=np^iv^j
$$

For $v^j<0$, the same expressions apply if we count the direction across the surface through its sign. Here $i,j$ are fixed, and no sum is taken.

We have now found both the density inside the box and the flux through its surface from the motion of the same particles.

## Putting Energy and Momentum into One Table

In Chapter 6, [“From Four-Velocity to Four-Momentum”](./06-ParallelTransportAndGeodesics.md#from-four-velocity-to-four-momentum), we combined a particle’s energy and momentum into

$$
p^\mu=(E/c,p^1,p^2,p^3)
$$

which is the four-momentum. We would like to combine density and flux into four components in the same way.

So we arrange the quantities as follows.

$$
T^{\mu\nu}=
\begin{pmatrix}
\varepsilon & F^1/c & F^2/c & F^3/c\\
c\pi^1 & \Pi^{11} & \Pi^{12} & \Pi^{13}\\
c\pi^2 & \Pi^{21} & \Pi^{22} & \Pi^{23}\\
c\pi^3 & \Pi^{31} & \Pi^{32} & \Pi^{33}
\end{pmatrix}.
$$

The first index $\mu$ specifies the row, and the second index $\nu$ the column. The first column gives densities inside the box, and the other three columns give fluxes in the respective directions. The first row corresponds to energy, and the remaining three rows to momentum in the three directions.

|  | First column: density | Remaining three columns: flux in each direction |
| --- | --- | --- |
| First row: energy | $\varepsilon$ | $F^j/c$ |
| Remaining three rows: momentum | $c\pi^i$ | $\Pi^{ij}$ |

Rows and columns classify the same components from different viewpoints. A row says “what quantity?”, while a column says “density, or flux in which direction?” The lower-right $3\times3$ block is where momentum rows and flux columns meet. For example, $\Pi^{21}$ lies at the intersection of the row for $y$-direction momentum and the column for flux in the $x$ direction, so it represents flux that carries $y$-direction momentum in the $x$ direction.

The factors of $c$ in the table give every component the same units as energy density. Next, let us verify that this table can be written as one tensor.

## Why It Is a Tensor

Simply arranging quantities in a square does not make them a tensor. Under a coordinate change, they must obey the transformation rule for two upper indices.

Return to the particles all moving at the same velocity. Let $n_0$ be the particle number density measured by an observer moving with them. This density is defined in the particles’ rest frame and is a scalar independent of the choice of coordinates.

In a frame where the particles appear to move with velocity $\boldsymbol v$, the volume of the same collection is Lorentz-contracted along the direction of motion. Therefore its particle number density is

$$
n=\gamma n_0,
\qquad
\gamma=\frac{1}{\sqrt{1-|\boldsymbol v|^2/c^2}}
$$

Also, the particle’s four-velocity and four-momentum are

$$
u^\mu=\frac{dx^\mu}{d\tau}=\gamma(1,v^1/c,v^2/c,v^3/c),
\qquad
p^\mu=mcu^\mu
$$

Here $u^\mu$ is the four-velocity of particles flowing through the box, defined in the same way as $U^\mu$ in Chapter 6. Since $\tau$ has units of distance, $u^\mu$ is dimensionless in these local inertial coordinates. The $v^i$ are the particle’s velocity components measured by the observer who set up the box.

Using these, every component of the table above can be written as

$$
\boxed{T^{\mu\nu}=n_0mc^2\,u^\mu u^\nu}
$$

Indeed, using $E=\gamma mc^2$, $p^i=\gamma mv^i$, and $n=\gamma n_0$ gives

$$
\begin{aligned}
T^{00}&=n_0m\gamma^2c^2=nE=\varepsilon,\\
T^{0j}&=n_0m\gamma^2cv^j=nEv^j/c=F^j/c,\\
T^{i0}&=n_0m\gamma^2v^ic=cnp^i=c\pi^i,\\
T^{ij}&=n_0m\gamma^2v^iv^j=np^iv^j=\Pi^{ij}.
\end{aligned}
$$

Both the quantities counted from densities and those counted from particles crossing a surface are components of the same expression.

Because $u^\mu$ is a four-vector, under a coordinate transformation it becomes

$$
u'^\alpha=\frac{\partial x'^\alpha}{\partial x^\mu}u^\mu
$$

Therefore its product transforms as

$$
T'^{\alpha\beta}
=\frac{\partial x'^\alpha}{\partial x^\mu}
\frac{\partial x'^\beta}{\partial x^\nu}
T^{\mu\nu}
$$

This is exactly the transformation rule for a tensor with two upper indices. In other words, the earlier table was defined by choosing the component arrangement and factors of $c$ so that energy and momentum densities and fluxes transform together as one tensor. Writing it as a product of four-velocities confirms this. The $T^{\mu\nu}$ constructed in this way is called the **energy-momentum tensor**.

Moreover, since $u^\mu u^\nu=u^\nu u^\mu$, this tensor is symmetric. In particular,

$$
T^{0i}=T^{i0}
\quad\Longrightarrow\quad
F^i=c^2\pi^i
$$

Energy flow and momentum density cannot be chosen independently; they are two aspects of the motion of the same particles.

If particles have various velocities, we can separate them into groups with the same velocity and add their contributions. Labeling the groups by $a$ gives

$$
T^{\mu\nu}=\sum_a n_{0,a}m_ac^2 u_a^\mu u_a^\nu
$$

The sum of tensors is also a tensor, and symmetry is preserved. From this particle-based construction, let us next consider gas pressure.

What we derived here is the contribution to energy and momentum carried by massive particles. Light has no rest frame, and the energy of fields that mediate interactions cannot be counted using this particle formula alone. They require different constructions, but their shared role is to combine densities and fluxes.

The tensor transformation rule can still be used after moving to general curved coordinates.

## Pressure Is Also a Transfer of Momentum

Suppose the box contains a gas. Even if the box as a whole is at rest, its molecules are moving about.

For a particle moving in the $x$ direction, both $p^1$ and $v^1$ are positive, so $p^1v^1$ is positive. For a particle moving in the opposite direction, both are negative, and their product is still positive.

Thus, even if the momentum densities of left- and right-moving particles cancel, the momentum flux $T^{11}=\sum_a n_a p_a^1v_a^1$ remains. A gas being at rest as a whole does not mean that no momentum is transferred.

![For both right-moving and left-moving particles, the product of momentum and velocity is positive. Equal groups have canceling momentum densities, but their momentum fluxes add.](../../../images/general-relativity/08/pressure-momentum.svg)

---

Alice: “If the left and right momenta cancel, it feels as though the pressure should disappear too.”

Bob: “For momentum density, we add momenta, but for flux we also count the direction of crossing. A left-moving particle has both negative momentum and negative velocity, so their product is positive. Even if walls are pushed from both sides, the force on each wall remains.”

---

When a molecule hits a wall and bounces back, its momentum changes. The corresponding momentum is transferred to the wall. Momentum transferred per unit time is force, and dividing it by the wall’s area gives pressure.

Pressure is therefore represented as momentum flux.

![Alice and Bob use a transparent gas model to examine particles transferring momentum to a wall](../../../images/general-relativity/08/alice-bob-pressure.png)

For example, $T^{11}$ is the $x$-direction momentum transferred through a surface perpendicular to the $x$ direction per unit time and unit area. Here the direction perpendicular to the surface is the same as the direction of the transferred momentum. Since momentum transfer per unit time is force, $T^{11}$ corresponds to the force per unit area pushing normally on that surface: pressure.

Likewise, $T^{22}$ corresponds to pressure on a surface perpendicular to the $y$ direction, and $T^{33}$ to pressure on a surface perpendicular to the $z$ direction. If an observer at rest with the gas measures the same pressure $P$ in every direction, then

$$
T^{11}=T^{22}=T^{33}=P
$$

The three are equal because the same pressure acts regardless of the orientation of a surface cutting through the gas. If the gas as a whole flows relative to the observer, however, momentum carried by that flow also contributes, so these components cannot simply be read as the pressure $P$ in the gas’s rest frame.

In particular, $T^{xx}$ represents transfer of $x$-direction momentum through a surface perpendicular to the $x$ direction. For $T^{xy}$, $x$-direction momentum along the surface is transferred through a surface perpendicular to the $y$ direction. This is related to stress that tends to slide the surface sideways.

Consider an observer at rest with a fluid who measures the same pressure $P$ in every direction. For a fluid in which viscosity and heat flow can be ignored, in that observer’s local inertial coordinates,

$$
T^{\mu\nu} =
\begin{pmatrix}
\varepsilon & 0 & 0 & 0\\
0 & P & 0 & 0\\
0 & 0 & P & 0\\
0 & 0 & 0 & P
\end{pmatrix}
$$

This can be written as shown. $\varepsilon$ is the energy density including rest energy and internal energy. This idealization is called a perfect fluid.

Even when the gas as a whole is at rest, pressure components remain. In general relativity, curvature is connected not only to mass density, but to the state of matter including energy flow, pressure, and stress. Light and electromagnetic fields also contribute to $T^{\mu\nu}$ because they have energy and momentum.

Below, to match the indices on the curvature side, we also use

$$
T_{\mu\nu}=g_{\mu\alpha}g_{\nu\beta}T^{\alpha\beta}
$$

with lower indices. It is the same tensor with its indices lowered using the metric.

## Changes Inside the Box and Flow Through Its Surfaces

If more energy enters a small box than leaves it, the difference is stored inside the box.

Let us express this balance using the energy density $\varepsilon$ and energy fluxes $F^1,F^2,F^3$ defined above. Here we include all energy of interacting matter and fields, and consider the case in which energy is neither created nor destroyed overall inside the box.

In local inertial coordinates adapted to the observer, take a small box at rest in the coordinates, with side lengths $\Delta x,\Delta y,\Delta z$. Its volume is $\Delta V=\Delta x\Delta y\Delta z$. Take the box and observation time sufficiently small; below, we keep the leading terms when calculating the balance.

### First, Compare the Left and Right Surfaces

First consider only the $x$ direction. Let the left surface be at $x$ and the right surface at $x+\Delta x$, with both areas equal to $\Delta A=\Delta y\Delta z$.

![Energy enters through the left surface of a small box and leaves through its right surface. Fluxes at both surfaces are compared using the same positive x direction.](../../../images/general-relativity/08/energy-balance.svg)

Both arrows in the figure point in the positive $x$ direction. Flow in this direction enters the box at the left surface and leaves it at the right surface. This determines the signs in the balance.

$F^1$ is energy carried per unit time and unit area. Omitting the time and $y,z$ labels, write its value at the left surface as $F^1(x)$ and at the right surface as $F^1(x+\Delta x)$. During a short time $\Delta t$, the energy entering from the left and leaving through the right are, respectively,

$$
\begin{aligned}
\text{inflow from the left}&\simeq F^1(x)\,\Delta A\,\Delta t,\\
\text{outflow to the right}&\simeq F^1(x+\Delta x)\,\Delta A\,\Delta t
\end{aligned}
$$

Therefore, the increase in the box’s energy due to flow through these two surfaces is

$$
\begin{aligned}
\Delta E_x
&\simeq \bigl[F^1(x)-F^1(x+\Delta x)\bigr]\Delta A\,\Delta t\\
&\simeq -\frac{\partial F^1}{\partial x}\Delta x\,\Delta A\,\Delta t\\
&=-\frac{\partial F^1}{\partial x}\Delta V\,\Delta t
\end{aligned}
$$

In the second line, we wrote the difference in flux at two nearby surfaces as

$$
F^1(x+\Delta x)-F^1(x)
\simeq \frac{\partial F^1}{\partial x}\Delta x
$$


For example, if the flux at the right surface is greater than at the left, more leaves than enters, and the box’s energy decreases. In this case $\partial F^1/\partial x>0$, consistently making $\Delta E_x$ negative. If the flux is the same at both surfaces, this pair of surfaces produces no change in the box’s energy even when there is flow.

If $F^1$ is negative, the actual flow is opposite to the arrows. Even then, its sign lets us calculate the balance using the same “left value minus right value.”

### Add the Flows in the Three Directions

There are also two opposing surfaces in each of the $y$ and $z$ directions. The same calculation gives

$$
\Delta E_y\simeq-\frac{\partial F^2}{\partial y}\Delta V\,\Delta t,
\qquad
\Delta E_z\simeq-\frac{\partial F^3}{\partial z}\Delta V\,\Delta t
$$

The increase due to flow through all six surfaces is the sum of these three terms.

On the other hand, since the box’s volume is fixed, its increase in energy can be written using the change in density as

$$
\Delta E_{\mathrm{box}}
\simeq \bigl[\varepsilon(t+\Delta t)-\varepsilon(t)\bigr]\Delta V
\simeq \frac{\partial\varepsilon}{\partial t}\Delta t\,\Delta V
$$

This equals the total increase due to inflow and outflow, so we obtain

$$
\frac{\partial\varepsilon}{\partial t}\Delta V\,\Delta t
=-\left(
\frac{\partial F^1}{\partial x}
+\frac{\partial F^2}{\partial y}
+\frac{\partial F^3}{\partial z}
\right)\Delta V\,\Delta t
$$

as an equality of the leading terms. Dividing both sides by $\Delta V\,\Delta t$ and taking the limit as the box and time interval become small gives

$$
\frac{\partial\varepsilon}{\partial t}
+\frac{\partial F^1}{\partial x}
+\frac{\partial F^2}{\partial y}
+\frac{\partial F^3}{\partial z}
=0
$$

This is the local conservation law for energy. The first term is the rate of increase of energy per unit volume. The sum of the other three terms is the energy flowing out of the box net per unit time and unit volume. Their sum is zero because energy inside the box decreases by the amount that flows out.

### Combine Them Using Tensor Components

Using $T^{00}=\varepsilon$, $T^{0i}=F^i/c$, and $\partial_0=(1/c)\partial_t$, this equation becomes

$$
\partial_\nu T^{0\nu}=0
$$

For momentum, we can use exactly the same argument by replacing energy density and energy flux with momentum density and momentum flux. Since “increase inside the box” plus “net outflow through its surfaces” is zero,

$$
\frac{\partial\pi^i}{\partial t}
+\sum_{j=1}^3\frac{\partial\Pi^{ij}}{\partial x^j}=0
$$

Using $T^{i0}=c\pi^i$ and $T^{ij}=\Pi^{ij}$, this is $\partial_\nu T^{i\nu}=0$. The balances of energy and momentum in the three directions combine into the one equation

$$
\partial_\nu T^{\mu\nu}=0
$$


In general coordinates in curved spacetime, changes in the basis from place to place must also be included. We therefore replace the ordinary derivative with the covariant derivative and write

$$
\boxed{\nabla_\nu T^{\mu\nu}=0}
$$

This is the local conservation law for the energy and momentum of interacting matter and fields taken together. For example, if gas and light exchange energy, the balance includes both.

Lowering the indices and using the compatibility of the covariant derivative with the metric, we can write the same statement as

$$
\nabla^\mu T_{\mu\nu}=0,
\qquad
\nabla^\mu=g^{\mu\alpha}\nabla_\alpha
$$


This does not mean that in every curved spacetime “the total energy of the universe is constant.” Comparing energies at distant places and defining a globally conserved quantity require additional conditions, such as symmetries of spacetime.

## Examining the Divergence of the Ricci Tensor

On the matter side, we found that the energy-momentum tensor

$$
\nabla^\mu T_{\mu\nu}=0
$$

satisfies this equation. Next, let us examine a derivative of the same form for the Ricci tensor on the curvature side.

The quantity $\nabla^\mu R_{\mu\nu}$ that we calculate here is obtained by taking a covariant derivative and then contracting the derivative index with a tensor index. A derivative of this kind is called a **divergence**. We sum over the index $\mu$, leaving one index $\nu$. This is different from examining all components of the covariant derivative $\nabla_\alpha R_{\mu\nu}$.

### Reviewing the Definition of Curvature

In Chapter 7, we constructed the Ricci tensor and the curvature scalar from the Riemann curvature tensor:

$$
R_{\sigma\nu}={R^\rho}_{\sigma\rho\nu},
\qquad
R=g^{\sigma\nu}R_{\sigma\nu}
$$


To make index contractions easier from now on, we also lower the first index of the Riemann curvature tensor using the metric:

$$
R_{\alpha\sigma\mu\nu}
=g_{\alpha\rho}{R^\rho}_{\sigma\mu\nu}
$$

In this form, the definition of the Ricci tensor is

$$
R_{\sigma\nu}
=g^{\alpha\mu}R_{\alpha\sigma\mu\nu}
$$

Here, the first and third indices are contracted with the inverse metric.

### The Bianchi Identity Relating Derivatives of Curvature

Because the Riemann curvature tensor is constructed from the connection, its components cannot be chosen freely. The following relation also holds among covariant derivatives of curvature:

$$
\nabla_\lambda R_{\alpha\sigma\mu\nu}
+\nabla_\mu R_{\alpha\sigma\nu\lambda}
+\nabla_\nu R_{\alpha\sigma\lambda\mu}
=0.
$$

This is called the **differential Bianchi identity**. Holding $\alpha,\sigma$ fixed, it says that the sum of three terms, formed by cyclically permuting the remaining three indices $\lambda,\mu,\nu$, is zero.

This is not a law imposed on the distribution or motion of matter. It is a geometric identity satisfied by curvature constructed from the metric and connection used so far. The identity itself is derived from the definition of curvature in the end-of-chapter [“Appendix: Derivation of the Differential Bianchi Identity”](#appendix-derivation-of-the-differential-bianchi-identity). Here, let us use index contraction to see how this identity determines the divergence of the Ricci tensor.

We will also use the following properties. Their derivations can be checked in the end-of-chapter [“Appendix: Symmetries of the Curvature Tensor”](#appendix-symmetries-of-the-curvature-tensor).

$$
R_{\alpha\sigma\mu\nu}
=-R_{\sigma\alpha\mu\nu},
\qquad
R_{\alpha\sigma\mu\nu}
=-R_{\alpha\sigma\nu\mu},
\qquad
R_{\sigma\nu}=R_{\nu\sigma}.
$$

The first two state that the Riemann curvature tensor is antisymmetric in its first two indices and in its last two indices. The last equation is the symmetry of the Ricci tensor. These properties also follow from using a connection that is compatible with the metric and symmetric in its lower two indices.

### Obtaining the Ricci Tensor in the First Contraction

Multiply the Bianchi identity by $g^{\alpha\mu}$ and sum over $\alpha,\mu$. Because the covariant derivative of the metric is zero, we may move the inverse metric inside the covariant derivative.

First, consider the first term of the Bianchi identity, $\nabla_\lambda R_{\alpha\sigma\mu\nu}$. We multiply it by $g^{\alpha\mu}$ in order to contract the first and third indices of the curvature tensor and form the Ricci tensor.

This time, however, we are contracting the covariant derivative of curvature rather than curvature itself. So let us use the product rule to check that the inverse metric can be moved inside the covariant derivative.

$$
\nabla_\lambda\left(g^{\alpha\mu}R_{\alpha\sigma\mu\nu}\right)
=(\nabla_\lambda g^{\alpha\mu})R_{\alpha\sigma\mu\nu}
+g^{\alpha\mu}\nabla_\lambda R_{\alpha\sigma\mu\nu}
$$

The covariant derivative of the inverse metric is also zero, so the first term on the right-hand side vanishes. Therefore,

$$
g^{\alpha\mu}\nabla_\lambda R_{\alpha\sigma\mu\nu}
=\nabla_\lambda\left(g^{\alpha\mu}R_{\alpha\sigma\mu\nu}\right)
$$

The expression in parentheses is precisely the definition of the Ricci tensor reviewed at the beginning of this section:

$$
g^{\alpha\mu}R_{\alpha\sigma\mu\nu}=R_{\sigma\nu}
$$

Summing over $\alpha,\mu$ removes these two indices and leaves $\sigma,\nu$. Substituting this gives

$$
g^{\alpha\mu}\nabla_\lambda R_{\alpha\sigma\mu\nu}
=\nabla_\lambda R_{\sigma\nu}
$$

Thus, the contraction of the first term is the covariant derivative of the Ricci tensor in the $x^\lambda$ direction.

For the second term, $g^{\alpha\mu}\nabla_\mu=\nabla^\alpha$, so

$$
g^{\alpha\mu}\nabla_\mu R_{\alpha\sigma\nu\lambda}
=\nabla^\alpha R_{\alpha\sigma\nu\lambda}
$$

This follows directly.

For the third term, note that exchanging the last two indices changes the sign.

$$
g^{\alpha\mu}R_{\alpha\sigma\lambda\mu}
=-g^{\alpha\mu}R_{\alpha\sigma\mu\lambda}
=-R_{\sigma\lambda}.
$$

Therefore, the first contraction gives

$$
\nabla_\lambda R_{\sigma\nu}
+\nabla^\alpha R_{\alpha\sigma\nu\lambda}
-\nabla_\nu R_{\sigma\lambda}
=0
$$

We obtain this equation.

### Extracting the Divergence in the Second Contraction

Now multiply further by $g^{\sigma\nu}$ and sum over $\sigma,\nu$.

In the first term, contracting the Ricci tensor gives the curvature scalar, so

$$
g^{\sigma\nu}\nabla_\lambda R_{\sigma\nu}
=\nabla_\lambda R
=\partial_\lambda R
$$

The last equality uses the fact that the covariant derivative of a scalar equals its partial derivative.

For the curvature contracted in the second term, exchange the first two indices:

$$
g^{\sigma\nu}R_{\alpha\sigma\nu\lambda}
=-g^{\sigma\nu}R_{\sigma\alpha\nu\lambda}
=-R_{\alpha\lambda}
$$

Therefore, the second term becomes $-\nabla^\alpha R_{\alpha\lambda}$.

The third term is simply

$$
-g^{\sigma\nu}\nabla_\nu R_{\sigma\lambda}
=-\nabla^\sigma R_{\sigma\lambda}
$$

as it stands.

Combining the three terms gives

$$
\partial_\lambda R
-\nabla^\alpha R_{\alpha\lambda}
-\nabla^\sigma R_{\sigma\lambda}
=0
$$

Both $\alpha$ and $\sigma$ are indices over which we sum, so the second and third terms are the same quantity. Therefore,

$$
\partial_\lambda R-2\nabla^\mu R_{\mu\lambda}=0
$$

is obtained. Renaming the remaining index $\lambda$ as $\nu$ gives

$$
\boxed{\nabla^\mu R_{\mu\nu}=\frac12\partial_\nu R}
$$

This is the relation obtained by contracting the Bianchi identity.

### Difference from the Conservation Law on the Matter Side

The divergence of the Ricci tensor is not zero in general. If the curvature scalar changes with position or time, that change appears on the right-hand side.

Let us place the matter side and curvature side next to each other.

$$
\nabla^\mu T_{\mu\nu}=0,
\qquad
\nabla^\mu R_{\mu\nu}=\frac12\partial_\nu R.
$$

The divergence on the matter side is zero, but if we use only the Ricci tensor on the curvature side, a derivative of the curvature scalar remains. Keeping this difference in mind, let us look for an equation that connects matter and curvature.

---

Alice: “I want to sort out what we learned from that long index calculation.”

Bob: “We found that taking the divergence of the Ricci tensor leaves a derivative of the curvature scalar rather than zero. Next, let us find a term that cancels what remains.”

---

## Can We Use the Ricci Tensor as It Is?

![Alice and Bob spread out diagrams and calculation notes while discussing the relation between conservation laws and curvature](../../../images/general-relativity/08/alice-bob-conservation.png)

Both the curvature side and the matter side now have tensors with two lower indices.

Taking $\kappa$ as a proportionality constant, write

$$
R_{\mu\nu}\stackrel{?}{=}\kappa T_{\mu\nu}
$$


The index structure matches. However, because the matter side has a conservation law, the curvature side must also have a property consistent with it.

If $\kappa$ is a constant and we apply $\nabla^\mu$ to both sides, the right-hand side becomes zero by the conservation law for matter. We can use the relation derived in the previous section on the left-hand side, so

$$
\frac12\partial_\nu R=0
$$

is required.

As it stands, this imposes the extra condition that the curvature scalar $R$ does not change in any direction. The candidate above is therefore insufficient for treating a general distribution of matter.

So let us find a term that cancels this $\tfrac12\partial_\nu R$.

However, $R$ by itself is a scalar, so it cannot be subtracted directly from $R_{\mu\nu}$. Multiplying it by the metric gives $g_{\mu\nu}R$, a tensor with the same indices.

## A Combination Consistent with the Conservation Law

As we used in Chapter 5, the covariant derivative of the metric is zero. Also, the covariant derivative of a scalar is the same as its partial derivative, so

$$
\begin{aligned}
\nabla^\mu(g_{\mu\nu}R)
&=(\nabla^\mu g_{\mu\nu})R+g_{\mu\nu}\nabla^\mu R\\
&=\partial_\nu R
\end{aligned}
$$

Therefore, if we define

$$
\boxed{G_{\mu\nu}=R_{\mu\nu}-\frac12g_{\mu\nu}R}
$$

then

$$
\begin{aligned}
\nabla^\mu G_{\mu\nu}
&=\frac12\partial_\nu R-\frac12\partial_\nu R\\
&=0
\end{aligned}
$$

This $G_{\mu\nu}$ is called the Einstein tensor.

Because it is constructed from the Ricci tensor, metric, and curvature scalar, it is also a tensor. Moreover, its contracted covariant derivative is zero as a geometric identity, before specifying the motion of matter.

---

Alice: “So there really was a reason for subtracting one half.”

Bob: “Yes. It is a combination that not only represents curvature but also fits the balance of energy and momentum.”

---

The $1/2$ here is not a coefficient chosen merely to make the expression look neat. It is required for the two derivatives to cancel each other.

## The Einstein Equation

We now have a candidate for connecting $G_{\mu\nu}$ on the curvature side with $T_{\mu\nu}$ on the matter side.

The proportionality coefficient is determined so that, in a weak gravitational field where objects move much more slowly than light, the equation reduces to Newtonian gravity. The result is

$$
\boxed{
G_{\mu\nu}
=\frac{8\pi G}{c^4}T_{\mu\nu}
}
$$

This is the Einstein equation that we will use from here on.

$G_{\mu\nu}$ is the Einstein tensor, while the $G$ without indices in the coefficient is Newton’s gravitational constant. They use the same letter but play different roles.

Expanding the left-hand side gives

$$
R_{\mu\nu}-\frac12g_{\mu\nu}R
=\frac{8\pi G}{c^4}T_{\mu\nu}
$$

The left-hand side represents the curvature of spacetime, while the right-hand side represents the energy, momentum, pressure, and stress of matter and fields.

The discussion so far shows why the form of this equation is natural. It does not uniquely prove the law of gravity from conservation laws alone. Connecting matter and geometry in this way is itself a physical law, which must be checked against the Newtonian limit and observations.

More generally, $\Lambda g_{\mu\nu}$ can be added to the left-hand side. $\Lambda$ is the cosmological constant; if it is constant, this term is also consistent with the conservation law. In this series, we set $\Lambda=0$ from now on as we proceed to the Schwarzschild solution around an isolated celestial body.

## Matching the Coefficient to Newtonian Gravity

Let us also briefly check the origin of the coefficient $8\pi G/c^4$. The conditions of the approximation and each step of the calculation are explained in detail in the end-of-chapter [“Appendix: Matching the Coefficient to Newtonian Gravity”](#appendix-matching-the-coefficient-to-newtonian-gravity).

In a weak gravitational field whose time variation can be neglected, let $x^0=w=ct$. If $\Phi$ is the Newtonian gravitational potential, then for the geodesic equation of a slow-moving object to agree with Newton’s equation of motion,

<a id="eq-newtonian-time-metric"></a>

$$
g_{00}\simeq-\left(1+\frac{2\Phi}{c^2}\right)
\qquad (8.1)
$$

must hold.

In fact, the leading term in the expression that obtains the connection from the metric is $\Gamma^i_{00}\simeq\partial_i\Phi/c^2$, so the geodesic equation becomes $d^2x^i/dt^2\simeq-\partial_i\Phi$.

On the other hand, temporarily write the field equation as $G_{\mu\nu}=\kappa T_{\mu\nu}$ and contract both sides with $g^{\mu\nu}$. Since spacetime is four-dimensional, $g^{\mu\nu}g_{\mu\nu}=4$, and

$$
R-\frac12\cdot4R=\kappa T,
\qquad
T=g^{\mu\nu}T_{\mu\nu}
$$

gives $R=-\kappa T$. Substituting this back gives

$$
R_{\mu\nu}=\kappa\left(T_{\mu\nu}-\frac12g_{\mu\nu}T\right)
$$

This is the result.

For matter whose pressure and internal-motion energy can be neglected compared with its rest energy, let $\rho$ be its mass density. Then $T_{00}\simeq\rho c^2$ and $T\simeq-\rho c^2$. The time component is

$$
R_{00}\simeq\frac{\kappa}{2}\rho c^2
$$

This is the time component.

In the same weak, static field, the leading term in the expression for curvature is

$$
R_{00}\simeq\sum_{i=1}^3\partial_i\Gamma^i_{00}
\simeq\frac{1}{c^2}\nabla_{\!\mathrm{space}}^2\Phi
$$

Here, $\nabla_{\!\mathrm{space}}^2=\partial_x^2+\partial_y^2+\partial_z^2$ is the sum of spatial derivatives in Newtonian theory, distinguished from the notation for a covariant derivative.

The Poisson equation satisfied by the Newtonian gravitational potential is

$$
\nabla_{\!\mathrm{space}}^2\Phi=4\pi G\rho
$$

Comparing the two expressions for $R_{00}$ gives

$$
\frac{\kappa}{2}\rho c^2=\frac{4\pi G}{c^2}\rho,
\qquad
\kappa=\frac{8\pi G}{c^4}
$$

Thus, the strength of the connection between matter and curvature is determined so that it agrees with the known weak-gravity limit.

## Does Vacuum Mean Flat Spacetime?

Consider a region outside a star where there is neither matter nor an electromagnetic field. There,

$$
T_{\mu\nu}=0
$$

so the Einstein equation becomes

$$
R_{\mu\nu}-\frac12g_{\mu\nu}R=0
$$

Setting $T=0$ in the earlier contraction gives $R=0$, so in the end,

$$
\boxed{R_{\mu\nu}=0}
$$

This is the vacuum equation in four dimensions when the cosmological constant is zero.

---

Alice: “It became zero, but does that mean there is no gravity outside the star?”

Bob: “What became zero here is the Ricci tensor. Remember that it was made by contracting the Riemann curvature tensor.”

---

It is the Ricci tensor that became zero. As we saw in the previous chapter, it is obtained by summing over some of the indices of the Riemann curvature tensor.

Even if a sum is zero, every term in the sum need not be zero. In four-dimensional spacetime,

$$
R_{\mu\nu}=0
\quad\text{even though}\quad
{R^\rho}_{\sigma\mu\nu}\ne0
$$

can occur.

Even outside a star, neighboring freely falling objects can have relative acceleration. This is a tidal effect: the way they fall differs depending on their direction toward the star and their distance from it. The vacuum equation does not require this curvature to vanish.

Having no matter at a location and having flat spacetime are different things.

The sphere example in Chapter 7 was two-dimensional. We must not carry its single independent piece of curvature information directly over to four-dimensional spacetime.

## The Metric Is the Unknown

![Alice and Bob observe a star at an observatory while considering the metric that describes spacetime around it](../../../images/general-relativity/08/alice-bob-metric.png)

For the Einstein equation

$$
G_{\mu\nu}=\frac{8\pi G}{c^4}T_{\mu\nu}
$$

the left-hand side $G_{\mu\nu}$ represents the curvature of spacetime. When solving this equation, the unknown we seek is the metric $g_{\mu\nu}$ that gives rise to that curvature.

Once we choose a candidate metric, its inverse metric and partial derivatives determine $\Gamma^\rho_{\mu\nu}$. We can then differentiate the connection to form the Ricci tensor and contract it to find the curvature scalar, allowing us to calculate $G_{\mu\nu}$ on the left-hand side.

The connection contains first derivatives of the metric, and curvature contains second derivatives. In other words, the Einstein equation is a differential equation that the metric and its derivatives must satisfy.

However, the value of $T_{\mu\nu}$ at one point alone does not immediately determine the metric at that point. We seek solutions using boundary conditions and initial conditions, in addition to the distribution and motion of matter. If the motion of matter is also unknown, we must solve the matter equations and the metric equation together.

Even in vacuum, there is more than one metric satisfying the same $R_{\mu\nu}=0$. When a star is present, its connection to the interior and conditions far away help select the exterior solution.

Until now, we calculated curvature from a metric. From here on, we will seek metrics whose calculated curvature satisfies the equation.

---

Alice: “Calculating the curvature is not the end, then.”

Bob: “Right. We calculate curvature from a candidate metric and require it to balance the matter side. Solving the equation means finding a metric that satisfies that condition together with the boundary and initial conditions.”

---

Once we know that metric, we can return to the clocks and rulers of Chapter 3 and the geodesics of light and objects in Chapter 6 to study observable phenomena.

## Summary

- The energy-momentum tensor includes not only energy density, but also flows of energy and momentum, pressure, and stress.
- The local conservation law for matter and fields together can be written as $\nabla^\mu T_{\mu\nu}=0$.
- On the curvature side, $G_{\mu\nu}=R_{\mu\nu}-\tfrac12g_{\mu\nu}R$ satisfies $\nabla^\mu G_{\mu\nu}=0$.
- The physical law connecting them is $G_{\mu\nu}=(8\pi G/c^4)T_{\mu\nu}$, and its proportionality coefficient is determined by comparison with Newtonian gravity.
- In four-dimensional vacuum with the cosmological constant set to zero, $R_{\mu\nu}=0$, but the Riemann curvature tensor is not necessarily zero.
- The field equation is an equation for finding the metric of spacetime according to the state of matter, boundary conditions, and so on.

## The Next Question

We now have an equation connecting matter and spacetime. Next, let us actually find the metric around a single spherical star.

Treating all ten components of the symmetric metric as unknown functions from the start would be difficult. But if a star is spherically symmetric and the spacetime outside it does not change with time, changing direction or time should describe the same situation.

In the next document, [“Predicting a Spherically Symmetric Spacetime”](./09-SphericallySymmetricSpacetime.md), we use this symmetry to construct a candidate metric. Before solving the vacuum equation, let us consider how far we can reduce the number of unknown functions.

## For Readers Who Want to Explore Further

For detailed derivations of the conservation law, the Einstein equation, and the Newtonian limit, see Sean Carroll’s [Lecture Notes on General Relativity, Chapter 4](https://www.preposterousuniverse.com/wp-content/uploads/grnotes-four.pdf). The differential Bianchi identity used in this chapter is derived in the following appendix.

## Appendix: Symmetries of the Curvature Tensor

Let us derive the antisymmetries of the Riemann curvature tensor and the symmetry of the Ricci tensor used in the main text. Here too, we use local inertial coordinates in which the connection vanishes at an arbitrary point $q$.

### Expressing Curvature Through Second Derivatives of the Metric

In Chapter 5, we derived [equation (5.1)](./05-ChristoffelFromMetric.md#eq-metric-compatibility), which expresses the compatibility of the metric and the connection. If we simultaneously rename its indices as $\lambda\to\mu$, $\mu\to\alpha$, $\nu\to\rho$, and $\rho\to\beta$, we obtain

$$
\partial_\mu g_{\alpha\rho}
=\Gamma^\beta_{\mu\alpha}g_{\beta\rho}
+\Gamma^\beta_{\mu\rho}g_{\alpha\beta}
$$

Thus, the first partial derivatives of the metric also vanish at $q$. This does not mean that its second partial derivatives vanish.

Write the components of the connection with its first index lowered as

$$
\Gamma_{\alpha\nu\sigma}
=g_{\alpha\rho}\Gamma^\rho_{\nu\sigma}
$$

Multiplying [equation (5.2)](./05-ChristoffelFromMetric.md#eq-christoffel-from-metric) for the connection from Chapter 5 by the metric gives

$$
\Gamma_{\alpha\nu\sigma}
=\frac12\left(
\partial_\nu g_{\alpha\sigma}
+\partial_\sigma g_{\alpha\nu}
-\partial_\alpha g_{\nu\sigma}
\right)
$$

This is notation for calculation; it does not mean that the connection has become a tensor.

Lower the first index with the metric in the definition of curvature, [equation (7.2)](./07-CurvatureFromParallelTransport.md#eq-riemann-curvature), from Chapter 7. At $q$, products of connections vanish, so

$$
\left.R_{\alpha\sigma\mu\nu}\right|_q
=\left.g_{\alpha\rho}
\left(
\partial_\mu\Gamma^\rho_{\nu\sigma}
-\partial_\nu\Gamma^\rho_{\mu\sigma}
\right)\right|_q
$$

On the other hand, the product rule gives

$$
\partial_\mu\Gamma_{\alpha\nu\sigma}
=(\partial_\mu g_{\alpha\rho})\Gamma^\rho_{\nu\sigma}
+g_{\alpha\rho}\partial_\mu\Gamma^\rho_{\nu\sigma}
$$

At $q$, the first term on the right-hand side vanishes. Therefore, curvature can be written as

$$
\left.R_{\alpha\sigma\mu\nu}\right|_q
=\left.
\left(
\partial_\mu\Gamma_{\alpha\nu\sigma}
-\partial_\nu\Gamma_{\alpha\mu\sigma}
\right)\right|_q
$$

as desired.

From here until we verify the symmetries, all equations are evaluated at $q$, and we omit $\left.\cdots\right\vert_q$.

The preceding equation is the difference of two derivatives of the connection:

$$
R_{\alpha\sigma\mu\nu}
=\partial_\mu\Gamma_{\alpha\nu\sigma}
-\partial_\nu\Gamma_{\alpha\mu\sigma}
$$

Let us calculate these two terms separately.

For the first term, use the connection we just found:

$$
\Gamma_{\alpha\nu\sigma}
=\frac12\left(
\partial_\nu g_{\alpha\sigma}
+\partial_\sigma g_{\alpha\nu}
-\partial_\alpha g_{\nu\sigma}
\right)
$$

Taking its partial derivative with respect to $x^\mu$ applies $\partial_\mu$ to every term inside the parentheses, giving

$$
\partial_\mu\Gamma_{\alpha\nu\sigma}
=\frac12\left(
\partial_\mu\partial_\nu g_{\alpha\sigma}
+\partial_\mu\partial_\sigma g_{\alpha\nu}
-\partial_\mu\partial_\alpha g_{\nu\sigma}
\right)
$$

This gives the result above.

For the second term, use the connection formula with $\nu$ replaced by $\mu$:

$$
\Gamma_{\alpha\mu\sigma}
=\frac12\left(
\partial_\mu g_{\alpha\sigma}
+\partial_\sigma g_{\alpha\mu}
-\partial_\alpha g_{\mu\sigma}
\right)
$$

Taking its partial derivative with respect to $x^\nu$ gives

$$
\partial_\nu\Gamma_{\alpha\mu\sigma}
=\frac12\left(
\partial_\nu\partial_\mu g_{\alpha\sigma}
+\partial_\nu\partial_\sigma g_{\alpha\mu}
-\partial_\nu\partial_\alpha g_{\mu\sigma}
\right)
$$

This gives the result above.

Curvature is the first term minus the second, so all three terms inside the parentheses in the second term reverse sign. In particular, the final minus term in the second term becomes plus when it is subtracted. Combining the two results gives

$$
\begin{aligned}
R_{\alpha\sigma\mu\nu}
&=\frac12\bigl(
\partial_\mu\partial_\nu g_{\alpha\sigma}
+\partial_\mu\partial_\sigma g_{\alpha\nu}
-\partial_\mu\partial_\alpha g_{\nu\sigma}\\
&\qquad
-\partial_\nu\partial_\mu g_{\alpha\sigma}
-\partial_\nu\partial_\sigma g_{\alpha\mu}
+\partial_\nu\partial_\alpha g_{\mu\sigma}
\bigr).
\end{aligned}
$$

Assume that the metric is sufficiently smooth. Interchanging the order of second partial derivatives makes the first and fourth terms cancel. Rearranging what remains gives

$$
\begin{aligned}
R_{\alpha\sigma\mu\nu}
=\frac12\bigl(
&\partial_\mu\partial_\sigma g_{\alpha\nu}
+\partial_\nu\partial_\alpha g_{\sigma\mu}\\
&-\partial_\mu\partial_\alpha g_{\sigma\nu}
-\partial_\nu\partial_\sigma g_{\alpha\mu}
\bigr)
\end{aligned}
$$

. Let us use this formula to examine what happens when indices are exchanged.

### Antisymmetry in the First and Last Pair of Indices

First, exchange the first two indices $\alpha,\sigma$:

$$
\begin{aligned}
R_{\sigma\alpha\mu\nu}
=\frac12\bigl(
&\partial_\mu\partial_\alpha g_{\sigma\nu}
+\partial_\nu\partial_\sigma g_{\alpha\mu}\\
&-\partial_\mu\partial_\sigma g_{\alpha\nu}
-\partial_\nu\partial_\alpha g_{\sigma\mu}
\bigr)
=-R_{\alpha\sigma\mu\nu}.
\end{aligned}
$$

The two terms that were plus in the original expression are now minus, and the two that were minus are now plus.

Next, exchange the last two indices $\mu,\nu$:

$$
\begin{aligned}
R_{\alpha\sigma\nu\mu}
=\frac12\bigl(
&\partial_\nu\partial_\sigma g_{\alpha\mu}
+\partial_\mu\partial_\alpha g_{\sigma\nu}\\
&-\partial_\nu\partial_\alpha g_{\sigma\mu}
-\partial_\mu\partial_\sigma g_{\alpha\nu}
\bigr)
=-R_{\alpha\sigma\mu\nu}.
\end{aligned}
$$

Here too, all four terms reverse sign. Therefore,

$$
\boxed{
R_{\alpha\sigma\mu\nu}
=-R_{\sigma\alpha\mu\nu},
\qquad
R_{\alpha\sigma\mu\nu}
=-R_{\alpha\sigma\nu\mu}
}
$$

This proves the two antisymmetries.

### Exchanging the Two Pairs of Indices

To derive the symmetry of the Ricci tensor, let us verify one more property. Exchanging the two index pairs $(\alpha,\sigma)$ and $(\mu,\nu)$ gives

$$
\begin{aligned}
R_{\mu\nu\alpha\sigma}
=\frac12\bigl(
&\partial_\alpha\partial_\nu g_{\mu\sigma}
+\partial_\sigma\partial_\mu g_{\nu\alpha}\\
&-\partial_\alpha\partial_\mu g_{\nu\sigma}
-\partial_\sigma\partial_\nu g_{\mu\alpha}
\bigr).
\end{aligned}
$$

Using the symmetry of the metric, $g_{\mu\sigma}=g_{\sigma\mu}$, and the interchangeability of second partial derivatives, this becomes the same four terms as the original $R_{\alpha\sigma\mu\nu}$. Hence,

$$
\boxed{R_{\alpha\sigma\mu\nu}=R_{\mu\nu\alpha\sigma}}
$$

. Exchanging the two indices within either pair changes the sign, but exchanging both pairs as whole units does not.

We verified these results in local inertial coordinates at $q$. However, every relation obtained is a tensor equation, so it also holds in arbitrary coordinates at the same point. Moreover, $q$ was arbitrary, so these symmetries hold at every point.

### Symmetry of the Ricci Tensor

The Ricci tensor is defined by contracting the first and third indices:

$$
R_{\sigma\nu}=g^{\alpha\mu}R_{\alpha\sigma\mu\nu}
$$

Using the symmetry that exchanges the two pairs gives

$$
R_{\sigma\nu}
=g^{\alpha\mu}R_{\mu\nu\alpha\sigma}
$$

. Since $\alpha,\mu$ are summed indices, we may exchange their names. The inverse metric is also symmetric, so

$$
\begin{aligned}
R_{\sigma\nu}
&=g^{\mu\alpha}R_{\alpha\nu\mu\sigma}\\
&=g^{\alpha\mu}R_{\alpha\nu\mu\sigma}\\
&=R_{\nu\sigma}
\end{aligned}
$$

This proves the symmetry of the Ricci tensor used in the main text.

## Appendix: Derivation of the Differential Bianchi Identity

![Alice and Bob focus on one point of a curved-surface model and consider the coordinates used at that point](../../../images/general-relativity/08/alice-bob-local-coordinates.png)

Let us derive the differential Bianchi identity used in the main text from the definition of the Riemann curvature tensor in Chapter 7. We calculate with one index raised, then lower it with the metric at the end.

### Making the Connection Vanish at an Arbitrary Point

Let $q$ be an arbitrary point in spacetime. As explained in Chapters 6 and 7, we can choose local inertial coordinates such that at this point,

$$
\left.\Gamma^\rho_{\mu\nu}\right|_q=0
$$

. Here $\left.\cdots\right\vert_q$ means that the value is evaluated at $q$.

Importantly, the connection vanishes only at the chosen point; it need not vanish nearby. Therefore, we must not set the derivative of the connection, $\partial_\lambda\Gamma^\rho_{\mu\nu}$, to zero as well.

When differentiating curvature, first differentiate a general equation that holds in the surrounding region, and only then evaluate it at $q$. Let us keep this order in the calculation.

### Differentiating the Definition of Curvature

The definition in Chapter 7 is

$$
\begin{aligned}
{R^\rho}_{\sigma\mu\nu}
&=\partial_\mu\Gamma^\rho_{\nu\sigma}
-\partial_\nu\Gamma^\rho_{\mu\sigma}\\
&\quad+\Gamma^\rho_{\mu\beta}\Gamma^\beta_{\nu\sigma}
-\Gamma^\rho_{\nu\beta}\Gamma^\beta_{\mu\sigma}
\end{aligned}
$$

. Here $\beta$ is a summed index. Taking the partial derivative of the entire expression with respect to $x^\lambda$ gives

$$
\begin{aligned}
\partial_\lambda {R^\rho}_{\sigma\mu\nu}
&=\partial_\lambda\partial_\mu\Gamma^\rho_{\nu\sigma}
-\partial_\lambda\partial_\nu\Gamma^\rho_{\mu\sigma}\\
&\quad+(\partial_\lambda\Gamma^\rho_{\mu\beta})
\Gamma^\beta_{\nu\sigma}
+\Gamma^\rho_{\mu\beta}
(\partial_\lambda\Gamma^\beta_{\nu\sigma})\\
&\quad-(\partial_\lambda\Gamma^\rho_{\nu\beta})
\Gamma^\beta_{\mu\sigma}
-\Gamma^\rho_{\nu\beta}
(\partial_\lambda\Gamma^\beta_{\mu\sigma})
\end{aligned}
$$

Each of the four terms produced by the product rule contains one undifferentiated $\Gamma$. Thus, all four vanish at $q$. We have not set the derivatives of the connection themselves to zero.

Therefore,

$$
\left.\partial_\lambda {R^\rho}_{\sigma\mu\nu}\right|_q
=\left.
\left(
\partial_\lambda\partial_\mu\Gamma^\rho_{\nu\sigma}
-\partial_\lambda\partial_\nu\Gamma^\rho_{\mu\sigma}
\right)\right|_q
\qquad (A.1)
$$

This is equation (A.1).

### At q, Covariant Derivatives Also Equal Partial Derivatives

The Riemann curvature tensor has one upper index and three lower indices. Let us derive its covariant derivative from the covariant derivative of a vector and the product rule. This derivation is carried out in general coordinates, not only at $q$.

Take any three smooth vector fields $A^\sigma,B^\mu,C^\nu$, and set

$$
V^\rho={R^\rho}_{\sigma\mu\nu}A^\sigma B^\mu C^\nu
$$

. The three lower indices are contracted and only the upper index $\rho$ remains, so $V^\rho$ is a vector. Let us calculate its covariant derivative in two ways and compare them.

First, using the covariant derivative of a vector found in Chapter 6,

$$
\begin{aligned}
\nabla_\lambda V^\rho
&=\partial_\lambda V^\rho
+\Gamma^\rho_{\lambda\beta}V^\beta\\
&=(\partial_\lambda {R^\rho}_{\sigma\mu\nu})
A^\sigma B^\mu C^\nu\\
&\quad+{R^\rho}_{\sigma\mu\nu}
(\partial_\lambda A^\sigma)B^\mu C^\nu\\
&\quad+{R^\rho}_{\sigma\mu\nu}
A^\sigma(\partial_\lambda B^\mu)C^\nu\\
&\quad+{R^\rho}_{\sigma\mu\nu}
A^\sigma B^\mu(\partial_\lambda C^\nu)\\
&\quad+\Gamma^\rho_{\lambda\beta}
{R^\beta}_{\sigma\mu\nu}A^\sigma B^\mu C^\nu
\end{aligned}
$$

. Here we used the product rule for ordinary partial derivatives.

On the other hand, the covariant derivative of a tensor is defined to obey the product rule and to be compatible with index contraction. Therefore, the same quantity can also be written as

$$
\begin{aligned}
\nabla_\lambda V^\rho
&=(\nabla_\lambda {R^\rho}_{\sigma\mu\nu})
A^\sigma B^\mu C^\nu\\
&\quad+{R^\rho}_{\sigma\mu\nu}
(\nabla_\lambda A^\sigma)B^\mu C^\nu\\
&\quad+{R^\rho}_{\sigma\mu\nu}
A^\sigma(\nabla_\lambda B^\mu)C^\nu\\
&\quad+{R^\rho}_{\sigma\mu\nu}
A^\sigma B^\mu(\nabla_\lambda C^\nu)
\end{aligned}
$$

. Substitute

$$
\begin{aligned}
\nabla_\lambda A^\sigma
&=\partial_\lambda A^\sigma+\Gamma^\sigma_{\lambda\beta}A^\beta,\\
\nabla_\lambda B^\mu
&=\partial_\lambda B^\mu+\Gamma^\mu_{\lambda\beta}B^\beta,\\
\nabla_\lambda C^\nu
&=\partial_\lambda C^\nu+\Gamma^\nu_{\lambda\beta}C^\beta
\end{aligned}
$$

into this expression.

The two calculations contain the same three terms involving partial derivatives of $A,B,C$. Removing them from both sides leaves

$$
\begin{aligned}
&\left(
\partial_\lambda {R^\rho}_{\sigma\mu\nu}
+\Gamma^\rho_{\lambda\beta}{R^\beta}_{\sigma\mu\nu}
\right)A^\sigma B^\mu C^\nu\\
&=(\nabla_\lambda {R^\rho}_{\sigma\mu\nu})
A^\sigma B^\mu C^\nu\\
&\quad+{R^\rho}_{\sigma\mu\nu}
\Gamma^\sigma_{\lambda\beta}A^\beta B^\mu C^\nu\\
&\quad+{R^\rho}_{\sigma\mu\nu}
\Gamma^\mu_{\lambda\beta}A^\sigma B^\beta C^\nu\\
&\quad+{R^\rho}_{\sigma\mu\nu}
\Gamma^\nu_{\lambda\beta}A^\sigma B^\mu C^\beta
\end{aligned}
$$

which remains.

Rename the summed indices in the final three terms on the right so that they too can be read as coefficients multiplying $A^\sigma B^\mu C^\nu$. For example, in the first term, exchange the names $\sigma$ and $\beta$:

$$
{R^\rho}_{\sigma\mu\nu}
\Gamma^\sigma_{\lambda\beta}A^\beta B^\mu C^\nu =
\Gamma^\beta_{\lambda\sigma}
{R^\rho}_{\beta\mu\nu}A^\sigma B^\mu C^\nu
$$

. This does not exchange positions of tensor indices; it merely renames summation symbols, so the sign does not change.

For the remaining two terms, similarly exchange the names $\mu$ and $\beta$, and $\nu$ and $\beta$, respectively:

$$
\begin{aligned}
{R^\rho}_{\sigma\mu\nu}
\Gamma^\mu_{\lambda\beta}A^\sigma B^\beta C^\nu
&=\Gamma^\beta_{\lambda\mu}
{R^\rho}_{\sigma\beta\nu}A^\sigma B^\mu C^\nu,\\
{R^\rho}_{\sigma\mu\nu}
\Gamma^\nu_{\lambda\beta}A^\sigma B^\mu C^\beta
&=\Gamma^\beta_{\lambda\nu}
{R^\rho}_{\sigma\mu\beta}A^\sigma B^\mu C^\nu
\end{aligned}
$$

we obtain the following.

We can now compare all terms as coefficients multiplying $A^\sigma B^\mu C^\nu$. Since the three vectors are arbitrary, choosing each along every direction of the coordinate basis shows that the corresponding coefficients are equal for every $\sigma,\mu,\nu$.

Move the three connection terms on the right to the left and solve for the covariant derivative of curvature:

$$
\begin{aligned}
\nabla_\lambda {R^\rho}_{\sigma\mu\nu}
&=\partial_\lambda {R^\rho}_{\sigma\mu\nu}
+\Gamma^\rho_{\lambda\beta}{R^\beta}_{\sigma\mu\nu}\\
&\quad-\Gamma^\beta_{\lambda\sigma}{R^\rho}_{\beta\mu\nu}
-\Gamma^\beta_{\lambda\mu}{R^\rho}_{\sigma\beta\nu}
-\Gamma^\beta_{\lambda\nu}{R^\rho}_{\sigma\mu\beta}
\end{aligned}
$$

. An upper index receives a plus connection term, and a lower index receives a minus connection term.

At $q$, all these connection terms also vanish, so

$$
\left.\nabla_\lambda {R^\rho}_{\sigma\mu\nu}\right|_q
=\left.\partial_\lambda {R^\rho}_{\sigma\mu\nu}\right|_q
$$

. Thus, we can use the calculation above directly.

### Cyclically Adding Three Derivatives

All equations from here on are evaluated at $q$; to keep the notation short, we omit $\left.\cdots\right\vert_q$.

At $q$, covariant and partial derivatives agree. Thus, equation (A.1) expresses the covariant derivative of curvature through second partial derivatives of the connection. Keeping $\rho,\sigma$ fixed and cyclically permuting $\lambda,\mu,\nu$ gives the following three equations.

$$
\begin{aligned}
\nabla_\lambda {R^\rho}_{\sigma\mu\nu}
&=\partial_\lambda\partial_\mu\Gamma^\rho_{\nu\sigma}
-\partial_\lambda\partial_\nu\Gamma^\rho_{\mu\sigma},\\
\nabla_\mu {R^\rho}_{\sigma\nu\lambda}
&=\partial_\mu\partial_\nu\Gamma^\rho_{\lambda\sigma}
-\partial_\mu\partial_\lambda\Gamma^\rho_{\nu\sigma},\\
\nabla_\nu {R^\rho}_{\sigma\lambda\mu}
&=\partial_\nu\partial_\lambda\Gamma^\rho_{\mu\sigma}
-\partial_\nu\partial_\mu\Gamma^\rho_{\lambda\sigma}.
\end{aligned}
$$

Adding the three equations and grouping terms that differentiate the same connection component gives

$$
\begin{aligned}
&\nabla_\lambda {R^\rho}_{\sigma\mu\nu}
+\nabla_\mu {R^\rho}_{\sigma\nu\lambda}
+\nabla_\nu {R^\rho}_{\sigma\lambda\mu}\\
&=(\partial_\lambda\partial_\mu-\partial_\mu\partial_\lambda)
\Gamma^\rho_{\nu\sigma}\\
&\quad+(\partial_\mu\partial_\nu-\partial_\nu\partial_\mu)
\Gamma^\rho_{\lambda\sigma}\\
&\quad+(\partial_\nu\partial_\lambda-\partial_\lambda\partial_\nu)
\Gamma^\rho_{\mu\sigma}\\
&=0
\end{aligned}
$$

. If the connection components are sufficiently smooth, the order of their second coordinate partial derivatives can be exchanged, so each of the three parentheses is zero.

What we exchanged here are **partial derivatives** acting on the connection components, which are functions of the coordinates. We did not exchange covariant derivatives, whose order cannot generally be exchanged.

### From a Calculation at One Point to General Coordinates

---

Alice: “By calculating in special coordinates where the connection is zero, have we really learned the general case too?”

Bob: “Yes, because the equation we obtained is a tensor equation. If all its components are zero at that point, they remain zero after changing coordinates. Also, that point could have been chosen anywhere. Let us use these two facts in order.”

---

The calculation above used coordinates in which the connection vanishes at $q$. However, the left-hand side of the resulting equation is a sum of covariant derivatives of the curvature tensor, and is itself a tensor.

If all components of a tensor are zero in one coordinate system, they are still all zero after transforming to another coordinate system at the same point. Therefore, this equation holds in arbitrary coordinates at $q$.

Moreover, $q$ was arbitrary from the beginning. The same reasoning works at every point, so without needing coordinates in which the connection vanishes throughout a region,

$$
\boxed{
\nabla_\lambda {R^\rho}_{\sigma\mu\nu}
+\nabla_\mu {R^\rho}_{\sigma\nu\lambda}
+\nabla_\nu {R^\rho}_{\sigma\lambda\mu}
=0
}
$$

holds at every point.

Finally, multiply by $g_{\alpha\rho}$. Since the covariant derivative of the metric is zero,

$$
g_{\alpha\rho}\nabla_\lambda {R^\rho}_{\sigma\mu\nu}
=\nabla_\lambda
\left(g_{\alpha\rho}{R^\rho}_{\sigma\mu\nu}\right)
=\nabla_\lambda R_{\alpha\sigma\mu\nu}
$$

. Lowering the indices of the other two terms in the same way gives

$$
\boxed{
\nabla_\lambda R_{\alpha\sigma\mu\nu}
+\nabla_\mu R_{\alpha\sigma\nu\lambda}
+\nabla_\nu R_{\alpha\sigma\lambda\mu}
=0
}
$$

This is the differential Bianchi identity used in the main text. The calculation that contracts this equation twice continues from [“Obtaining the Ricci Tensor in the First Contraction”](#obtaining-the-ricci-tensor-in-the-first-contraction) in the main text.

## Appendix: Matching the Coefficient to Newtonian Gravity

Using the Einstein tensor, we can write an equation consistent with conservation on the matter side:

$$
G_{\mu\nu}=\kappa T_{\mu\nu}
$$

Let us determine the proportionality constant $\kappa$ by comparing this with Newtonian gravity.

First, we connect the metric and gravitational potential through the motion of objects; then we determine $\kappa$ from the field equation.

Consider a weak, time-independent gravitational field. Assume that objects and the gravitational source move slowly, and that contributions from pressure and internal motion can be ignored. We use coordinates that become inertial coordinates in the limit of no gravity, and set $x^0=ct$. Below, we keep terms first order in weak gravity and the leading terms in velocity.

### Newtonian Gravitational Potential

![Alice and Bob observe falling apples in an orchard and compare them with a Newtonian gravity calculation](../../../images/general-relativity/08/alice-bob-newton.png)

The equation of motion in Newtonian mechanics is $ma^i=F^i$. Let us rewrite it using the gravitational potential.

Consider a particle of mass $m$ at a distance $r$ from the center, outside a spherically symmetric body of mass $M$. Its potential energy, chosen to be zero at infinity, is

$$
U=-\frac{GMm}{r}
$$

Here $r$ is the distance from the center, not a coordinate component $x^i$ itself. In Cartesian coordinates with the center at the origin, $r=\sqrt{(x^1)^2+(x^2)^2+(x^3)^2}$.

Dividing this energy by the particle mass $m$ gives

$$
\Phi=\frac{U}{m}=-\frac{GM}{r}
$$

which is called the **gravitational potential**. While $U$ also depends on the particle’s mass, $\Phi$ is potential energy per unit mass and represents the gravitational field.

Since force acts in the direction in which potential energy decreases,

$$
F^i=-\frac{\partial U}{\partial x^i}
=-m\frac{\partial\Phi}{\partial x^i}
$$

Substituting this into $ma^i=F^i$ and dividing both sides by $m$ gives

$$
\frac{d^2x^i}{dt^2}=-\partial_i\Phi
$$

Here $\partial_i=\partial/\partial x^i$. This relation between acceleration and potential is not limited to the spherically symmetric case. Below, we choose $\Phi=0$ where gravity vanishes and assume $\lvert\Phi\rvert/c^2\ll1$.

### Low-Speed Approximation of the Geodesic Equation

The spatial components of the geodesic equation derived in Chapter 6 are

$$
\frac{d^2x^i}{d\tau^2}
+\Gamma^i_{\alpha\beta}
\frac{dx^\alpha}{d\tau}
\frac{dx^\beta}{d\tau}
=0
$$

Here too, $\tau$ is proper time with units of distance, and the time coordinate is $x^0=w$. Separating the sums over $\alpha,\beta$ into time and space gives

$$
\begin{aligned}
0={}&\frac{d^2x^i}{d\tau^2}
+\Gamma^i_{00}\left(\frac{dw}{d\tau}\right)^2\\
&+2\sum_j\Gamma^i_{0j}
\frac{dw}{d\tau}\frac{dx^j}{d\tau}
+\sum_{j,k}\Gamma^i_{jk}
\frac{dx^j}{d\tau}\frac{dx^k}{d\tau}.
\end{aligned}
$$

At low speed, among the terms containing the connection, the $\Gamma^i_{00}$ term, which contains no spatial velocity, gives the leading contribution.

Next, let us rewrite acceleration with respect to proper time $\tau$ in terms of acceleration with respect to coordinate time $w$. Viewing the particle position as $x^i(w(\tau))$, the chain rule gives

$$
\frac{dx^i}{d\tau}
=\frac{dx^i}{dw}\frac{dw}{d\tau}
$$

Differentiate this once more with respect to $\tau$. Since the right-hand side is a product of two factors,

$$
\frac{d^2x^i}{d\tau^2}
=\frac{d}{d\tau}\left(\frac{dx^i}{dw}\right)\frac{dw}{d\tau}
+\frac{dx^i}{dw}\frac{d}{d\tau}\left(\frac{dw}{d\tau}\right)
$$

For the first term, use the chain rule once again:

$$
\frac{d}{d\tau}\left(\frac{dx^i}{dw}\right)
=\frac{d^2x^i}{dw^2}\frac{dw}{d\tau}
$$

Substitute this. The final factor in the second term is $d^2w/d\tau^2$, so we obtain

$$
\frac{d^2x^i}{d\tau^2}
=\left(\frac{dw}{d\tau}\right)^2\frac{d^2x^i}{dw^2}
+\frac{dx^i}{dw}\frac{d^2w}{d\tau^2}
$$

No approximation has been used so far. The first term is the acceleration in coordinate time multiplied by a time-conversion factor. The second term appears because that conversion factor $dw/d\tau$ itself changes along the particle’s motion.

In the weak-gravity, low-speed approximation, $dw/d\tau\simeq1$, and in this static weak field the second term is a higher-order low-speed correction. Therefore, at leading order,

$$
\frac{d^2x^i}{dw^2}\simeq-\Gamma^i_{00}
$$

To return to coordinate time in seconds, as used in Newtonian mechanics, use $w=ct$, so that $d^2x^i/dt^2=c^2d^2x^i/dw^2$. Therefore,

$$
\frac{d^2x^i}{dt^2}\simeq-c^2\Gamma^i_{00}
$$

This gives the acceleration expressed using coordinate time in seconds.

### Relating the Time Component of the Metric to the Potential

By equation (5.2), which obtains the connection from the metric,

$$
\Gamma^i_{00}
=\frac12 g^{i\beta}
\left(2\partial_0g_{\beta0}-\partial_\beta g_{00}\right)
$$

Since we ignore time variation of the field, $\partial_0g_{\beta0}=0$, leaving

$$
\Gamma^i_{00}=-\frac12 g^{i\beta}\partial_\beta g_{00}
$$

Here $\beta$ is an index summed over $0,1,2,3$. Separating time and spatial components gives

$$
\Gamma^i_{00}
=-\frac12\left(
g^{i0}\partial_0g_{00}
+\sum_{j=1}^3g^{ij}\partial_jg_{00}
\right)
$$

Since $\partial_0g_{00}$ is also zero, the time-component term disappears, and we obtain

$$
\Gamma^i_{00}
=-\frac12\sum_{j=1}^3g^{ij}\partial_jg_{00}
$$


Next use the weak-gravity approximation. In the limit where gravity vanishes, the inverse spatial metric becomes $\delta^{ij}$, so write

$$
g^{ij}=\delta^{ij}+k^{ij},
\qquad
g_{00}=-1+h_{00}
$$

Here $k^{ij}$ and $h_{00}$ are small deviations due to weak gravity. Therefore,

$$
\sum_jg^{ij}\partial_jg_{00}
=\sum_j\delta^{ij}\partial_jh_{00}
+\sum_jk^{ij}\partial_jh_{00}
$$

The last term is a product of a small deviation and its derivative, so we neglect it as second order in weak gravity. Thus, to first order,

$$
\Gamma^i_{00}
\simeq-\frac12\sum_{j=1}^3\delta^{ij}\partial_jh_{00}
$$

Since $\delta^{ij}$ is 1 only when $i=j$ and 0 otherwise, only the $j=i$ term remains in this sum. For example, if $i=1$, only $\partial_1h_{00}$ remains. Therefore,

$$
\Gamma^i_{00}\simeq-\frac12\partial_i h_{00}
$$

and the geodesic equation becomes

$$
\frac{d^2x^i}{dt^2}\simeq\frac{c^2}{2}\partial_i h_{00}
$$

For this to agree with the Newtonian expression $-\partial_i\Phi$,

$$
\frac{c^2}{2}\partial_i h_{00}=-\partial_i\Phi
$$

must hold. In other words, the spatial derivative of $h_{00}+2\Phi/c^2$ is zero, so this quantity is spatially constant. If we also set the metric deviation to $h_{00}=0$ where gravity vanishes and $\Phi=0$, that constant is zero. Therefore, at first order,

$$
h_{00}=-\frac{2\Phi}{c^2}
$$

Returning to $g_{00}=-1+h_{00}$ gives

$$
\boxed{g_{00}\simeq-\left(1+\frac{2\Phi}{c^2}\right)}
$$

Substituting this back into the connection expression gives

$$
\Gamma^i_{00}\simeq\frac{\partial_i\Phi}{c^2}
$$


### Rewrite the Field Equation in Terms of the Ricci Tensor

Next consider the field equation with unknown coefficient $\kappa$,

$$
R_{\mu\nu}-\frac12g_{\mu\nu}R=\kappa T_{\mu\nu}
$$

and rewrite it in a form that makes $R_{00}$ easy to compare. Contracting both sides with $g^{\mu\nu}$, we have $g^{\mu\nu}R_{\mu\nu}=R$, and in four dimensions,

$$
g^{\mu\nu}g_{\mu\nu}=\delta^\mu_\mu=4
$$

so

$$
R-\frac12\cdot4R=\kappa T,
\qquad
T=g^{\mu\nu}T_{\mu\nu}
$$

Thus $R=-\kappa T$. Substituting this into the original equation and simplifying gives

$$
\boxed{
R_{\mu\nu}
=\kappa\left(T_{\mu\nu}-\frac12g_{\mu\nu}T\right)
}
$$


### Find the Time Component on the Matter Side

Let $\rho$ be the mass density of the gravitational source. Ignoring contributions from matter motion and pressure, the main part of the energy is rest energy, so

$$
T^{00}\simeq\rho c^2
$$

In this approximation, lowering the indices gives two factors of $g_{00}\simeq-1$, and hence

$$
T_{00}\simeq(-1)^2T^{00}=\rho c^2
$$

On the other hand, the contraction $T$ contains one inverse metric, so

$$
T=g^{\mu\nu}T_{\mu\nu}
\simeq g^{00}T_{00}
\simeq-\rho c^2
$$

Spatial components and similar terms are neglected here as small.

Therefore, the time component of the field equation is

$$
\begin{aligned}
R_{00}
&=\kappa\left(T_{00}-\frac12g_{00}T\right)\\
&\simeq\kappa\left[
\rho c^2-\frac12(-1)(-\rho c^2)
\right]\\
&=\frac{\kappa}{2}\rho c^2
\end{aligned}
$$


### Find the Time Component on the Curvature Side

Substituting the curvature definition (7.2) into the Ricci tensor definition $R_{00}={R^\alpha}_{0\alpha0}$ gives

$$
R_{00}
=\partial_\alpha\Gamma^\alpha_{00}
-\partial_0\Gamma^\alpha_{\alpha0}
+\Gamma^\alpha_{\alpha\beta}\Gamma^\beta_{00}
-\Gamma^\alpha_{0\beta}\Gamma^\beta_{\alpha0}
$$

The connection is first order in weak gravity, so products of connections are neglected as second order. We also set time derivatives to zero. Then only

$$
R_{00}\simeq\sum_{i=1}^3\partial_i\Gamma^i_{00}
$$

remains. Substituting $\Gamma^i_{00}\simeq\partial_i\Phi/c^2$, obtained by comparing the motion, gives

$$
\begin{aligned}
R_{00}
&\simeq\frac1{c^2}\sum_{i=1}^3\partial_i\partial_i\Phi\\
&=\frac1{c^2}\left(
\frac{\partial^2\Phi}{\partial x^2}
+\frac{\partial^2\Phi}{\partial y^2}
+\frac{\partial^2\Phi}{\partial z^2}
\right)
\end{aligned}
$$


### Compare with Newton’s Field Equation

In Newtonian theory, mass density $\rho$ and potential $\Phi$ are related by the Poisson equation,

$$
\frac{\partial^2\Phi}{\partial x^2}
+\frac{\partial^2\Phi}{\partial y^2}
+\frac{\partial^2\Phi}{\partial z^2}
=4\pi G\rho
$$

The origin of this Poisson equation can be checked in the end-of-chapter [“Appendix: From Comparison with the Electrostatic Field to the Poisson Equation”](#appendix-from-comparison-with-the-electrostatic-field-to-the-poisson-equation).

Therefore, the curvature-side value that agrees with Newtonian theory is

$$
R_{00}\simeq\frac{4\pi G}{c^2}\rho
$$

On the other hand, the matter side gave $R_{00}\simeq(\kappa/2)\rho c^2$. Comparing the coefficients so that the two agree for the same mass density,

$$
\frac{\kappa c^2}{2}=\frac{4\pi G}{c^2}
$$

and therefore

$$
\boxed{\kappa=\frac{8\pi G}{c^4}}
$$


The constant $\kappa=8\pi G/c^4$ determined by this comparison is also used in the general Einstein equation.

## Appendix: From Comparison with the Electrostatic Field to the Poisson Equation

Let us check the Poisson equation for Newtonian gravity by comparing it with the electrostatic field. We use the three-dimensional Euclidean space of Newtonian theory, and $\nabla$ denotes the ordinary spatial derivative.

### Compare Electric Potential and Gravitational Potential

The electric potential $V$ of a point charge $Q$ at the origin and the gravitational potential $\Phi$ of a point mass $M$, both chosen to be zero at infinity, are

$$
V=\frac{1}{4\pi\varepsilon_0}\frac{Q}{r},
\qquad
\Phi=-\frac{GM}{r}
$$

Here $\varepsilon_0$ is the vacuum permittivity, a different quantity from the energy density $\varepsilon$. Both potentials are proportional to $1/r$, with different coefficients and signs.

The electric field $\boldsymbol E$ and gravitational acceleration $\boldsymbol g$ are respectively the negative gradients of their potentials.

$$
\boldsymbol E=-\nabla V,
\qquad
\boldsymbol g=-\nabla\Phi.
$$

Since this case is spherically symmetric, we only need to differentiate in the radial direction. With outward unit vector $\boldsymbol e_r$,

$$
\boldsymbol E
=-\frac{dV}{dr}\boldsymbol e_r
=\frac{Q}{4\pi\varepsilon_0r^2}\boldsymbol e_r,
\qquad
\boldsymbol g
=-\frac{d\Phi}{dr}\boldsymbol e_r
=-\frac{GM}{r^2}\boldsymbol e_r
$$

The electric field produced by positive charge points outward, whereas the gravitational field produced by positive mass points inward.

### Count the Flux Through a Sphere

Consider a sphere of radius $r$ centered at the origin. Let $d\boldsymbol S$ be its outward area vector. The flux of a field is the sum, over the entire surface, of the component perpendicular to the surface.

![The electric field of positive charge points outward, while the gravitational field of positive mass points inward. In both cases, the area vector points outward from the sphere.](../../../images/general-relativity/08/field-flux.svg)

The field magnitude is constant on the sphere, so multiplying by its area $4\pi r^2$ gives

$$
\oint\boldsymbol E\cdot d\boldsymbol S
=\frac{Q}{4\pi\varepsilon_0r^2}\,4\pi r^2
=\frac{Q}{\varepsilon_0},
$$

$$
\oint\boldsymbol g\cdot d\boldsymbol S
=-\frac{GM}{r^2}\,4\pi r^2
=-4\pi GM
$$

The $r^{-2}$ in the inverse-square law cancels the $r^2$ in the sphere’s area, so the flux does not depend on the sphere’s radius. The $4\pi$ on the gravity side comes from this sphere area.

---

Alice: “Even though the field becomes weaker farther away, the flux through the entire sphere stays the same.”

Bob: “When the radius doubles, the field strength becomes one quarter while the sphere’s area becomes four times larger. The gravitational flux is negative because the field points inward through a surface whose outward direction is counted as positive.”

---

This relation extends to any closed surface. Express the extent of the surface as seen from a point source by the solid angle $d\Omega$. If $\vartheta$ is the angle between the outward normal and the radial direction,

$$
d\Omega=\frac{\cos\vartheta\,dS}{r^2}
$$

For a closed surface enclosing the point source, the sum of these signed solid angles is $4\pi$. If the point source is outside, entering and leaving contributions cancel, giving zero.

Therefore, flux is determined not by the shape of the closed surface, but by the charge or mass inside it. Adding the fields of multiple point sources and extending this to a continuous distribution, for a region $\mathcal V$ we obtain

$$
\oint_{\partial\mathcal V}\boldsymbol E\cdot d\boldsymbol S
=\frac1{\varepsilon_0}\int_{\mathcal V}\rho_e\,dV,
\qquad
\oint_{\partial\mathcal V}\boldsymbol g\cdot d\boldsymbol S
=-4\pi G\int_{\mathcal V}\rho\,dV
$$

Here $\rho_e$ is charge density and $\rho$ is mass density. These are Gauss’s laws for the respective fields.

### From Flux to an Equation at Each Point

By the divergence theorem, the flux through a closed surface equals the integral of the field’s divergence inside it.

$$
\oint_{\partial\mathcal V}\boldsymbol g\cdot d\boldsymbol S
=\int_{\mathcal V}\nabla\cdot\boldsymbol g\,dV.
$$

Therefore, for gravity,

$$
\int_{\mathcal V}\nabla\cdot\boldsymbol g\,dV
=-4\pi G\int_{\mathcal V}\rho\,dV
$$

Since this holds for every small region, for a smooth mass distribution it holds at every point:

$$
\nabla\cdot\boldsymbol g=-4\pi G\rho
$$

Similarly, for the electrostatic field,

$$
\nabla\cdot\boldsymbol E=\frac{\rho_e}{\varepsilon_0}
$$


Finally, express the fields in terms of potentials. Substituting $\boldsymbol E=-\nabla V$ and $\boldsymbol g=-\nabla\Phi$ gives

$$
\boxed{\nabla^2V=-\frac{\rho_e}{\varepsilon_0}},
\qquad
\boxed{\nabla^2\Phi=4\pi G\rho}
$$

where

$$
\nabla^2
=\frac{\partial^2}{\partial x^2}
+\frac{\partial^2}{\partial y^2}
+\frac{\partial^2}{\partial z^2}
$$

The minus sign in Gauss’s law for gravity cancels the minus sign in $\boldsymbol g=-\nabla\Phi$, so the right-hand side of the gravitational-potential equation is positive.

This does not derive the law of gravity from the law of the electrostatic field. It uses the inverse-square law and superposition shared by electric fields and Newtonian gravity to express each as a differential equation for its potential.
