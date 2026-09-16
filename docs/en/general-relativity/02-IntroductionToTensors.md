# Equations That Survive a Change of Coordinates

## Introduction

In the previous document, “Combining Coordinates into One Notation,” we wrote the coordinates of time and space together as

$$
x^\mu
$$

We also wrote the line element of flat spacetime as

$$
ds^2
=
\eta_{\mu\nu}dx^\mu dx^\nu
$$

This was a shorter index-notation form of

$$
ds^2
=
-dw^2+dx^2+dy^2+dz^2
$$

When the coordinates change, the coordinate difference $dx^\mu$ assigned to the same two events changes. Even so, the line element $ds^2$ must have the same value.

Then the metric must also have a fixed way of changing, one that cancels the change in $dx^\mu$.

In this document, we will consider in order

- how $dx^\mu$ changes when we change coordinates,
- how upper and lower indices differ,
- how the metric changes, and
- roughly what a tensor is.

Our goal is not to construct a rigorous definition of a tensor.

Instead, the goal is to get a feel for this idea:

> When there is an equation that describes a physical phenomenon, each quantity has a fixed way of changing so that, even if changing coordinate systems changes the numbers in its components, the equation can still be written in exactly the same form.

## What Does It Mean to Change Coordinates?

Suppose there is a point P on a plane.

In one coordinate system, suppose the coordinates of P are

$$
(x,y)=(3,2)
$$

If we change the scale on the coordinate axes, we can assign different coordinates to the same P.

For example, define new coordinates by

$$
x'=2x
$$

$$
y'=y
$$

Then the new coordinates of P are

$$
(x',y')=(6,2)
$$

P has not moved to another location. We have only used a new scale that doubles the coordinate value in the $x$ direction.

---

Alice: “Even though it is the same place, we can write either $x=3$ or $x'=6$.”

Bob: “Right. The place itself has not changed; we changed the rule for the numbers we attach to the place.”

---

![Alice and Bob measuring the same point P with different scales](../../../images/general-relativity/02/same-place-different-coordinates.webp)

*Point P has not moved. The two coordinate systems assign different numbers to the same place*

What changes under a coordinate transformation is not the physical object itself, but the coordinate components used to represent it.

## Writing a Coordinate Transformation as an Equation

In general, we can write the new coordinates $x'^\mu$ as functions of the old coordinates $x^\nu$:

$$
x'^\mu
=
x'^\mu(x^0,x^1,x^2,x^3)
$$

We sometimes write this more briefly as

$$
x'^\mu=x'^\mu(x)
$$

This means that each of the four new coordinates is determined using the old coordinates.

For example, in two dimensions,

$$
x'=x'(x,y)
$$

$$
y'=y'(x,y)
$$

A coordinate transformation does not necessarily just double one coordinate. The new $x'$ may depend on both the old $x$ and $y$.

## How Do Small Coordinate Differences Change?

Suppose the new coordinates are given by

$$
x'^\mu=x'^\mu(x)
$$

If you see the phrase “total differential” for the first time, you may feel as though a difficult calculation is about to begin. But the idea here is simple.

First, in two dimensions, consider the case in which the new coordinate is defined by

$$
x'=x+2y
$$

If only $x$ changes by $dx$, then $x'$ changes by

$$
dx
$$

On the other hand, if only $y$ changes by $dy$, then $x'$ changes by

$$
2dy
$$

If $x$ and $y$ change at the same time, the change in the new coordinate $x'$ is found by adding the changes coming from the two directions:

$$
dx'=dx+2dy
$$

---

Alice: “So we just add the effect of the change in $x$ and the effect of the change in $y$ at the end.”

Bob: “Exactly. We find how much each old coordinate moves the new coordinate, then add them all.”

---

![Alice and Bob adding changes coming from two coordinate directions](../../../images/general-relativity/02/total-differential-contributions.webp)

*Adding $dx$ from the $x$ direction and $2dy$ from the $y$ direction gives the change $dx'$ in the new coordinate*

More generally, if

$$
x'=x'(x,y)
$$

then the effect on $x'$ of a small change in the $x$ direction is

$$
\frac{\partial x'}{\partial x}dx
$$

The quantity

$$
\frac{\partial x'}{\partial x}
$$

that appears here is the factor that tells us how much $x'$ changes when we hold $y$ still for the moment and change only $x$ a little.

Likewise, the effect coming from the $y$ direction is

$$
\frac{\partial x'}{\partial y}dy
$$

Adding the changes coming from the two directions gives

$$
dx'
=
\frac{\partial x'}{\partial x}dx
+
\frac{\partial x'}{\partial y}dy
$$

This is the idea of a total differential.

> Break a small change in the new coordinate into the small changes coming from each old coordinate direction, and add them all together.

The same idea applies when we combine time and three-dimensional space.

When the old coordinates change by $dx^\nu$, the change in the new coordinates can be written as

$$
dx'^\mu
=
\frac{\partial x'^\mu}{\partial x^\nu}dx^\nu
$$

Since $\nu$ appears once above and once below on the right-hand side, we sum over $\nu=0,1,2,3$.

Written out, this is

$$
\begin{aligned}
dx'^\mu
={}&
\frac{\partial x'^\mu}{\partial x^0}dx^0
+
\frac{\partial x'^\mu}{\partial x^1}dx^1 \\
&+
\frac{\partial x'^\mu}{\partial x^2}dx^2
+
\frac{\partial x'^\mu}{\partial x^3}dx^3
\end{aligned}
$$

The partial derivative

$$
\frac{\partial x'^\mu}{\partial x^\nu}
$$

tells us how much the new coordinate $x'^\mu$ changes when the old coordinate $x^\nu$ is changed a little.

The matrix made by arranging these quantities is called the Jacobian matrix.

Rather than focusing on its name, it is enough to think of it as

> a table of factors that carries small changes in the old coordinates into small changes in the new coordinates.

## An Example of Doubling a Coordinate

Consider two-dimensional spacetime with one time coordinate and one space coordinate.

Let the old coordinates be $(w,x)$ and the new coordinates be $(w',x')$.

Define the coordinate transformation by

$$
w'=w
$$

$$
x'=2x
$$

This transformation leaves the time coordinate unchanged and doubles only the number used for the space coordinate.

The small coordinate differences become

$$
dw'=dw
$$

$$
dx'=2dx
$$

In terms of the Jacobian matrix,

$$
\begin{pmatrix}
dw' \\
dx'
\end{pmatrix}
=
\begin{pmatrix}
1 & 0 \\
0 & 2
\end{pmatrix}
\begin{pmatrix}
dw \\
dx
\end{pmatrix}
$$

In the new coordinates, the same spatial separation is represented by a number twice as large.

But this does not mean that the physical distance itself has doubled.

## The Transformation in the Reverse Direction

The coordinate transformation we just used,

$$
w'=w,\qquad x'=2x
$$

can be solved in reverse as

$$
w=w'
$$

$$
x=\frac{x'}{2}
$$

Therefore,

$$
dw=dw'
$$

$$
dx=\frac{1}{2}dx'
$$

For a general coordinate transformation, wherever an inverse transformation exists, we can also write

$$
dx^\mu
=
\frac{\partial x^\mu}{\partial x'^\rho}dx'^\rho
$$

Here, the transformation from the old coordinates to the new ones is

$$
dx'^\rho
=
\frac{\partial x'^\rho}{\partial x^\sigma}dx^\sigma
$$

Substituting this equation into the inverse transformation above,

$$
dx^\mu
=
\frac{\partial x^\mu}{\partial x'^\rho}dx'^\rho
$$

gives

$$
\begin{aligned}
dx^\mu
&=
\frac{\partial x^\mu}{\partial x'^\rho}dx'^\rho \\
&=
\frac{\partial x^\mu}{\partial x'^\rho}
\frac{\partial x'^\rho}{\partial x^\sigma}dx^\sigma
\end{aligned}
$$

This is the result of taking the small change $dx^\sigma$ in the old coordinates to the new coordinates, then returning it to the old coordinates again.

Even after the two coordinate transformations in sequence, the original small change cannot become something else. The zeroth component must return to the zeroth component, and the first component to the first component.

Therefore, the part made from the two Jacobian matrices can be written as

$$
\frac{\partial x^\mu}{\partial x'^\rho}
\frac{\partial x'^\rho}{\partial x^\sigma}
=
{\delta^\mu}_\sigma
$$

${\delta^\mu}_\sigma$ is called the Kronecker delta, and

$$
{\delta^\mu}_\sigma
=
\begin{cases}
1 & \mu=\sigma \\
0 & \mu\neq\sigma
\end{cases}
$$

In matrix terms, it corresponds to the identity matrix,

$$
\begin{pmatrix}
1&0&0&0\\
0&1&0&0\\
0&0&1&0\\
0&0&0&1
\end{pmatrix}
$$

In other words, transforming from the old coordinates to the new coordinates and returning by the inverse transformation is the same as doing no transformation at all.

## Components with an Upper Index

$dx^\mu$ transformed as

$$
dx'^\mu
=
\frac{\partial x'^\mu}{\partial x^\nu}dx^\nu
$$

In general, a vector $V^\mu$ with one upper index transforms in the same form:

$$
V'^\mu
=
\frac{\partial x'^\mu}{\partial x^\nu}V^\nu
$$

Components that follow this transformation rule are called contravariant components.

There is no need to force yourself to memorize the name “contravariant.” For now, it is enough to read this as

> Vector components with an upper index transform, like the coordinate difference $dx^\mu$, using the factor $\partial x'^\mu/\partial x^\nu$ that takes us from the old coordinates to the new ones.

For example, if

$$
x'=2x
$$

then

$$
V'^x=2V^x
$$

Because the number in the new coordinate is twice the old one, the vector component represented in that coordinate is also doubled.

## Quantities with a Lower Index

Then what is $A_\mu$, with a lower index?

First, combine it with an upper-index vector $V^\mu$ and consider the quantity

$$
A_\mu V^\mu
$$

Since we sum over the index,

$$
A_\mu V^\mu
=
A_0V^0+A_1V^1+A_2V^2+A_3V^3
$$

Suppose this combination represents one number that does not depend on the coordinates.

If the upper component $V^\mu$ doubles under a coordinate transformation, the corresponding lower component must be halved to keep the product at the same value.

For example, in one dimension, if

$$
V'^x=2V^x
$$

then if it changes as

$$
A'_x=\frac{1}{2}A_x
$$

we have

$$
A'_xV'^x
=
\left(\frac{1}{2}A_x\right)(2V^x)
=
A_xV^x
$$

Upper- and lower-index components transform in ways that cancel each other’s changes.

In general, they transform as

$$
A'_\mu
=
\frac{\partial x^\nu}{\partial x'^\mu}A_\nu
$$

Upper-index components use

$$
\frac{\partial x'^\mu}{\partial x^\nu}
$$

but lower-index components use the reverse-direction expression

$$
\frac{\partial x^\nu}{\partial x'^\mu}
$$

Anything that follows this transformation rule is called a covariant vector, or a dual vector.

---

Alice: “If the upper-index component doubles, the lower-index component is halved.”

Bob: “Yes. It changes in the opposite direction so that the result of multiplying the two does not change.”

---

![Upper- and lower-index components changing in opposite directions to keep their product constant](../../../images/general-relativity/02/upper-lower-cancellation.webp)

*When the upper-index component doubles and the lower-index component is halved, the combined quantity $A_xV^x$ does not change*

## A Concrete Example of a Lower Index

As an example of a quantity with a lower index, consider the change in a scalar $f$.

A scalar is a quantity that has the same value even when the coordinates are changed.

For example, suppose a temperature $f$ is assigned to every point in space. Changing how coordinates are assigned does not change the actual temperature at that place.

A small change in temperature can be written as

$$
df
=
\frac{\partial f}{\partial x^\mu}dx^\mu
$$

If we define

$$
\partial_\mu f
\equiv
\frac{\partial f}{\partial x^\mu}
$$

then

$$
df
=
\partial_\mu f\,dx^\mu
$$

$df$ represents the temperature difference between the same two points, so it has the same value even when the coordinates are changed.

On the other hand, $dx^\mu$ transforms as an upper-index component.

Therefore, in order to cancel that change,

$$
\partial_\mu f
$$

transforms as a lower-index component.

In fact, the chain rule gives

$$
\frac{\partial f}{\partial x'^\mu}
=
\frac{\partial x^\nu}{\partial x'^\mu}
\frac{\partial f}{\partial x^\nu}
$$

This has the same form as

$$
A'_\mu
=
\frac{\partial x^\nu}{\partial x'^\mu}A_\nu
$$

A lower index is not simply an upper index written below instead. It is a component that behaves in the reverse direction under coordinate transformations.

## Contraction Makes Indices Disappear

Combining an upper-index vector $V^\mu$ and a lower-index vector $A_\mu$ gives

$$
A_\mu V^\mu
$$

The same index $\mu$ appears once above and once below, so we sum over $\mu$. As a result, no index remains in the expression.

The operation of pairing an upper index with a lower index, summing them, and reducing the number of indices is called contraction.

Calculating the value after a coordinate transformation gives

$$
A'_\mu V'^\mu
=
\left(
\frac{\partial x^\nu}{\partial x'^\mu}A_\nu
\right)
\left(
\frac{\partial x'^\mu}{\partial x^\rho}V^\rho
\right)
$$

Putting the two Jacobian matrices together,

$$
A'_\mu V'^\mu
=
\frac{\partial x^\nu}{\partial x'^\mu}
\frac{\partial x'^\mu}{\partial x^\rho}
A_\nu V^\rho
$$

The coordinate transformation and its inverse cancel each other, so

$$
\frac{\partial x^\nu}{\partial x'^\mu}
\frac{\partial x'^\mu}{\partial x^\rho}
=
{\delta^\nu}_\rho
$$

Therefore,

$$
A'_\mu V'^\mu
=
{\delta^\nu}_\rho A_\nu V^\rho
=
A_\nu V^\nu
$$

Thus,

$$
\boxed{
A'_\mu V'^\mu
=
A_\mu V^\mu
}
$$

and the value obtained by contraction does not change before or after a coordinate transformation.

## The Metric Has Two Lower Indices

The line element is written as

$$
ds^2
=
g_{\mu\nu}dx^\mu dx^\nu
$$

$dx^\mu$ and $dx^\nu$ both transform as upper-index components.

Therefore, to cancel their two changes, the metric $g_{\mu\nu}$ has two lower indices.

The metric has one other important property.

If we expand a two-dimensional line element by components, we obtain

$$
ds^2
=
g_{11}(dx^1)^2
+g_{12}dx^1dx^2
+g_{21}dx^2dx^1
+g_{22}(dx^2)^2
$$

For ordinary multiplication of numbers,

$$
dx^1dx^2
=
dx^2dx^1
$$

so the two middle terms can be combined as

$$
g_{12}dx^1dx^2
+g_{21}dx^2dx^1
=
(g_{12}+g_{21})dx^1dx^2
$$

What the line element reveals is the sum of $g_{12}$ and $g_{21}$, not the difference between them.

So the metrics used in general relativity are treated as satisfying

$$
g_{12}=g_{21}
$$

In general index notation,

$$
\boxed{
g_{\mu\nu}=g_{\nu\mu}
}
$$

Since the component is unchanged when the indices are swapped, this is called the symmetry of the metric.

Because of this property, when the components of the metric are arranged in a matrix, the same numbers appear on opposite sides of the diagonal running from the upper left to the lower right.

Under a coordinate transformation, we can write

$$
dx^\mu
=
\frac{\partial x^\mu}{\partial x'^\rho}dx'^\rho
$$

$$
dx^\nu
=
\frac{\partial x^\nu}{\partial x'^\sigma}dx'^\sigma
$$

Substituting these into the line element gives

$$
\begin{aligned}
ds^2
&=
g_{\mu\nu}dx^\mu dx^\nu \\
&=
g_{\mu\nu}
\frac{\partial x^\mu}{\partial x'^\rho}dx'^\rho
\frac{\partial x^\nu}{\partial x'^\sigma}dx'^\sigma
\end{aligned}
$$

Gathering together the parts related to the coordinate transformation,

$$
ds^2
=
\left(
g_{\mu\nu}
\frac{\partial x^\mu}{\partial x'^\rho}
\frac{\partial x^\nu}{\partial x'^\sigma}
\right)
dx'^\rho dx'^\sigma
$$

We want to write the line element in the new coordinates as

$$
ds^2
=
g'_{\rho\sigma}dx'^\rho dx'^\sigma
$$

Comparing the two equations, we can define the metric components in the new coordinates as

$$
\boxed{
g'_{\rho\sigma}
=
g_{\mu\nu}
\frac{\partial x^\mu}{\partial x'^\rho}
\frac{\partial x^\nu}{\partial x'^\sigma}
}
$$

The metric has two lower indices, so it is multiplied by two reverse-direction Jacobian matrices.

This transformation rule allows the metric to cancel the change in the coordinate differences $dx^\mu$ and keep the line element $ds^2$ at the same value.

## The Metric When a Coordinate Is Doubled

Let us return to the two-dimensional spacetime from before.

Suppose that in the old coordinates,

$$
ds^2
=
-dw^2+dx^2
$$

We made the coordinate transformation

$$
w'=w
$$

$$
x'=2x
$$

The inverse transformation is

$$
w=w'
$$

$$
x=\frac{x'}{2}
$$

so

$$
dw=dw'
$$

$$
dx=\frac{1}{2}dx'
$$

Substituting this into the old line element gives

$$
\begin{aligned}
ds^2
&=
-dw^2+dx^2 \\
&=
-dw'^2+\left(\frac{1}{2}dx'\right)^2 \\
&=
-dw'^2+\frac{1}{4}dx'^2
\end{aligned}
$$

Therefore, the metric in the new coordinates is

$$
g'_{\mu\nu}
=
\begin{pmatrix}
-1&0\\
0&1/4
\end{pmatrix}
$$

In the old coordinates,

$$
g_{\mu\nu}
=
\begin{pmatrix}
-1&0\\
0&1
\end{pmatrix}
$$

Under the coordinate transformation, the metric component in the spatial direction changed from

$$
1
\longrightarrow
\frac{1}{4}
$$

On the other hand, the coordinate difference became twice as large:

$$
dx
\longrightarrow
dx'=2dx
$$

Calculating the spatial part in the new coordinates,

$$
\frac{1}{4}dx'^2
=
\frac{1}{4}(2dx)^2
=
dx^2
$$

The metric component becoming $1/4$ cancels the doubling of the coordinate difference.

As a result,

$$
-dw'^2+\frac{1}{4}dx'^2
=
-dw^2+dx^2
$$

and the line element keeps the same value.

---

Alice: “When we doubled the coordinate number, the metric number became $1/4$.”

Bob: “The coordinate difference is squared in the line element. To cancel $(2dx)^2$, the metric has to become $1/4$.”

Alice: “So changing the metric does not mean that spacetime itself has changed.”

Bob: “Right. This time, we only described the same flat spacetime using a different scale.”

---

## Metric Components and the Metric Itself

Before and after the coordinate transformation,

$$
g_{\mu\nu}
=
\begin{pmatrix}
-1&0\\
0&1
\end{pmatrix}
$$

changed to

$$
g'_{\mu\nu}
=
\begin{pmatrix}
-1&0\\
0&1/4
\end{pmatrix}
$$

The two matrices look different.

But they do not represent different spacetimes. They are the result of expressing the same metric in components using different coordinates.

This is like measuring the same arrow using different coordinate axes: the vector components change.

- The metric is a geometric object that can be considered before choosing coordinates.
- $g_{\mu\nu}$ is the set of components that represents that metric in a particular coordinate system.
- When the coordinates change, its component representation changes.
- Even if the components change, the geometric interval represented by the line element does not.

Therefore, we need to be careful with the statement

> The metric has changed.

For example, it may mean that a celestial body has moved closer and its gravity has changed the physical state of spacetime itself. Or it may mean only that the components of the same metric have changed because of a coordinate transformation.

We must distinguish between these two cases.

## Lowering an Index with the Metric

Combining the metric with an upper-index vector $V^\nu$ gives the quantity

$$
V_\mu
=
g_{\mu\nu}V^\nu
$$

On the right-hand side, we sum over $\nu$, leaving one $\mu$. The result is $V_\mu$, which has one lower index.

This operation is called lowering an index.

In flat two-dimensional spacetime, if

$$
g_{\mu\nu}
=
\begin{pmatrix}
-1&0\\
0&1
\end{pmatrix}
$$

then

$$
V_0
=
g_{00}V^0+g_{01}V^1
=
-V^0
$$

$$
V_1
=
g_{10}V^0+g_{11}V^1
=
V^1
$$

That is, for

$$
V^\mu
=
\begin{pmatrix}
V^0\\
V^1
\end{pmatrix}
$$

we have

$$
V_\mu
=
\begin{pmatrix}
-V^0\\
V^1
\end{pmatrix}
$$

Only the sign in the time direction has changed.

Moving an index up or down is not simply moving the position of a symbol. It is an operation that uses the metric to convert it into a different kind of component.

The reverse operation, raising an index, uses the inverse metric $g^{\mu\nu}$.

We will consider the inverse metric in the next document, where we study the metric itself in more detail.

## Looking at Tensors

So far, we have seen that upper-index components, lower-index components, and the metric each change in fixed ways under a coordinate transformation.

Looking only at the transformation equations, it may feel as though we need to remember many separate rules. But all of the rules serve one purpose.

For example, in the old coordinates, the line element can be written as

$$
ds^2
=
g_{\mu\nu}dx^\mu dx^\nu
$$

Even after changing coordinates, it can be written in exactly the same form:

$$
ds^2
=
g'_{\rho\sigma}dx'^\rho dx'^\sigma
$$

The numbers in the coordinate components change. Even so, because the components cancel one another’s changes, we can express the same line element with an equation of the same form.

In this document, we take this to be the central idea of a tensor.

> A tensor is a quantity whose components change according to fixed rules so that, even when a coordinate transformation changes the coordinate numbers, an equation expressing a physical or geometric relationship can be written in the same form as before.

---

Alice: “The different ways upper and lower indices change were not meant just to make us memorize separate rules.”

Bob: “Right. Each one was changing so that, when they are combined into an equation, we can still read it in the same form after changing coordinates.”

Alice: “So we do not have to make a different physical law for each coordinate system!”

---

![Alice and Bob finding an equation with the same form in different coordinate systems](../../../images/general-relativity/02/tensor-same-equation-form.webp)

*Even when the component numbers and the directions of the coordinates change, the way an equation expressing a physical relationship is put together remains the same*

Scalars, contravariant vectors, covariant vectors, and metrics are tensors with different numbers and positions of indices. More important than memorizing the classification names is being able to read from the positions of indices how the components transform and how they can be combined.

Also, tensor components can be arranged in a matrix, but simply arranging numbers does not make a tensor. The important point for something to be a tensor is that its components change according to fixed rules under coordinate transformations.

## Summary

The quantities and transformation rules that appeared in this document are as follows.

- Scalar $f$

  $$
  f'=f
  $$

- Contravariant vector $V^\mu$

  $$
  V'^\mu
  =
  \frac{\partial x'^\mu}{\partial x^\nu}V^\nu
  $$

- Covariant vector $A_\mu$

  $$
  A'_\mu
  =
  \frac{\partial x^\nu}{\partial x'^\mu}A_\nu
  $$

- Metric $g_{\mu\nu}$

  $$
  g'_{\rho\sigma}
  =
  g_{\mu\nu}
  \frac{\partial x^\mu}{\partial x'^\rho}
  \frac{\partial x^\nu}{\partial x'^\sigma}
  $$

More important than memorizing the forms of the transformation rules is understanding the following relationships.

- Upper- and lower-index components cancel each other’s coordinate transformations when combined.
- The metric cancels the changes in two coordinate differences, making the line element $ds^2$ a coordinate-independent value.
- Tensors allow equations that express physical or geometric relationships to be written in the same form in different coordinate systems.

## The Next Question

In the example of doubling a coordinate, the spatial component of the metric changed from $1$ to $1/4$, even though it described the same flat spacetime.

Then how can we read the rate of a clock or the length of a ruler from the numbers in the metric components?

Also, when the metric components vary from place to place, is that only an appearance caused by the choice of coordinates, or is spacetime truly curved?

In the next document, we will read the metric as a “ruler for spacetime” and use Cartesian and polar coordinates to consider these questions.
