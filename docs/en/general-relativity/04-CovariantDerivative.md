# How Do We Compare Vectors at Different Locations?

## Introduction

In the previous document, “The Metric as a Ruler for Spacetime,” we saw that when a plane is expressed in polar coordinates,

$$
ds^2 =
dr^2+r^2d\theta^2
$$

This describes the same plane as

$$
ds^2 =
dx^2+dy^2
$$

written in Cartesian coordinates.

In polar coordinates, the components of the metric change from place to place. However, from this change alone, we cannot tell whether it comes from our choice of coordinates or from a geometric property of space or spacetime itself.

To investigate this question, we need to compare slightly separated locations.

But vectors at different locations cannot be compared as they are.

In this document, we will consider, in order,

- why we cannot simply subtract vectors at different locations,
- what ordinary differentiation overlooks,
- what a basis is when we break a vector into components,
- how to include changes in the coordinate directions in differentiation,
- what the covariant derivative of a vector represents, and
- how to find the covariant derivative of lower-index quantities and second-rank tensors.

Our goal is to develop a feeling for the idea that

> The covariant derivative measures not only changes in a vector’s components, but also changes in the coordinate directions used to express those components.

## Breaking a Vector into Components

Suppose there is a vector $\boldsymbol{V}$ on a plane.

We can think of a vector as an arrow with a magnitude and a direction.

To express this arrow using coordinate numbers, we must first decide which directions to use to break it apart.

In Cartesian coordinates $(x,y)$, we prepare one arrow in the direction of increasing $x$ and another in the direction of increasing $y$.

We write them as

$$
\boldsymbol{e}_x,
\qquad
\boldsymbol{e}_y.
$$

The vector $\boldsymbol{V}$ can be written as

$$
\boldsymbol{V} =
V^x\boldsymbol{e}_x
+
V^y\boldsymbol{e}_y.
$$

$V^x$ is a number that tells us how far to go in the direction of $\boldsymbol e_x$, and $V^y$ tells us how far to go in the direction of $\boldsymbol e_y$. These two numbers are the components of the vector.

Meanwhile,

$$
\boldsymbol{e}_x,
\qquad
\boldsymbol{e}_y
$$

are direction arrows used to assemble the components into the actual vector.

Such a set of arrows is called a basis.

> A vector is the arrow itself, while its components are the numbers used to express that arrow in a chosen basis.

If we change the basis, the component numbers that express the same vector change. The arrow itself, however, has not changed.

This restates in terms of a basis what we saw in Chapter 1: when we change the coordinate axes, the components of the same arrow change.

![Alice and Bob checking that the same components produce arrows pointing in different directions at different points on a mountain trail](../../../images/general-relativity/04/local-basis-on-mountain-trail.webp)

## Making a Basis for Each Coordinate

Let us write general coordinates as $x^\mu$.

We prepare a basis vector in the direction in which each coordinate $x^\mu$ increases and write it as

$$
\boldsymbol{e}_\mu.
$$

A vector can be written as

$$
\boxed{
\boldsymbol{V} =
V^\mu\boldsymbol{e}_\mu
}.
$$

Because the same index $\mu$ appears once above and once below, we sum over all coordinate directions.

In two dimensions, this equation means

$$
\boldsymbol{V} =
V^1\boldsymbol{e}_1
+
V^2\boldsymbol{e}_2.
$$

A basis made from coordinates in this way is called a coordinate basis.

The coordinate basis $\boldsymbol e_\mu$ represents the direction and amount of the actual displacement produced when only $x^\mu$ is increased slightly while the other coordinates are held fixed.

The vector for an infinitesimal displacement can also be written as

$$
d\boldsymbol{x} =
dx^\mu\boldsymbol{e}_\mu.
$$

An important point here is that a basis vector does not necessarily have length $1$.

In Cartesian coordinates, we normally choose

$$
\boldsymbol{e}_x,
\qquad
\boldsymbol{e}_y
$$

as mutually perpendicular arrows of length $1$.

However, a basis made from general coordinates may change its direction or its length from place to place.

In polar coordinates $(r,\theta)$,

$$
\boldsymbol{e}_r
$$

represents the direction in which $r$ increases, while

$$
\boldsymbol{e}_\theta
$$

represents the direction in which $\theta$ increases.

The length of $\boldsymbol e_r$ is $1$, but the length of $\boldsymbol e_\theta$ is $r$.

$\boldsymbol e_\theta$ is not a unit vector of length $1$ pointing in the angular direction. It is a coordinate basis vector that converts a change in the coordinate $\theta$ into an actual displacement.

Therefore, in

$$
d\boldsymbol{x} =
dr\,\boldsymbol{e}_r
+
d\theta\,\boldsymbol{e}_\theta,
$$

the length in the angular direction is

$$
\left|d\theta\,\boldsymbol{e}_\theta\right| =
r\,d\theta.
$$

This is the same reason that $r^2$ appeared in

$$
ds^2 =
dr^2+r^2d\theta^2
$$

in the previous document.

---

Alice: “The components alone do not make the arrow itself.”

Bob: “Right. We also need the basis that gives the directions of the arrows and tells us which one each component multiplies.”

Alice: “And in polar coordinates, the directions and lengths of those basis vectors change from place to place.”

---

![Alice and Bob observing polar-coordinate basis vectors whose directions and lengths change from place to place around a lighthouse by the sea](../../../images/general-relativity/04/polar-basis-by-the-sea.webp)

## The Same Components Do Not Necessarily Mean the Same Direction

Consider two points P and Q on a plane.

At each point, place the polar-coordinate basis

$$
\boldsymbol{e}_r,
\qquad
\boldsymbol{e}_\theta.
$$

At P and Q, consider vectors with the components

$$
V^r=1,
\qquad
V^\theta=0.
$$

Each points in the same direction as $\boldsymbol e_r$ at its own location.

However, if the angle $\theta$ differs between P and Q, the two vectors $\boldsymbol e_r$ point in different directions on the plane.

Therefore, even though the two vectors have the same components, they do not actually point in the same direction.

---

Alice: “They are both $(1,0)$, but their arrows point in different directions?”

Bob: “That is because $(1,0)$ is not the vector itself. It is a set of components that multiplies the basis. The vector at P can be written as”

$$
\boldsymbol{V}(P) =
1\,\boldsymbol{e}_r(P)
+
0\,\boldsymbol{e}_\theta(P) =
\boldsymbol{e}_r(P).
$$

Bob: “At Q, on the other hand, it is”

$$
\boldsymbol{V}(Q) =
1\,\boldsymbol{e}_r(Q)
+
0\,\boldsymbol{e}_\theta(Q) =
\boldsymbol{e}_r(Q).
$$

Bob: “The sets of components are the same, but $\boldsymbol e_r(P)$ and $\boldsymbol e_r(Q)$ point in different directions, so the two vectors also point in different directions.”

Alice: “So we need to look not only at the numbers, but also at the basis at the location with which those numbers are combined.”

---

When comparing vectors at different locations, we must consider changes in the basis as well as changes in the components.

## Differentiating the Entire Vector

Write a vector field as

$$
\boldsymbol{V} =
V^\nu\boldsymbol{e}_\nu.
$$

$V^\nu$ are the components of the vector, and $\boldsymbol e_\nu$ is the basis at that location.

We want to examine how the entire vector changes when we move in the direction of the coordinate $x^\mu$.

Using the product rule gives

$$
\partial_\mu\boldsymbol{V} =
\partial_\mu
\left(
V^\nu\boldsymbol{e}_\nu
\right)
$$

$$
= \left(
\partial_\mu V^\nu
\right)
\boldsymbol{e}_\nu
+
V^\nu
\partial_\mu\boldsymbol{e}_\nu.
$$

There are two kinds of change on the right-hand side.

The first is the change in the components,

$$
\partial_\mu V^\nu.
$$

The second is the change in the basis,

$$
\partial_\mu\boldsymbol{e}_\nu.
$$

If we apply an ordinary derivative only to the components, we overlook the second change.

The Cartesian-coordinate basis points in the same directions everywhere, so this problem is not noticeable. The directions and magnitudes of the polar-coordinate basis, however, change from place to place.

To make a derivative that works in general coordinates, we need to include changes in the basis in the equation as well.

## Expressing Changes in the Basis with Components

A change in a basis vector can also be expressed using the basis at that location.

We therefore write

$$
\partial_\mu\boldsymbol{e}_\nu =
\Gamma^\rho_{\mu\nu}
\boldsymbol{e}_\rho.
$$

$\Gamma^\rho_{\mu\nu}$ is a coefficient that tells us how the basis vector $\boldsymbol e_\nu$ changes when we move in the direction of $x^\mu$.

These coefficients are called the Christoffel symbols, or connection coefficients.

Substituting this into the derivative of the vector above gives

$$
\partial_\mu\boldsymbol{V} =
\left(
\partial_\mu V^\rho
+
\Gamma^\rho_{\mu\nu}V^\nu
\right)
\boldsymbol{e}_\rho.
$$

The expression in parentheses includes both the change in the components and the change in the basis.

This combination is called the covariant derivative of a vector.

$$
\boxed{
\nabla_\mu V^\rho =
\partial_\mu V^\rho
+
\Gamma^\rho_{\mu\nu}V^\nu
}.
$$

Let us summarize once more how this definition is related to the derivative of the entire vector.

Writing the entire vector as

$$
\boldsymbol{V} =
V^\nu\boldsymbol{e}_\nu
$$

and differentiating gives

$$
\begin{aligned}
\partial_\mu\boldsymbol{V}
&=
\partial_\mu
\left(
V^\nu\boldsymbol{e}_\nu
\right)\\
&=
\left(
\partial_\mu V^\nu
\right)
\boldsymbol{e}_\nu
+
V^\nu
\partial_\mu\boldsymbol{e}_\nu.
\end{aligned}
$$

Substituting the definition of the Christoffel symbols,

$$
\partial_\mu\boldsymbol{e}_\nu =
\Gamma^\rho_{\mu\nu}\boldsymbol{e}_\rho,
$$

and renaming the index in the first term from $\nu$ to $\rho$, we obtain

$$
\begin{aligned}
\partial_\mu\boldsymbol{V}
&=
\left(
\partial_\mu V^\rho
\right)
\boldsymbol{e}_\rho
+
\Gamma^\rho_{\mu\nu}V^\nu
\boldsymbol{e}_\rho\\
&=
\left(
\partial_\mu V^\rho
+
\Gamma^\rho_{\mu\nu}V^\nu
\right)
\boldsymbol{e}_\rho\\
&=
\left(
\nabla_\mu V^\rho
\right)
\boldsymbol{e}_\rho.
\end{aligned}
$$

Therefore,

$$
\boxed{
\partial_\mu\boldsymbol{V} =
\left(
\nabla_\mu V^\rho
\right)
\boldsymbol{e}_\rho
}.
$$

In other words, the covariant derivative $\nabla_\mu V^\rho$ consists of the components, in the basis at that location, of the change $\partial_\mu\boldsymbol{V}$ in the entire vector.

For a vector whose direction and length are fixed on a plane,

$$
\partial_\mu\boldsymbol{V}=0.
$$

Because the basis vectors $\boldsymbol e_\rho$ are independent, for

$$
\left(
\nabla_\mu V^\rho
\right)
\boldsymbol{e}_\rho
=0
$$

to hold, the coefficient multiplying each basis vector must be zero.

Therefore,

$$
\boxed{
\nabla_\mu V^\rho=0
}.
$$

The covariant derivative is not zero because the derivative of the components and the Christoffel-symbol term happen to cancel. It is necessarily zero when the entire vector is fixed because the covariant derivative was constructed to represent the change in the entire vector.

In a general curved space, however, vectors at separated locations cannot be given the “same direction” independently of a path. Later, we will define parallel transport as transporting a vector so that its covariant derivative along a specified path is zero.

What matters here is not the name of the notation, but the idea

$$
\text{change in the entire vector} =
\text{change in the components}
+
\text{change in the basis}.
$$

## How Does the Polar-Coordinate Basis Change?

Write the position vector on a plane as

$$
\boldsymbol{x}(r,\theta) =
\begin{pmatrix}
r\cos\theta\\
r\sin\theta
\end{pmatrix}.
$$

The position vector $\boldsymbol{x}$ changes with both $r$ and $\theta$. Its total differential is

$$
d\boldsymbol{x} =
\frac{\partial\boldsymbol{x}}{\partial r}dr
+
\frac{\partial\boldsymbol{x}}{\partial\theta}d\theta.
$$

Carrying out the differentiation gives

$$
\begin{aligned}
d\boldsymbol{x}
&=
d
\begin{pmatrix}
r\cos\theta\\
r\sin\theta
\end{pmatrix}\\
&=
\begin{pmatrix}
\cos\theta\\
\sin\theta
\end{pmatrix}
dr
+
\begin{pmatrix}
-r\sin\theta\\
r\cos\theta
\end{pmatrix}
d\theta.
\end{aligned}
$$

On the other hand, an infinitesimal displacement in polar coordinates can be expressed using the coordinate basis in the $r$ and $\theta$ directions as

$$
d\boldsymbol{x} =
\boldsymbol{e}_r\,dr
+
\boldsymbol{e}_\theta\,d\theta.
$$

Comparing the vectors that multiply $dr$ and $d\theta$ in the two equations, respectively, we find that the polar-coordinate basis is

$$
\boldsymbol{e}_r =
\frac{\partial\boldsymbol{x}}{\partial r} =
\begin{pmatrix}
\cos\theta\\
\sin\theta
\end{pmatrix}
$$

$$
\boldsymbol{e}_\theta =
\frac{\partial\boldsymbol{x}}{\partial\theta} =
\begin{pmatrix}
-r\sin\theta\\
r\cos\theta
\end{pmatrix}.
$$

Thus, the coordinate basis arises naturally from the total differential of the position vector as

$$
\boxed{
\boldsymbol{e}_r =
\frac{\partial\boldsymbol{x}}{\partial r},
\qquad
\boldsymbol{e}_\theta =
\frac{\partial\boldsymbol{x}}{\partial\theta}
}.
$$

The length of $\boldsymbol e_r$ is $1$, while the length of $\boldsymbol e_\theta$ is $r$.

This also appears in the metric components

$$
g_{rr}=1,
\qquad
g_{\theta\theta}=r^2.
$$

Let us differentiate the basis vectors.

First,

$$
\partial_r\boldsymbol{e}_r=0.
$$

Meanwhile,

$$
\partial_\theta\boldsymbol{e}_r =
\begin{pmatrix}
-\sin\theta\\
\cos\theta
\end{pmatrix} =
\frac{1}{r}\boldsymbol{e}_\theta.
$$

Also,

$$
\partial_r\boldsymbol{e}_\theta =
\begin{pmatrix}
-\sin\theta\\
\cos\theta
\end{pmatrix} =
\frac{1}{r}\boldsymbol{e}_\theta,
$$

and

$$
\partial_\theta\boldsymbol{e}_\theta =
\begin{pmatrix}
-r\cos\theta\\
-r\sin\theta
\end{pmatrix} =
-r\boldsymbol{e}_r.
$$

Recall that the definition of the Christoffel symbols is

$$
\partial_\mu\boldsymbol{e}_\nu =
\Gamma^\rho_{\mu\nu}\boldsymbol{e}_\rho.
$$

In two-dimensional polar coordinates, we sum over the index $\rho$ on the right-hand side, so we can expand this as

$$
\partial_\mu\boldsymbol{e}_\nu =
\Gamma^r_{\mu\nu}\boldsymbol{e}_r
+
\Gamma^\theta_{\mu\nu}\boldsymbol{e}_\theta.
$$

The three indices tell us

- $\mu$: which coordinate direction to differentiate in,
- $\nu$: which basis vector to differentiate, and
- $\rho$: which basis direction the result of the differentiation points in.

First, compare

$$
\partial_r\boldsymbol{e}_r=0
$$

with the definition.

$$
\partial_r\boldsymbol{e}_r =
\Gamma^r_{rr}\boldsymbol{e}_r
+
\Gamma^\theta_{rr}\boldsymbol{e}_\theta
=0.
$$

Therefore,

$$
\Gamma^r_{rr}=0,
\qquad
\Gamma^\theta_{rr}=0.
$$

Next, comparing

$$
\partial_\theta\boldsymbol{e}_r =
\frac{1}{r}\boldsymbol{e}_\theta
$$

gives

$$
\partial_\theta\boldsymbol{e}_r =
\Gamma^r_{\theta r}\boldsymbol{e}_r
+
\Gamma^\theta_{\theta r}\boldsymbol{e}_\theta =
\frac{1}{r}\boldsymbol{e}_\theta,
$$

so

$$
\Gamma^r_{\theta r}=0,
\qquad
\Gamma^\theta_{\theta r} =
\frac{1}{r}.
$$

Similarly, comparing

$$
\partial_r\boldsymbol{e}_\theta =
\frac{1}{r}\boldsymbol{e}_\theta
$$

gives

$$
\partial_r\boldsymbol{e}_\theta =
\Gamma^r_{r\theta}\boldsymbol{e}_r
+
\Gamma^\theta_{r\theta}\boldsymbol{e}_\theta =
\frac{1}{r}\boldsymbol{e}_\theta,
$$

so

$$
\Gamma^r_{r\theta}=0,
\qquad
\Gamma^\theta_{r\theta} =
\frac{1}{r}.
$$

Finally, comparing

$$
\partial_\theta\boldsymbol{e}_\theta =
-r\boldsymbol{e}_r
$$

gives

$$
\partial_\theta\boldsymbol{e}_\theta =
\Gamma^r_{\theta\theta}\boldsymbol{e}_r
+
\Gamma^\theta_{\theta\theta}\boldsymbol{e}_\theta =
-r\boldsymbol{e}_r,
$$

so

$$
\Gamma^r_{\theta\theta}=-r,
\qquad
\Gamma^\theta_{\theta\theta}=0.
$$

Putting these results together, the nonzero Christoffel symbols are

$$
\boxed{
\Gamma^r_{\theta\theta}=-r,
\qquad
\Gamma^\theta_{r\theta} =
\Gamma^\theta_{\theta r} =
\frac{1}{r}
},
$$

and all other components are zero.

The plane itself has not changed. These Christoffel symbols appear because the polar-coordinate basis changes from place to place.

## The Christoffel Symbols Are Not a Tensor

When the same plane is expressed in Cartesian coordinates, the basis is constant and does not depend on location.

Therefore, in Cartesian coordinates,

$$
\Gamma^\rho_{\mu\nu}=0.
$$

However, when the same plane is expressed in polar coordinates,

$$
\Gamma^r_{\theta\theta}=-r,
\qquad
\Gamma^\theta_{r\theta} =
\Gamma^\theta_{\theta r} =
\frac{1}{r}.
$$

They are all zero in one coordinate system but nonzero in another. This way of changing differs from the transformation rule for a tensor.

Therefore, the Christoffel symbols themselves are not a tensor.

This is not a defect. For polar coordinates on the plane considered here, the Christoffel symbols appear as coefficients that compensate for changes in the basis caused by the coordinates.

The ordinary derivative $\partial_\mu V^\nu$ is not a tensor by itself either. The combination

$$
\nabla_\mu V^\nu =
\partial_\mu V^\nu
+
\Gamma^\nu_{\mu\rho}V^\rho
$$

transforms as a tensor with one lower index and one upper index.

Under a coordinate transformation, extra terms that do not follow the tensor transformation rule appear in the ordinary derivative $\partial_\mu V^\nu$. The Christoffel-symbol term transforms so as to cancel those extra terms. For now, let us keep this mechanism in mind. We will explicitly check that the covariant derivative $\nabla_\mu V^\nu$ transforms as a tensor later, in [06, “Why Is the Covariant Derivative a Tensor?”](./06-ParallelTransportAndGeodesics.md#why-is-the-covariant-derivative-a-tensor).

---

Alice: “We use something that is not a tensor to make a tensor?”

Bob: “Yes. The Christoffel symbols exactly cancel the extra changes that appear in the ordinary derivative.”

---

## The Components Change Even Though the Vector Is the Same

Let us look at a specific example.

Consider a vector of length $1$ pointing in the positive $x$ direction in Cartesian coordinates.

This vector points in the same direction everywhere and does not change on the plane.

![Alice and Bob breaking a vector that points in a fixed direction on a field into different polar-coordinate basis vectors at each location](../../../images/general-relativity/04/fixed-vector-changing-components.webp)

In Cartesian components, it is

$$
\boldsymbol{V} =
\begin{pmatrix}
1\\
0
\end{pmatrix}.
$$

Meanwhile, the polar-coordinate basis was

$$
\boldsymbol{e}_r =
\begin{pmatrix}
\cos\theta\\
\sin\theta
\end{pmatrix}
$$

$$
\boldsymbol{e}_\theta =
\begin{pmatrix}
-r\sin\theta\\
r\cos\theta
\end{pmatrix}.
$$

We want to express $\boldsymbol{V}$ as a linear combination of the two polar-coordinate basis vectors:

$$
\boldsymbol{V} =
V^r\boldsymbol{e}_r
+
V^\theta\boldsymbol{e}_\theta.
$$

The polar-coordinate basis vectors are perpendicular to each other, and their inner products are

$$
\boldsymbol{e}_r\cdot\boldsymbol{e}_r=1,
\qquad
\boldsymbol{e}_r\cdot\boldsymbol{e}_\theta=0,
\qquad
\boldsymbol{e}_\theta\cdot\boldsymbol{e}_\theta=r^2.
$$

First, taking the inner product of $\boldsymbol{V}$ and $\boldsymbol e_r$ gives

$$
\begin{aligned}
\boldsymbol{V}\cdot\boldsymbol{e}_r
&=
V^r
\left(
\boldsymbol{e}_r\cdot\boldsymbol{e}_r
\right)
+
V^\theta
\left(
\boldsymbol{e}_\theta\cdot\boldsymbol{e}_r
\right)\\
&=V^r.
\end{aligned}
$$

On the other hand, calculating with the Cartesian components gives

$$
\boldsymbol{V}\cdot\boldsymbol{e}_r =
\begin{pmatrix}
1\\
0
\end{pmatrix}
\cdot
\begin{pmatrix}
\cos\theta\\
\sin\theta
\end{pmatrix} =
\cos\theta,
$$

so

$$
V^r=\cos\theta.
$$

Similarly, taking the inner product with $\boldsymbol e_\theta$ gives

$$
\boldsymbol{V}\cdot\boldsymbol{e}_\theta =
r^2V^\theta.
$$

On the other hand,

$$
\boldsymbol{V}\cdot\boldsymbol{e}_\theta =
\begin{pmatrix}
1\\
0
\end{pmatrix}
\cdot
\begin{pmatrix}
-r\sin\theta\\
r\cos\theta
\end{pmatrix} =
-r\sin\theta,
$$

so

$$
r^2V^\theta=-r\sin\theta.
$$

Therefore,

$$
V^\theta=-\frac{\sin\theta}{r}.
$$

Thus, expressing the same vector in the polar-coordinate basis gives

$$
\boldsymbol{V} =
\cos\theta\,\boldsymbol{e}_r -
\frac{\sin\theta}{r}\boldsymbol{e}_\theta.
$$

Even if we parallel transport this vector to another point on the plane, the arrow itself remains a vector of length $1$ pointing in the positive $x$ direction.

At the destination, however, the directions and lengths of the polar-coordinate basis vectors $\boldsymbol e_r$ and $\boldsymbol e_\theta$ have changed. Therefore, when we express the same arrow in the polar-coordinate basis at the destination, the numbers in the components $V^r$ and $V^\theta$ change.

In other words, even if parallel transport does not change the vector itself, its polar-coordinate components change from place to place.

Before calculating, let us check why the derivative of the components and the Christoffel-symbol term cancel.

Because this vector does not change on the plane, differentiating the entire vector with respect to $\theta$ gives

$$
\partial_\theta\boldsymbol{V}=0.
$$

On the other hand, differentiating

$$
\boldsymbol{V} =
V^r\boldsymbol{e}_r
+
V^\theta\boldsymbol{e}_\theta
$$

with the product rule gives

$$
\begin{aligned}
\partial_\theta\boldsymbol{V}
&=
\left(\partial_\theta V^r\right)\boldsymbol{e}_r
+
V^r\partial_\theta\boldsymbol{e}_r\\
&\quad
+
\left(\partial_\theta V^\theta\right)\boldsymbol{e}_\theta
+
V^\theta\partial_\theta\boldsymbol{e}_\theta.
\end{aligned}
$$

Substituting the derivatives of the polar-coordinate basis,

$$
\partial_\theta\boldsymbol{e}_r =
\frac{1}{r}\boldsymbol{e}_\theta
$$

$$
\partial_\theta\boldsymbol{e}_\theta =
-r\boldsymbol{e}_r,
$$

gives

$$
\begin{aligned}
\partial_\theta\boldsymbol{V}
&=
\left(
\partial_\theta V^r-rV^\theta
\right)\boldsymbol{e}_r\\
&\quad+
\left(
\partial_\theta V^\theta+\frac{1}{r}V^r
\right)\boldsymbol{e}_\theta.
\end{aligned}
$$

For the entire vector not to change, the coefficients multiplying the two independent basis vectors must each be zero.

Therefore,

$$
\partial_\theta V^r-rV^\theta=0
$$

$$
\partial_\theta V^\theta+\frac{1}{r}V^r=0.
$$

Because

$$
\Gamma^r_{\theta\theta}=-r,
\qquad
\Gamma^\theta_{\theta r}=\frac{1}{r},
$$

these two equations are precisely

$$
\nabla_\theta V^r =
\partial_\theta V^r
+
\Gamma^r_{\theta\theta}V^\theta
=0
$$

$$
\nabla_\theta V^\theta =
\partial_\theta V^\theta
+
\Gamma^\theta_{\theta r}V^r
=0.
$$

Thus, the Christoffel symbols are not quantities chosen afterward to make the result of the calculation happen to be zero. Because they are defined as the coefficients that appear when the basis is differentiated, the change in the components and the change in the basis correspond within a single equation from the beginning.

Indeed, substituting

$$
V^r=\cos\theta,
\qquad
V^\theta=-\frac{\sin\theta}{r}
$$

gives

$$
\begin{aligned}
\nabla_\theta V^r
&=
-\sin\theta
+
(-r)
\left(
-\frac{\sin\theta}{r}
\right)
=0,\\
\nabla_\theta V^\theta
&=
-\frac{\cos\theta}{r}
+
\frac{1}{r}\cos\theta
=0,
\end{aligned}
$$

which agrees with the result we derived above from the derivative of the entire vector.

## The Covariant Derivative of a Lower Index

So far, we have considered a vector with an upper index.

The equation for a covector $A_\nu$ with a lower index can be derived from the upper-index case.
For this purpose, consider the scalar

$$
f=A_\nu V^\nu
$$

formed by contracting $A_\nu$ with an arbitrary vector $V^\nu$.

The covariant derivative of a scalar is the same as its ordinary partial derivative, so we must have

$$
\nabla_\mu f =
\partial_\mu f.
$$

Meanwhile, if we require the covariant derivative to obey the product rule, then

$$
\nabla_\mu(A_\nu V^\nu) =
(\nabla_\mu A_\nu)V^\nu
+
A_\nu(\nabla_\mu V^\nu).
$$

On the right-hand side, substitute the covariant derivative of a vector that we already know,

$$
\nabla_\mu V^\nu =
\partial_\mu V^\nu
+
\Gamma^\nu_{\mu\rho}V^\rho.
$$

The left-hand side, on the other hand, is the partial derivative of a scalar, so

$$
\partial_\mu(A_\nu V^\nu) =
(\partial_\mu A_\nu)V^\nu
+
A_\nu\partial_\mu V^\nu.
$$

Setting the two sides equal, canceling the common term $A_\nu\partial_\mu V^\nu$, and aligning the indices gives

$$
(\partial_\mu A_\rho)V^\rho =
(\nabla_\mu A_\rho)V^\rho
+
A_\nu\Gamma^\nu_{\mu\rho}V^\rho.
$$

This must hold for any $V^\rho$, so

$$
\nabla_\mu A_\rho =
\partial_\mu A_\rho -
\Gamma^\nu_{\mu\rho}A_\nu.
$$

Renaming the free and dummy indices gives

$$
\boxed{
\nabla_\mu A_\nu =
\partial_\mu A_\nu -
\Gamma^\rho_{\mu\nu}A_\rho
}.
$$

The connection term for a lower index has a minus sign so that it cancels the positive connection term produced by the upper index within the contracted scalar.

## The Covariant Derivative of a Second-Rank Tensor

We can use the same idea for a second-rank tensor.

Consider a mixed tensor $T^\rho{}_\nu$ with one upper index and one lower index.

If we contract all its indices using a covector $A_\rho$ and a vector $V^\nu$, then

$$
S =
A_\rho T^\rho{}_\nu V^\nu
$$

is a scalar. Therefore, we must have

$$
\nabla_\mu S =
\partial_\mu S.
$$

Using the product rule gives

$$
\begin{aligned}
\nabla_\mu S
={}&
(\nabla_\mu A_\rho)T^\rho{}_\nu V^\nu\\
&+
A_\rho(\nabla_\mu T^\rho{}_\nu)V^\nu\\
&+
A_\rho T^\rho{}_\nu(\nabla_\mu V^\nu).
\end{aligned}
$$

Into this, substitute the results already derived,

$$
\nabla_\mu A_\rho =
\partial_\mu A_\rho -
\Gamma^\sigma_{\mu\rho}A_\sigma,
\qquad
\nabla_\mu V^\nu =
\partial_\mu V^\nu
+
\Gamma^\nu_{\mu\sigma}V^\sigma.
$$

For the entire expression to become the ordinary partial derivative of the product, the connection terms produced by $A_\rho$ and $V^\nu$ must be canceled by the connection terms within $\nabla_\mu T^\rho{}_\nu$.
Therefore, the covariant derivative of a mixed tensor is

$$
\boxed{
\nabla_\mu T^\rho{}_\nu =
\partial_\mu T^\rho{}_\nu
+
\Gamma^\rho_{\mu\sigma}T^\sigma{}_\nu -
\Gamma^\sigma_{\mu\nu}T^\rho{}_\sigma
}.
$$

Let us actually substitute the three covariant-derivative equations into the product rule above.

$$
\begin{aligned}
\nabla_\mu S
={}&
\left(\partial_\mu A_\rho
-\Gamma^\sigma_{\mu\rho}A_\sigma\right)
T^\rho{}_\nu V^\nu\\
&+A_\rho\left(
\partial_\mu T^\rho{}_\nu
+\Gamma^\rho_{\mu\sigma}T^\sigma{}_\nu
-\Gamma^\sigma_{\mu\nu}T^\rho{}_\sigma
\right)V^\nu\\
&+A_\rho T^\rho{}_\nu
\left(\partial_\mu V^\nu
+\Gamma^\nu_{\mu\sigma}V^\sigma\right).
\end{aligned}
$$

There are three terms containing partial derivatives and four connection terms containing Christoffel symbols.
Let us confirm that the connection terms cancel in pairs.

First, the term produced by the covariant derivative of $A_\rho$ can be rewritten as

$$
-\Gamma^\sigma_{\mu\rho}A_\sigma T^\rho{}_\nu V^\nu
=-A_\rho\Gamma^\rho_{\mu\sigma}T^\sigma{}_\nu V^\nu.
$$

Here, we have simultaneously exchanged the names of the summed indices $\rho$ and $\sigma$.
This cancels the term

$$
+A_\rho\Gamma^\rho_{\mu\sigma}T^\sigma{}_\nu V^\nu
$$

produced by the covariant derivative of $T^\rho{}_\nu$.

Next, the term produced by the covariant derivative of $V^\nu$ can be rewritten as

$$
+A_\rho T^\rho{}_\nu\Gamma^\nu_{\mu\sigma}V^\sigma
=+A_\rho T^\rho{}_\sigma\Gamma^\sigma_{\mu\nu}V^\nu.
$$

This time, we have simultaneously exchanged the names of the summed indices $\nu$ and $\sigma$.
This cancels the term

$$
-A_\rho\Gamma^\sigma_{\mu\nu}T^\rho{}_\sigma V^\nu
$$

produced by the covariant derivative of $T^\rho{}_\nu$. In both renamings, the free index $\mu$, which represents the direction of differentiation, has not been changed.

Therefore, only the three terms containing ordinary partial derivatives remain.

$$
\begin{aligned}
\nabla_\mu S
={}&(\partial_\mu A_\rho)T^\rho{}_\nu V^\nu\\
&+A_\rho(\partial_\mu T^\rho{}_\nu)V^\nu\\
&+A_\rho T^\rho{}_\nu(\partial_\mu V^\nu)\\
={}&\partial_\mu\left(A_\rho T^\rho{}_\nu V^\nu\right)
=\partial_\mu S.
\end{aligned}
$$

We have now confirmed that the covariant derivative of the scalar formed by contraction agrees with its ordinary partial derivative.

Next, consider a tensor $T_{\mu\nu}$ with two lower indices.
Contracting it with any two vectors $V^\mu,W^\nu$ gives

$$
F=T_{\mu\nu}V^\mu W^\nu,
$$

which is a scalar. Therefore, $\nabla_\lambda F=\partial_\lambda F$.
Using the product rule for the covariant derivative on the left-hand side gives

$$
\begin{aligned}
\nabla_\lambda F
={}&(\nabla_\lambda T_{\mu\nu})V^\mu W^\nu\\
&+T_{\mu\nu}(\nabla_\lambda V^\mu)W^\nu\\
&+T_{\mu\nu}V^\mu(\nabla_\lambda W^\nu).
\end{aligned}
$$

Into this, substitute the covariant derivatives of the vectors,

$$
\nabla_\lambda V^\mu
=\partial_\lambda V^\mu+\Gamma^\mu_{\lambda\rho}V^\rho,
\qquad
\nabla_\lambda W^\nu
=\partial_\lambda W^\nu+\Gamma^\nu_{\lambda\rho}W^\rho.
$$

Meanwhile, the ordinary partial derivative on the right-hand side is

$$
\begin{aligned}
\partial_\lambda F
={}&(\partial_\lambda T_{\mu\nu})V^\mu W^\nu\\
&+T_{\mu\nu}(\partial_\lambda V^\mu)W^\nu\\
&+T_{\mu\nu}V^\mu(\partial_\lambda W^\nu).
\end{aligned}
$$

Set the two sides equal and cancel the common terms containing the partial derivatives of the vectors.
Renaming the dummy indices in the remaining connection terms and collecting the coefficients of $V^\mu W^\nu$ gives

$$
\left(
\nabla_\lambda T_{\mu\nu}
+\Gamma^\rho_{\lambda\mu}T_{\rho\nu}
+\Gamma^\rho_{\lambda\nu}T_{\mu\rho}
\right)V^\mu W^\nu =
(\partial_\lambda T_{\mu\nu})V^\mu W^\nu.
$$

This must hold for arbitrary $V^\mu,W^\nu$, so we obtain

$$
\boxed{
\nabla_\lambda T_{\mu\nu}
=\partial_\lambda T_{\mu\nu}
-\Gamma^\rho_{\lambda\mu}T_{\rho\nu}
-\Gamma^\rho_{\lambda\nu}T_{\mu\rho}
}.
$$

One negative connection term appears for each of the lower indices $\mu,\nu$.
These cancel the positive connection terms produced by the two vectors used in the contraction.

In the next chapter, we will apply this equation to the metric $g_{\mu\nu}$.

Because a scalar $f$ has no index that needs to be compensated for,

$$
\nabla_\mu f =
\partial_\mu f.
$$

From these results, instead of memorizing each equation separately, it is helpful to read them as the rules

- add one connection term for each upper index, and
- subtract one connection term for each lower index.

## Summary

- We must distinguish a vector itself from its components.
- A basis is a set of direction arrows that assembles components into an actual vector.
- A coordinate basis may change its direction or length from place to place.
- In polar coordinates,

  $$\boldsymbol{e}_r = \frac{\partial\boldsymbol{x}}{\partial r}, \qquad \boldsymbol{e}_\theta = \frac{\partial\boldsymbol{x}}{\partial\theta}$$

  holds.
- Because the basis differs at different locations, we cannot compare vector components directly.
- A change in the entire vector includes both a change in its components and a change in the basis.
- The Christoffel symbols express changes in the basis through components according to

  $$\partial_\mu\boldsymbol{e}_\nu = \Gamma^\rho_{\mu\nu}\boldsymbol{e}_\rho.$$

- The covariant derivative of a contravariant vector is

  $$\nabla_\mu V^\rho = \partial_\mu V^\rho + \Gamma^\rho_{\mu\nu}V^\nu.$$

- The covariant derivative consists of the components, in the basis at that location, of the change in the entire vector.
- For a vector fixed on a plane, the entire vector does not change, so the change in the components and the change in the basis necessarily cancel, and the covariant derivative is zero.
- The Christoffel symbols themselves are not a tensor.
- Add a connection term for an upper index, and subtract a connection term for a lower index.

## The Next Question

For polar coordinates on a plane, we made the coordinate basis from the position vector

$$
\boldsymbol{x}(r,\theta) =
\begin{pmatrix}
r\cos\theta\\
r\sin\theta
\end{pmatrix},
$$

then differentiated that basis directly to find the Christoffel symbols.

In general relativity, however, we do not prepare a position vector from which spacetime can be viewed from the outside and then differentiate its basis directly.

We normally begin with the metric $g_{\mu\nu}$, which tells us how to measure lengths and angles in spacetime.

Then can we find

$$
\Gamma^\rho_{\mu\nu}
$$

using only the metric?

In the next document, we will take the partial derivative of the metric as an inner product of basis vectors and derive, one step at a time, the formula for finding the Christoffel symbols from the metric.
