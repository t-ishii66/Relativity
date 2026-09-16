# Carrying Vectors and Going Straight

## Introduction

In the previous document, “Deriving the Christoffel Symbols from the Metric,” we derived

$$
\Gamma^\rho_{\mu\nu}
=\frac12g^{\rho\sigma}
\left(
\partial_\mu g_{\sigma\nu}
+\partial_\nu g_{\sigma\mu}
-\partial_\sigma g_{\mu\nu}
\right)
$$

If we know the metric, we can find the Christoffel symbols, which describe changes in the basis.

The covariant derivative was

$$
\nabla_\mu V^\rho
=\partial_\mu V^\rho
+\Gamma^\rho_{\mu\nu}V^\nu
$$

In this document, we will first check that the covariant derivative transforms as a tensor. Then, in order, we will consider covariant differentiation along a path, parallel transport of vectors, the geodesic equation, straight lines in polar coordinates, and free fall and geodesics.

Our goal is to gain an intuitive sense that

> A geodesic is a path whose tangent vector is parallel transported along itself.

## Why Is the Covariant Derivative a Tensor?

In the document before last, we said that the Christoffel symbols themselves are not tensors, but that the combination

$$
\nabla_\mu V^\rho =
\partial_\mu V^\rho
+
\Gamma^\rho_{\mu\nu}V^\nu
$$

transforms as a tensor.

How can combining quantities that are not tensors produce a tensor? Here, we will check that the extra terms that appear in each quantity under a coordinate transformation cancel each other out.

### Expressing a Vector in New Coordinates

Let the old coordinates be $x^\mu$, and the new coordinates be $x'^\mu$.

The components of a vector with an upper index transform as

$$
V'^\rho =
\frac{\partial x'^\rho}{\partial x^\sigma}
V^\sigma
$$

On the other hand, by the chain rule, the partial derivative in the new coordinates can be written as

$$
\partial'_\mu =
\frac{\partial x^\alpha}{\partial x'^\mu}
\partial_\alpha
$$

If $\partial_\mu V^\rho$ were a tensor with one lower index and one upper index, it would transform as

$$
\partial'_\mu V'^\rho =
\frac{\partial x^\alpha}{\partial x'^\mu}
\frac{\partial x'^\rho}{\partial x^\sigma}
\partial_\alpha V^\sigma
$$

Let us calculate whether this is really the case.

### Transforming a Vector’s Partial Derivative

Differentiating the transformation rule for $V'^\rho$ in the new coordinates gives

$$
\begin{aligned}
\partial'_\mu V'^\rho
&=
\frac{\partial x^\alpha}{\partial x'^\mu}
\partial_\alpha
\left(
\frac{\partial x'^\rho}{\partial x^\sigma}
V^\sigma
\right)\\
&=
\frac{\partial x^\alpha}{\partial x'^\mu}
\frac{\partial x'^\rho}{\partial x^\sigma}
\partial_\alpha V^\sigma\\
&\quad+
\frac{\partial x^\alpha}{\partial x'^\mu}
\frac{\partial^2x'^\rho}
{\partial x^\alpha\partial x^\sigma}
V^\sigma
\end{aligned}
\qquad (6.1)
$$

The first term is the transformation expected of a tensor with lower index $\mu$ and upper index $\rho$. However, the second term contains a second derivative of the coordinate transformation.

If the coordinate transformation is linear, changing only by a constant factor, this second derivative is zero. But it is not zero for a general coordinate transformation, such as one from Cartesian to polar coordinates.

Therefore, $\partial_\mu V^\rho$ alone is not a tensor.

### Writing the Extra Term Using the Inverse Transformation

We want to see that this extra second term cancels the term arising from the Christoffel symbols. For this, use the relation between a coordinate transformation and its inverse,

$$
\frac{\partial x'^\rho}{\partial x^\lambda}
\frac{\partial x^\lambda}{\partial x'^\nu} =
{\delta^\rho}_\nu
$$

The right-hand side is constant, so differentiating it with respect to $x'^\mu$ gives zero. Expanding the left-hand side using the product rule gives

$$
\begin{aligned}
0
&=
\frac{\partial}{\partial x'^\mu}
\left(
\frac{\partial x'^\rho}{\partial x^\lambda}
\frac{\partial x^\lambda}{\partial x'^\nu}
\right)\\
&=
\frac{\partial x^\alpha}{\partial x'^\mu}
\frac{\partial^2x'^\rho}
{\partial x^\alpha\partial x^\lambda}
\frac{\partial x^\lambda}{\partial x'^\nu}
+
\frac{\partial x'^\rho}{\partial x^\lambda}
\frac{\partial^2x^\lambda}
{\partial x'^\mu\partial x'^\nu}
\end{aligned}
$$

Now multiply both sides by $V'^\nu$. Use the inverse transformation of the vector,

$$
\frac{\partial x^\lambda}{\partial x'^\nu}V'^\nu =
V^\lambda
$$

Also, $\lambda$ is a summed index in each term, so to make the two terms easier to distinguish, rename only the $\lambda$ in the first term as $\sigma$. Then

$$
\frac{\partial x^\alpha}{\partial x'^\mu}
\frac{\partial^2x'^\rho}
{\partial x^\alpha\partial x^\sigma}
V^\sigma
+
\frac{\partial x'^\rho}{\partial x^\lambda}
\frac{\partial^2x^\lambda}
{\partial x'^\mu\partial x'^\nu}
V'^\nu
=0
$$

Moving the second term to the right-hand side lets us rewrite the extra term in the partial derivative as

$$
\frac{\partial x^\alpha}{\partial x'^\mu}
\frac{\partial^2x'^\rho}
{\partial x^\alpha\partial x^\sigma}
V^\sigma = -
\frac{\partial x'^\rho}{\partial x^\lambda}
\frac{\partial^2x^\lambda}
{\partial x'^\mu\partial x'^\nu}
V'^\nu
$$

Substituting this rewrite into the second term of equation (6.1), equation (6.1) becomes

$$
\begin{aligned}
\partial'_\mu V'^\rho
&=
\frac{\partial x^\alpha}{\partial x'^\mu}
\frac{\partial x'^\rho}{\partial x^\sigma}
\partial_\alpha V^\sigma\\
&\quad-
\frac{\partial x'^\rho}{\partial x^\lambda}
\frac{\partial^2x^\lambda}
{\partial x'^\mu\partial x'^\nu}
V'^\nu
\end{aligned}
\qquad (6.2)
$$

The last term prevents this from transforming as a tensor.

### How Do the Christoffel Symbols Transform?

The basis in the new coordinates can be written in terms of the basis in the old coordinates as

$$
\boldsymbol{e}'_\nu =
\frac{\partial x^\beta}{\partial x'^\nu}
\boldsymbol{e}_\beta
$$

Differentiating this equation with respect to $x'^\mu$ gives, by the product rule,

$$
\begin{aligned}
\partial'_\mu\boldsymbol{e}'_\nu
&=
\partial'_\mu
\left(
\frac{\partial x^\beta}{\partial x'^\nu}
\boldsymbol{e}_\beta
\right)\\
&=
\frac{\partial^2x^\beta}
{\partial x'^\mu\partial x'^\nu}
\boldsymbol{e}_\beta
+
\frac{\partial x^\beta}{\partial x'^\nu}
\partial'_\mu\boldsymbol{e}_\beta
\end{aligned}
$$

For the derivative of the basis in the second term, we can use the chain rule,

$$
\partial'_\mu =
\frac{\partial x^\alpha}{\partial x'^\mu}
\partial_\alpha
$$

and the definition of the Christoffel symbols,

$$
\partial_\alpha\boldsymbol{e}_\beta =
\Gamma^\lambda_{\alpha\beta}
\boldsymbol{e}_\lambda
$$

Therefore,

$$
\begin{aligned}
\partial'_\mu\boldsymbol{e}'_\nu
&=
\frac{\partial^2x^\beta}
{\partial x'^\mu\partial x'^\nu}
\boldsymbol{e}_\beta\\
&\quad+
\frac{\partial x^\alpha}{\partial x'^\mu}
\frac{\partial x^\beta}{\partial x'^\nu}
\Gamma^\lambda_{\alpha\beta}
\boldsymbol{e}_\lambda
\end{aligned}
$$

So far, the right-hand side is expressed in the basis of the old coordinates. The old basis can be written in terms of the basis in the new coordinates as

$$
\boldsymbol{e}_\lambda =
\frac{\partial x'^\rho}{\partial x^\lambda}
\boldsymbol{e}'_\rho
$$

Using the same transformation for $\boldsymbol e_\beta$ in the first term, and renaming that term’s summed index $\beta$ as $\lambda$, gives

$$
\begin{aligned}
\partial'_\mu\boldsymbol{e}'_\nu
&=
\frac{\partial x'^\rho}{\partial x^\lambda}
\frac{\partial^2x^\lambda}
{\partial x'^\mu\partial x'^\nu}
\boldsymbol{e}'_\rho\\
&\quad+
\frac{\partial x'^\rho}{\partial x^\lambda}
\frac{\partial x^\alpha}{\partial x'^\mu}
\frac{\partial x^\beta}{\partial x'^\nu}
\Gamma^\lambda_{\alpha\beta}
\boldsymbol{e}'_\rho
\end{aligned}
$$

On the other hand, defining the Christoffel symbols in the new coordinates gives

$$
\partial'_\mu\boldsymbol{e}'_\nu =
\Gamma'^\rho_{\mu\nu}
\boldsymbol{e}'_\rho
$$

Comparing the coefficients of the independent basis vectors $\boldsymbol{e}'_\rho$ gives the transformation rule for the Christoffel symbols,

$$
\begin{aligned}
\Gamma'^\rho_{\mu\nu}
&=
\frac{\partial x'^\rho}{\partial x^\lambda}
\frac{\partial x^\alpha}{\partial x'^\mu}
\frac{\partial x^\beta}{\partial x'^\nu}
\Gamma^\lambda_{\alpha\beta}\\
&\quad+
\frac{\partial x'^\rho}{\partial x^\lambda}
\frac{\partial^2x^\lambda}
{\partial x'^\mu\partial x'^\nu}
\end{aligned}
$$

If there were only the first term, the Christoffel symbols would transform like a tensor with one upper index and two lower indices. In fact, however, the second term, which contains a second derivative of the coordinate transformation, is added. Therefore, the Christoffel symbols themselves are not tensors.

Because of this second-derivative term, by choosing coordinates appropriately, we can make the second term exactly cancel the first at a particular point. Thus, all the Christoffel symbols can be made zero at that point. However, this does not mean they can be made zero throughout a neighborhood of that point. This distinction will be important later when we consider the Riemann curvature tensor.

This second term may look unnecessary, but it is needed to construct the covariant derivative.

Multiplying by $V'^\nu$ and using

$$
\frac{\partial x^\beta}{\partial x'^\nu}V'^\nu =
V^\beta
$$

gives

$$
\begin{aligned}
\Gamma'^\rho_{\mu\nu}V'^\nu
&=
\frac{\partial x'^\rho}{\partial x^\lambda}
\frac{\partial x^\alpha}{\partial x'^\mu}
\Gamma^\lambda_{\alpha\beta}V^\beta\\
&\quad+
\frac{\partial x'^\rho}{\partial x^\lambda}
\frac{\partial^2x^\lambda}
{\partial x'^\mu\partial x'^\nu}
V'^\nu
\end{aligned}
$$

The last term has the same form as the second term of equation (6.2), but the opposite sign.

### The Two Extra Terms Cancel Each Other Out

The covariant derivative is

$$
\nabla'_\mu V'^\rho =
\partial'_\mu V'^\rho
+
\Gamma'^\rho_{\mu\nu}V'^\nu
$$

Substituting the two transformation results into this, the terms containing second derivatives of the coordinate transformation cancel each other out, giving

$$
\begin{aligned}
\nabla'_\mu V'^\rho
&=
\frac{\partial x^\alpha}{\partial x'^\mu}
\frac{\partial x'^\rho}{\partial x^\sigma}
\left(
\partial_\alpha V^\sigma
+
\Gamma^\sigma_{\alpha\beta}V^\beta
\right)\\
&=
\frac{\partial x^\alpha}{\partial x'^\mu}
\frac{\partial x'^\rho}{\partial x^\sigma}
\nabla_\alpha V^\sigma
\end{aligned}
$$

Readers who want to check the intermediate algebra line by line should try actually substituting the two equations obtained just before this. The terms containing second derivatives cancel because their signs differ. Then factor out the common coordinate-transformation coefficients from the remaining terms to reproduce the equation above yourself.

This is precisely the tensor transformation rule: multiply the lower index $\mu$ by the inverse coordinate transformation, and the upper index $\rho$ by the forward coordinate transformation.

Therefore,

$$
\boxed{
\nabla_\mu V^\rho
\text{ is a tensor}
}
$$

We should make an exact distinction here. The connection $\nabla$ itself, and the Christoffel symbols that are its components, are not tensors. Rather, $\nabla_\mu V^\rho$, obtained by applying the covariant derivative to a vector field $V$, is a tensor.

The fact that the Christoffel symbols are not tensors is not a drawback. A term in their non-tensorial transformation cancels the extra term in the ordinary partial derivative. Combining the two lets us describe the change of a vector independently of the choice of coordinates.

This is important for the parallel transport that we will now define. Because the covariant derivative transforms as a tensor, the condition “the covariant derivative is zero” also has a geometric meaning independent of the choice of coordinates.

## Choosing a Path

To compare vectors at different places, we need to carry one vector to the location of the other.

But the starting point and destination alone do not determine where we carry it through. So first, specify a path as

$$
x^\mu=x^\mu(\lambda)
$$

$\lambda$ is a variable that indicates a location along the path.

The tangent vector of the path is

$$
U^\mu=\frac{dx^\mu}{d\lambda}
$$

$U^\mu$ tells us how much, and in which direction, each coordinate changes when $\lambda$ is increased a little.

## Differentiating Along a Path

Suppose there is a vector field $V^\rho(x)$. Along the path,

$$
V^\rho=V^\rho(x(\lambda))
$$

Using the chain rule,

$$
\frac{dV^\rho}{d\lambda}
=\frac{dx^\mu}{d\lambda}\partial_\mu V^\rho
$$

This differentiates only the components along the path; it does not include changes in the basis.

So, replace the ordinary partial derivative with the covariant derivative and define

$$
\boxed{
\frac{D V^\rho}{D\lambda}
=\frac{dx^\mu}{d\lambda}\nabla_\mu V^\rho
}
$$

$D/D\lambda$ denotes the covariant derivative along a path.

It is the sum of the covariant derivatives $\nabla_\mu$ in each coordinate direction, weighted by the way the path advances in that direction, $dx^\mu/d\lambda$. The summed index is $\mu$, which denotes a coordinate direction; we are not summing over $\rho$, the index specifying the component of the vector being differentiated.

$dx^\mu/d\lambda$ is a vector with an upper index, and $\nabla_\mu V^\rho$ is a tensor. Contracting the lower $\mu$ and upper $\mu$ indices, $DV^\rho/D\lambda$ transforms as a vector with one upper index $\rho$.

Expanding it gives

$$
\begin{aligned}
\frac{D V^\rho}{D\lambda}
&=\frac{dx^\mu}{d\lambda}
\left(
\partial_\mu V^\rho
+\Gamma^\rho_{\mu\nu}V^\nu
\right)\\
&=\frac{dV^\rho}{d\lambda}
+\Gamma^\rho_{\mu\nu}
\frac{dx^\mu}{d\lambda}V^\nu
\end{aligned}
$$

## Parallel Transport

First, consider an arrow drawn on a flat sheet of paper. Slide the arrow to another place without rotating it or stretching or shrinking it. This is parallel transport on a plane.

The arrow’s location changes, but the direction and length of the arrow itself do not. “Moving” and “the arrow itself changing” are different things.

![Alice and Bob excitedly notice that an arrow can be slid across a garden table while keeping its direction and length even though its location changes](../../../images/general-relativity/06/parallel-transport-in-garden.png)

How can we express “the arrow itself has not changed” using components?

If the basis is the same everywhere, as in Cartesian coordinates, we can simply keep each component constant. But in polar coordinates, the direction and length of the basis change at the destination. To continue representing the same arrow, we must change the numerical components to match the change in the basis.

In Chapter 4, “[How Do We Compare Vectors at Different Locations?](./04-CovariantDerivative.md#expressing-changes-in-the-basis-with-components),” we checked that combining changes in components and changes in the basis gives the change in the entire vector. In other words, on a plane, we derived

$$
\partial_\mu\boldsymbol V =
(\nabla_\mu V^\rho)\boldsymbol e_\rho
$$

From this equation, let us derive the formula for differentiation along a path step by step.

First, multiply both sides by $dx^\mu/d\lambda$ and sum over $\mu$, which denotes coordinate directions.

$$
\frac{dx^\mu}{d\lambda}\partial_\mu\boldsymbol V =
\frac{dx^\mu}{d\lambda}
(\nabla_\mu V^\rho)\boldsymbol e_\rho
$$

On the left-hand side, regard the vector on the path as $\boldsymbol V(x(\lambda))$ and use the usual chain rule for derivatives.

$$
\frac{d\boldsymbol V}{d\lambda} =
\frac{dx^\mu}{d\lambda}\partial_\mu\boldsymbol V
$$

Therefore,

$$
\frac{d\boldsymbol V}{d\lambda} =
\frac{dx^\mu}{d\lambda}
(\nabla_\mu V^\rho)\boldsymbol e_\rho
$$

Next, expand and substitute the covariant derivative on the right-hand side as

$$
\nabla_\mu V^\rho
=\partial_\mu V^\rho+\Gamma^\rho_{\mu\nu}V^\nu
$$

$$
\begin{aligned}
\frac{d\boldsymbol V}{d\lambda}
&=
\frac{dx^\mu}{d\lambda}
\left(
\partial_\mu V^\rho+\Gamma^\rho_{\mu\nu}V^\nu
\right)\boldsymbol e_\rho\\
&=
\left(
\frac{dx^\mu}{d\lambda}\partial_\mu V^\rho
+\Gamma^\rho_{\mu\nu}\frac{dx^\mu}{d\lambda}V^\nu
\right)\boldsymbol e_\rho
\end{aligned}
$$

The chain rule can also be used for the first term in parentheses, for each component $V^\rho(x(\lambda))$.

$$
\frac{dx^\mu}{d\lambda}\partial_\mu V^\rho
=\frac{dV^\rho}{d\lambda}
$$

Here the sum is over $\mu$, and this equation holds for each component $\rho$. Substituting this gives

$$
\frac{d\boldsymbol V}{d\lambda} =
\left(
\frac{dV^\rho}{d\lambda}
+\Gamma^\rho_{\mu\nu}
\frac{dx^\mu}{d\lambda}V^\nu
\right)\boldsymbol e_\rho
$$

On the other hand, expanding the definition of the covariant derivative along a path gives

$$
\begin{aligned}
\frac{DV^\rho}{D\lambda}
&=\frac{dx^\mu}{d\lambda}\nabla_\mu V^\rho\\
&=\frac{dx^\mu}{d\lambda}
\left(\partial_\mu V^\rho+\Gamma^\rho_{\mu\nu}V^\nu\right)\\
&=\frac{dV^\rho}{d\lambda}
+\Gamma^\rho_{\mu\nu}\frac{dx^\mu}{d\lambda}V^\nu
\end{aligned}
$$

This matches the expression in parentheses above. Therefore,

$$
\boxed{
\frac{d\boldsymbol V}{d\lambda}
=\frac{DV^\rho}{D\lambda}\boldsymbol e_\rho
}
$$

On the right-hand side, we multiply the covariant derivative of each component $\rho$ by the basis $\boldsymbol e_\rho$ and sum over $\rho$, thereby assembling the change in the whole vector.

In other words, the covariant derivative along a path describes change measured not only from the component numbers, but also from changes in the basis.

If we carry the arrow without rotating it or stretching or shrinking it, the left-hand side is zero. The bases are independent of one another, so the coefficient of each basis must also be zero. Therefore, parallel transport on a plane can be expressed by the condition

$$
\boxed{
\frac{D V^\rho}{D\lambda}=0
}
$$

In curved space, arrows at separated locations cannot be directly placed on top of each other and compared as they can on paper. So we use the comparison rule determined by the connection and adopt this condition as the definition of parallel transport.

That is, as we advance little by little along a path, we carry the vector so that its change measured by this rule is zero at every step. Once we choose one arrow at the starting point, this condition determines the arrows ahead one after another.

Writing this condition in components gives

$$
\boxed{
\frac{dV^\rho}{d\lambda}
+\Gamma^\rho_{\mu\nu}
\frac{dx^\mu}{d\lambda}V^\nu
=0
}
$$

This equation can also be written as

$$
\frac{dV^\rho}{d\lambda}
=-\Gamma^\rho_{\mu\nu}
\frac{dx^\mu}{d\lambda}V^\nu
$$

The right-hand side tells us how to change the components to cancel the change in the basis along the path.

---

Alice: “If we are transporting it parallelly, can’t we just keep its components constant?”

Bob: “That works in coordinates whose basis does not change. But in coordinates with a changing basis, we need to change the components to keep the same arrow.”

---

What remains constant in parallel transport is not the numerical coordinate components, but the whole vector as compared using the connection.

## Parallel Transport Preserves Inner Products

The metric compatibility introduced in Chapter 5 corresponds to inner products being preserved under parallel transport. Let us check why with equations.

Parallel transport two vectors $A^\mu,B^\nu$ along the same path $x^\alpha(\lambda)$. The conditions are

$$
\frac{DA^\mu}{D\lambda}=0,
\qquad
\frac{DB^\nu}{D\lambda}=0
$$

For example, expanding the first condition gives

$$
\frac{dA^\mu}{d\lambda}
+\Gamma^\mu_{\alpha\rho}
\frac{dx^\alpha}{d\lambda}A^\rho
=0
$$

This is the condition that the change in the components and the correction from the connection cancel each other out.

The inner product of the two vectors is

$$
I=g_{\mu\nu}A^\mu B^\nu=A_\nu B^\nu
$$

Let us calculate, step by step, how this inner product changes along the path.

First, use the chain rule for ordinary derivatives. Also, because $I$ is a scalar, we can write $\partial_\alpha I=\nabla_\alpha I$. Therefore,

$$
\frac{dI}{d\lambda}
=\frac{dx^\alpha}{d\lambda}\partial_\alpha I
=\frac{dx^\alpha}{d\lambda}\nabla_\alpha I
$$

Next, substitute $I=g_{\mu\nu}A^\mu B^\nu$ and use the product rule for covariant derivatives on the three factors.

$$
\begin{aligned}
\nabla_\alpha I
&=\nabla_\alpha(g_{\mu\nu}A^\mu B^\nu)\\
&=(\nabla_\alpha g_{\mu\nu})A^\mu B^\nu\\
&\quad+g_{\mu\nu}(\nabla_\alpha A^\mu)B^\nu\\
&\quad+g_{\mu\nu}A^\mu(\nabla_\alpha B^\nu).
\end{aligned}
$$

It separates into three terms: one differentiating the metric, one differentiating $A^\mu$, and one differentiating $B^\nu$. Multiplying this equation by $dx^\alpha/d\lambda$ gives

$$
\begin{aligned}
\frac{dI}{d\lambda}
={}&\frac{dx^\alpha}{d\lambda}
(\nabla_\alpha g_{\mu\nu})A^\mu B^\nu\\
&+g_{\mu\nu}
\left(\frac{dx^\alpha}{d\lambda}\nabla_\alpha A^\mu\right)B^\nu\\
&+g_{\mu\nu}A^\mu
\left(\frac{dx^\alpha}{d\lambda}\nabla_\alpha B^\nu\right)
\end{aligned}
$$

The expressions in parentheses in the second and third terms are precisely the definitions of covariant derivatives along a path.

$$
\frac{dx^\alpha}{d\lambda}\nabla_\alpha A^\mu
=\frac{DA^\mu}{D\lambda},
\qquad
\frac{dx^\alpha}{d\lambda}\nabla_\alpha B^\nu
=\frac{DB^\nu}{D\lambda}
$$

Rewriting them gives

$$
\begin{aligned}
\frac{dI}{d\lambda}
={}&
\frac{dx^\alpha}{d\lambda}
(\nabla_\alpha g_{\mu\nu})A^\mu B^\nu\\
&+g_{\mu\nu}\frac{DA^\mu}{D\lambda}B^\nu\\
&+g_{\mu\nu}A^\mu\frac{DB^\nu}{D\lambda}.
\end{aligned}
$$

The first term is zero by metric compatibility, $\nabla_\alpha g_{\mu\nu}=0$. The second and third terms are zero by the conditions that the two vectors are parallel transported. Therefore,

$$
\boxed{\frac{dI}{d\lambda}=0}
$$

and the inner product stays constant along the path.

In other words, metric compatibility alone does not make the inner product of arbitrary vector fields constant. The inner product is preserved when two vectors are parallel transported along the same path using a metric-compatible connection.

## What Happens in Cartesian Coordinates?

When an ordinary plane is described in Cartesian coordinates, all Christoffel symbols are zero.

Therefore, the parallel-transport equation becomes

$$
\frac{dV^\rho}{d\lambda}=0
$$

In this case, keeping the components of a vector constant is itself parallel transport.

In polar coordinates, the Christoffel symbols are not zero, so the components change during parallel transport even on the same plane.

The geometric meaning of parallel transport does not depend on coordinates, but the component equation expressing its condition looks different in different coordinates.

## Carrying the Direction of the Path Itself

Let the tangent vector of the path be

$$
U^\rho=\frac{dx^\rho}{d\lambda}
$$

This time, instead of a separately prepared vector, parallel transport this tangent vector itself along the path.

The condition is

$$
\boxed{
\frac{D U^\rho}{D\lambda}=0
}
$$

Substituting $U^\rho=dx^\rho/d\lambda$ gives

$$
\frac{dU^\rho}{d\lambda}
=\frac{d^2x^\rho}{d\lambda^2}
$$

so

<a id="eq-geodesic-equation"></a>

$$
\boxed{
\frac{d^2x^\rho}{d\lambda^2}
+\Gamma^\rho_{\mu\nu}
\frac{dx^\mu}{d\lambda}
\frac{dx^\nu}{d\lambda}
=0
}
\qquad (6.3)
$$

This is called the geodesic equation.

In fact, this equation is also **the equation of motion for an object in free fall under gravity**. In general relativity, a small object that feels no force other than gravity moves through spacetime as “straight as possible”—that is, along a geodesic.

The Christoffel symbols are calculated from the metric. Therefore, if gravity changes the spacetime metric, its effect appears in an object’s coordinate motion through the Christoffel symbols in the geodesic equation. If we solve this equation for the coordinates including time, giving an initial point and initial velocity, we can find the object’s later motion.

However, Christoffel symbols also include effects caused by the choice of coordinates. Indeed, they are nonzero when polar coordinates are used even on a flat plane, and they can be made zero at a point by choosing coordinates even in curved spacetime. Therefore, the fact that Christoffel symbols are nonzero alone does not show that spacetime is curved.

The curvature of spacetime that remains when we examine not only one point but also its neighborhood, and that cannot be removed by a coordinate transformation, appears in curvature constructed from the Christoffel symbols. We will examine this in Chapter 7.

First, let us check that on a flat plane this equation represents the usual straight line.

## Why Is It “Straight”?

In Cartesian coordinates on a plane, $\Gamma^\rho_{\mu\nu}=0$, so

$$
\frac{d^2x^\rho}{d\lambda^2}=0
$$

Integrating once gives

$$
\frac{dx^\rho}{d\lambda}=\text{constant}
$$

and integrating again gives

$$
x^\rho(\lambda)=a^\rho\lambda+b^\rho
$$

This is a straight line on a plane.

In general coordinates or curved spacetime, we cannot call a path “straight” simply because its coordinate components are constant.

So we use

> Parallel transporting the tangent vector along itself

as the coordinate-independent definition of “as straight as possible.”

## About the Parameter

To write the geodesic equation as $D U^\rho/D\lambda=0$, we use a parameter that does not unnaturally stretch or shrink the rate at which the path is traversed.

Such a $\lambda$ is called an affine parameter.

For a timelike geodesic, proper time $\tau$ can be chosen as an affine parameter.

In this document, let $\lambda$ in the geodesic equation be an affine parameter.

## The Geodesic Equation in Polar Coordinates

In polar coordinates on a plane,

$$
\Gamma^r_{\theta\theta}=-r,
\qquad
\Gamma^\theta_{r\theta}
=\Gamma^\theta_{\theta r}
=\frac1r
$$

For the $r$ component, the only nonzero $\Gamma^r_{\mu\nu}$ is $\Gamma^r_{\theta\theta}$, so

$$
\boxed{
\frac{d^2r}{d\lambda^2}
-r\left(\frac{d\theta}{d\lambda}\right)^2
=0
}
$$

For the $\theta$ component,

$$
\frac{d^2\theta}{d\lambda^2}
+\Gamma^\theta_{r\theta}
\frac{dr}{d\lambda}\frac{d\theta}{d\lambda}
+\Gamma^\theta_{\theta r}
\frac{d\theta}{d\lambda}\frac{dr}{d\lambda}
=0
$$

so

$$
\boxed{
\frac{d^2\theta}{d\lambda^2}
+\frac{2}{r}
\frac{dr}{d\lambda}
\frac{d\theta}{d\lambda}
=0
}
$$

Even for a straight line on the same plane, $r$ and $\theta$ do not necessarily change at constant rates in polar coordinates. The terms containing Christoffel symbols account for changes in the coordinate basis.

![Alice and Bob discover, while looking at a straight line crossing the polar-coordinate markings drawn on a table by the sea, that the path remains straight](../../../images/general-relativity/06/straight-path-in-polar-coordinates.png)

## A Radial Straight Line

Keep the angle constant, with $\theta=\text{constant}$. Then

$$
\frac{d\theta}{d\lambda}=0,
\qquad
\frac{d^2\theta}{d\lambda^2}=0
$$

The two geodesic equations become

$$
\frac{d^2r}{d\lambda^2}=0,
\qquad
0=0
$$

Therefore, a radial straight line in which $r$ changes proportionally to $\lambda$ is a geodesic.

## A Circle Is Not a Geodesic

Next, consider a path moving around a circle with $r=\text{constant}$. Then

$$
\frac{dr}{d\lambda}=0,
\qquad
\frac{d^2r}{d\lambda^2}=0
$$

The $r$ component of the geodesic equation becomes

$$
-r\left(\frac{d\theta}{d\lambda}\right)^2=0
$$

If $r>0$ and the path actually moves around the circle, then $d\theta/d\lambda\neq0$, so the left-hand side is not zero.

Therefore, a circle is not a geodesic on a plane. To keep moving along a circle, the direction of motion must keep being bent toward the center.

## Coordinate Appearance Does Not Decide It

Whether a path is a geodesic is not decided by whether it looks straight in coordinates. It is decided by whether it satisfies the geodesic equation.

If the same path is expressed in different coordinates, its shape in coordinates changes. Even so, its geometric property of being a geodesic does not change.

## Free Fall and Geodesics

In general relativity, an object experiencing no force other than gravity follows a geodesic in spacetime.

Let the object’s proper time be $\tau$. As in Chapter 3, $\tau$ is ordinary proper time multiplied by $c$, so it has units of distance. The four-velocity is

$$
U^\mu=\frac{dx^\mu}{d\tau}
$$

For a general vector $V^\mu$ and path parameter $\lambda$, the covariant derivative along a path was

$$
\frac{D V^\mu}{D\lambda} =
\frac{dx^\nu}{d\lambda}
\nabla_\nu V^\mu
$$

Here, let the path parameter be proper time $\tau$, and choose the four-velocity $U^\mu$ itself as the vector $V^\mu$ carried along the path. Then

$$
\frac{D U^\mu}{D\tau} =
\frac{dx^\nu}{d\tau}
\nabla_\nu U^\mu =
U^\nu\nabla_\nu U^\mu
$$

Thus, the condition for parallel transporting the four-velocity along the path, $DU^\mu/D\tau=0$, is

$$
U^\nu\nabla_\nu U^\mu=0
$$

In components,

$$
\boxed{
\frac{d^2x^\mu}{d\tau^2}
+\Gamma^\mu_{\rho\sigma}
\frac{dx^\rho}{d\tau}
\frac{dx^\sigma}{d\tau}
=0
}
$$

From coordinates on the ground, the spatial coordinates of an object in free fall appear to accelerate.

![Alice and Bob eagerly observe a ball falling in an orchard and notice that the spacing between its falling positions grows over time](../../../images/general-relativity/06/free-fall-in-orchard.png)

But in general relativity, rather than thinking that a force called gravity acts on an object and bends its path, we think of the object as moving as straight as possible through spacetime.

The acceleration in coordinates contains Christoffel symbols constructed from the spacetime metric.

## From Four-Velocity to Four-Momentum

Let us also describe the motion of a freely falling object in terms of energy and momentum. Here, consider a small particle with mass $m$.

The four-velocity defined above is

$$
U^\mu=\frac{dx^\mu}{d\tau}
$$

Proper time $\tau$ does not depend on the choice of coordinates, so under a coordinate transformation,

$$
U'^\alpha
=\frac{dx'^\alpha}{d\tau}
=\frac{\partial x'^\alpha}{\partial x^\mu}U^\mu
$$

This is the transformation rule for a vector with one upper index.

Multiply this four-velocity by $mc$, the product of the scalar mass and the speed of light, and define

$$
\boxed{p^\mu=mcU^\mu}
$$

This $p^\mu$ is called the **four-momentum**. Multiplying by a scalar does not change the transformation rule, so four-momentum is also a four-vector.

Here, a four-vector is not a different kind of quantity from a tensor. **A four-vector is a rank-1 tensor with four spacetime components.** The 4 in “four” refers to the number of components, and the 1 in “rank 1” refers to the number of indices.

### What Do the Four Components Represent?

Let us observe a particle in local inertial coordinates matched to an observer’s clocks and rulers. Let the time coordinate be $x^0=w$. Since coordinate time measured in seconds is $t=w/c$, the particle’s three-dimensional velocity is $v^i=dx^i/dt=c\,dx^i/dw$. In these coordinates, just as in special relativity,

$$
\frac{dw}{d\tau}=\gamma,
\qquad
\gamma=\frac{1}{\sqrt{1-|\boldsymbol v|^2/c^2}}
$$

so the components of four-velocity are

$$
U^0=\frac{dw}{d\tau}=\gamma,
\qquad
U^i=\frac{dx^i}{dw}\frac{dw}{d\tau}=\gamma\frac{v^i}{c}
$$

In these local inertial coordinates, every component of the four-velocity is dimensionless. Multiplying by $mc$, the four-momentum is

$$
p^\mu=(\gamma mc,\gamma mv^1,\gamma mv^2,\gamma mv^3)
$$

The three spatial components $p^i=\gamma mv^i$ are momentum in special relativity. If the speed is much smaller than the speed of light, $\gamma\simeq1$, so they return to $mv^i$ from Newtonian mechanics.

The time component corresponds to energy. The particle’s total energy measured by this observer is $E=\gamma mc^2$, so

$$
p^0=\frac{E}{c}
$$

Here, $E$ includes rest energy as well as kinetic energy. If the particle is at rest relative to the observer, then $\gamma=1$ and $E=mc^2$.

Thus,

$$
\boxed{p^\mu=(E/c,p^1,p^2,p^3)}
$$

Dividing energy by $c$ gives all four components the same units as momentum.

---

Alice: “I thought energy and momentum were separate quantities, but they make up one vector.”

Bob: “If the observer’s motion changes, both the measured energy and momentum change. We can handle those changes together as transformations of four components.”

---

> **Tip: Components of Four-Momentum and Measured Values**
>
> Four-momentum $p^\mu$ is a rank-1 tensor, and both its time and spatial components follow the transformation rule of the same tensor. For every component, we need to consider the correspondence between a coordinate component and the value an observer actually measures.
>
> In local inertial coordinates matched to an observer’s clocks and rulers, we can read the four components as “the energy measured by that observer divided by $c$“ and ”the momentum in the three directions measured by that observer.“ The notation $(E/c,p^1,p^2,p^3)$ uses this correspondence. Although only the time component is written as $E/c$, the spatial components also correspond to measured momentum; it is not only the time component that relates to measured values.
>
> If we transform to local inertial coordinates matched to another observer, the four transformed components correspond to the energy and momentum measured by that new observer.
>
> Coordinates express numerically “when and where something happened,” and we use them to handle events at separated locations on one diagram. In this sense, a coordinate system is like a “canvas” for drawing events. However, its markings do not necessarily match values measured directly by real clocks and rulers.
>
> In general coordinates, neither the time axis nor the spatial axes are necessarily matched to an observer’s clocks, rulers, and motion. Therefore, in general we cannot read $p^0$ directly as measured $E/c$, nor $p^1,p^2,p^3$ directly as measured momentum in three directions. This is a problem of the correspondence between coordinate components and measured values that is common to all four components.
>
> On the other hand, $p^\mu=mcU^\mu=mc\,dx^\mu/d\tau$ holds in general coordinates as well. This is because “which coordinates express position” and “what we use to differentiate” are separate matters. Even if coordinates change, the proper time $\tau$ ticked by the particle’s own clock is used for differentiation. What changes are the coordinates $x^\mu$ being differentiated, and the components of four-velocity and four-momentum undergo the same transformation. Therefore, their relation $p^\mu=mcU^\mu$ is preserved.

### In Free Fall, Four-Momentum Is Also Parallel Transported

If the mass $m$ is constant,

$$
\frac{Dp^\mu}{D\tau}
=mc\frac{DU^\mu}{D\tau}
$$

In free fall, $DU^\mu/D\tau=0$, so

$$
\boxed{\frac{Dp^\mu}{D\tau}=0}
$$

That is, the four-momentum of a freely falling particle is parallel transported along its geodesic.

This does not mean that the numerical values of all four components remain constant in every coordinate system. The covariant derivative contains a connection term that accounts for changes in the basis from place to place.

In Chapter 8, we will move from the energy and momentum of a single particle to the density and flux of a collection of particles. This four-momentum will be the starting point.

## Even with Christoffel Symbols, a Plane Is Still a Plane

When a plane is expressed in polar coordinates, the Christoffel symbols are not zero. When the same plane is expressed in Cartesian coordinates, they are all zero.

Therefore,

> The fact that Christoffel symbols are nonzero does not necessarily mean that space or spacetime itself is curved.

Christoffel symbols are components of the connection and change with coordinates.

Curvature is the bending of space or spacetime itself that cannot be removed by a choice of coordinates. In the next chapter, we will consider how to investigate it.

## Summary

- An ordinary partial derivative of vector components is not, by itself, a tensor because an extra term containing second derivatives of the coordinate transformation appears.
- Christoffel symbols are also not tensors, and their transformation rule contains an extra term with second derivatives of the coordinate transformation.
- The two extra terms cancel in the covariant derivative, so $\nabla_\mu V^\rho$ transforms as a tensor.
- It is not the connection $\nabla$ itself but $\nabla_\mu V^\rho$, obtained by applying it to a vector field, that is a tensor.
- A path can be written as $x^\mu=x^\mu(\lambda)$.
- The tangent vector of a path is $U^\mu=dx^\mu/d\lambda$.
- The covariant derivative along a path, $DV^\rho/D\lambda$, is a vector obtained by contracting $U^\mu$ with $\nabla_\mu V^\rho$.
- The covariant derivative along a path is

  $$\frac{D V^\rho}{D\lambda} = \frac{dx^\mu}{d\lambda}\nabla_\mu V^\rho$$
- Carrying a vector so that its covariant derivative along a path is zero is called parallel transport.
- In parallel transport, a vector’s coordinate components do not necessarily remain constant.
- A path whose tangent vector is parallel transported along itself is a geodesic.
- The geodesic equation is

  $$\frac{d^2x^\rho}{d\lambda^2} + \Gamma^\rho_{\mu\nu} \frac{dx^\mu}{d\lambda} \frac{dx^\nu}{d\lambda} =0$$
- Even in polar coordinates, a straight line on a plane is a geodesic, while a circle is not.
- An object receiving no force other than gravity follows a geodesic in spacetime.
- Nonzero Christoffel symbols alone do not mean that curvature is present.

## The Next Question

We have learned how to parallel transport a vector along a specified path.

Then, if we carry a vector from the same starting point to the same destination along two different paths, will the result be the same?

Or, if we carry a vector around a small closed curve and return it to the starting point, will it return to its original vector?

On a plane, it returns to the original vector. But in general space or spacetime, the result can differ depending on the path.

In the next document, “[Real Curvature Revealed by Going Around Once](./07-CurvatureFromParallelTransport.md),” we will move from parallel transport along a closed curve and the difference caused by the order of covariant differentiation to curvature that cannot be removed by coordinates.
