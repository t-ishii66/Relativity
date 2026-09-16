# Free Fall and the Event Horizon

## Introduction

In the previous document [“Gravitational Redshift and the Propagation of Light”](./12-GravitationalRedshiftAndLight.md), stationary Alice sent light that was received by stationary Charlie outside. Because neither person’s position changed, signals sent one after another arrived after the same amount of coordinate time.

This time, Bob will freely fall from the place where Alice is. Bob also carries a clock and a light emitter, and will send light to Charlie outside while falling.

How much does Bob’s clock advance? How does that light reach Charlie? Using a fall that approaches the horizon as an example, let us distinguish among the time Bob himself experiences, the motion drawn in coordinates, and the light Charlie receives.

In this chapter too, $w$ and proper time $\tau$ are quantities measured in distance units obtained by multiplying ordinary time by $c$.

## The Setting and the Roles of the Three People

First, outside, where $r>r_{\mathrm s}$, we use the same metric as before.

$$
f(r)=1-\frac{r_{\mathrm s}}r,\qquad
r_{\mathrm s}=\frac{2GM}{c^2},
$$

$$
ds^2=-f(r)dw^2+\frac{dr^2}{f(r)}+r^2d\Omega^2,
\qquad
d\Omega^2=d\theta^2+\sin^2\theta\,d\phi^2.
\tag{13.1}
$$

However, to consider a fall all the way to the horizon, from here on we use the **idealized, time-independent model of a black hole with neither rotation nor charge**. We ignore the effect of falling Bob’s mass and of the light he sends on spacetime.

The event horizon is the boundary beyond which light can no longer be delivered from inside to far away. For the black hole considered here, $r=r_{\mathrm s}$ is that boundary. In this chapter, we first examine Bob’s motion as he approaches the horizon from outside, $r>r_{\mathrm s}$, and the outward light Bob sends.

For an ordinary star whose surface lies outside $r_{\mathrm s}$, Bob reaches the star’s surface before approaching the horizon. The vacuum metric cannot simply be used where the star’s matter is present. The setting in this chapter is distinct from that case.

| Person | Role |
|---|---|
| Alice | Remains stationary at $r=r_0>r_{\mathrm s}$, supported in place |
| Bob | Begins freely falling beside Alice from zero relative velocity and moves in the radial direction |
| Charlie | Remains stationary at $r=r_{\mathrm{Charlie}}>r_0$, far enough that the effects of gravity can be ignored, and receives outward light from Bob |

Alice and Charlie have supports that keep them in place. After departure, Bob does not fire a rocket and is assumed to experience no force other than gravity.

Charlie is sufficiently far away that we can ignore $r_{\mathrm s}/r_{\mathrm{Charlie}}$. In this chapter, under this approximation, we calculate with $f(r_{\mathrm{Charlie}})=1$. Therefore,

$$
d\tau_{\mathrm{Charlie}}=dw
$$

and the advance of Charlie’s clock agrees with the advance of coordinate time. Charlie is placed at a distant but finite position, and the time until the light arrives is calculated along its path as before.

---

Alice: “Can Bob’s clock also be calculated as $d\tau=\sqrt f\,dw$, just like my clock?”

Bob: “I change position, so the spatial term remains too. First, let’s find out how I fall.”

---

## Quantities That Determine the Free-Fall Motion

![Alice seeing Bob off from the platform in a falling-experiment capsule](../../../images/general-relativity/13/alice-bob-fall-capsule.png)

*Bob undertaking a falling experiment with a clock, and Alice seeing him off. An image for thinking about free fall.*

Let Bob’s proper time be $\tau_{\mathrm{Bob}}$, and let a dot below denote differentiation with respect to it.

$$
\dot w=\frac{dw}{d\tau_{\mathrm{Bob}}},\qquad
\dot r=\frac{dr}{d\tau_{\mathrm{Bob}}}.
$$

Because the motion is only in the radial direction, $d\theta=d\phi=0$. Along Bob’s orbit, $ds^2=-d\tau_{\mathrm{Bob}}^2$, so dividing equation (13.1) by $d\tau_{\mathrm{Bob}}^2$ gives,

$$
-1=-f(r)\dot w^2+\frac{\dot r^2}{f(r)}.
\tag{13.2}
$$

Let us use one more condition for free fall. If we write again the [geodesic equation (6.3)](./06-ParallelTransportAndGeodesics.md#eq-geodesic-equation) derived in Chapter 6, it is

$$
\frac{d^2x^\rho}{d\lambda^2}
+\Gamma^\rho_{\mu\nu}
\frac{dx^\mu}{d\lambda}
\frac{dx^\nu}{d\lambda}
=0
$$

The index $\rho$ specifies which coordinate component of the motion we are examining, and for the repeated $\mu,\nu$, we sum over all coordinate directions.

This time, choose Bob’s proper time $\tau_{\mathrm{Bob}}$ as the parameter $\lambda$, and set $\rho=w$. Then, as the equation determining the change in the time coordinate $w$, we obtain

$$
\ddot w+\sum_{\mu,\nu}
\Gamma^w_{\mu\nu}\dot x^\mu\dot x^\nu=0
$$

Here $\mu,\nu$ each take the values $w,r,\theta,\phi$.

Since Bob falls only in the radial direction, $\dot\theta=\dot\phi=0$. Thus, terms containing angular velocities vanish, and the four remaining combinations are $(w,w),(w,r),(r,w),(r,r)$. Expanding the sum gives,

$$
\ddot w
+\Gamma^w_{ww}\dot w^2
+\Gamma^w_{wr}\dot w\dot r
+\Gamma^w_{rw}\dot r\dot w
+\Gamma^w_{rr}\dot r^2
=0.
$$

Furthermore, for this metric, $\Gamma^w_{ww}$ and $\Gamma^w_{rr}$ are also zero. Let us use the connection formula to check why.

The general formula for the Christoffel symbols is,

$$
\Gamma^\rho_{\mu\nu}
=\frac12g^{\rho\sigma}
\left(
\partial_\mu g_{\sigma\nu}
+\partial_\nu g_{\sigma\mu}
-\partial_\sigma g_{\mu\nu}
\right)
$$

Setting $\rho=w$ gives,

$$
\Gamma^w_{\mu\nu}
=\frac12g^{w\sigma}
\left(
\partial_\mu g_{\sigma\nu}
+\partial_\nu g_{\sigma\mu}
-\partial_\sigma g_{\mu\nu}
\right).
$$

On the right, we sum over $\sigma=w,r,\theta,\phi$. But this metric and its inverse are diagonal, so $g^{w\sigma}$ is nonzero only when $\sigma=w$. Therefore, writing the $\sigma=w$ term that remains in the sum,

$$
\Gamma^w_{\mu\nu}
=\frac12g^{ww}
\left(
\partial_\mu g_{w\nu}
+\partial_\nu g_{w\mu}
-\partial_w g_{\mu\nu}
\right).
\tag{13.3}
$$

This metric does not depend on $w$, and $g_{wr}=0$. Therefore,

$$
\begin{aligned}
\Gamma^w_{ww}
&=\frac12g^{ww}\partial_w g_{ww}=0,\\
\Gamma^w_{rr}
&=\frac12g^{ww}
\left(2\partial_r g_{wr}-\partial_w g_{rr}\right)=0.
\end{aligned}
$$

The two remaining connections are equal even when the lower indices are exchanged: $\Gamma^w_{wr}=\Gamma^w_{rw}$. Also, since $\dot w\dot r=\dot r\dot w$, adding the two terms gives,

$$
\Gamma^w_{wr}\dot w\dot r
+\Gamma^w_{rw}\dot r\dot w
=2\Gamma^w_{wr}\dot w\dot r.
$$

Thus, the $w$ component of the geodesic equation becomes,

$$
\ddot w+2\Gamma^w_{wr}\dot w\dot r=0
$$

The factor 2 arose from the two index combinations $(w,r)$ and $(r,w)$.

Finally, calculate the remaining connection $\Gamma^w_{wr}$. In connection formula (13.3), set $\mu=w,\nu=r$ and use $g_{wr}=0$. Writing $f'=df/dr$, we get,

$$
\Gamma^w_{wr}
=\frac12 g^{ww}\partial_r g_{ww}
=\frac12\left(-\frac1f\right)(-f')
=\frac{f'}{2f}.
$$

Substituting this and multiplying by $f$ gives,

$$
f\ddot w+f'\dot r\dot w=0.
$$

The left side is a product derivative, so,

$$
\frac{d}{d\tau_{\mathrm{Bob}}}(f\dot w)=0.
$$

Therefore, we obtain the quantity that does not change during the fall,

$$
\boxed{\varepsilon=f(r)\frac{dw}{d\tau_{\mathrm{Bob}}}}
\tag{13.4}
$$

$\varepsilon$ is a positive dimensionless constant determined by the initial conditions.

Substitute $\dot w=\varepsilon/f$ into equation (13.2) and multiply both sides by $f$:

$$
-f=-\varepsilon^2+\dot r^2.
$$

Thus, choosing the inward-falling branch,

$$
\boxed{\frac{dr}{d\tau_{\mathrm{Bob}}}
=-\sqrt{\varepsilon^2-f(r)}}
\tag{13.5}
$$

At the starting point $r=r_0$, $\dot r=0$, so,

$$
\varepsilon=\sqrt{f(r_0)}
=\sqrt{1-\frac{r_{\mathrm s}}{r_0}}.
$$

Therefore, Bob’s fall is described by,

$$
\frac{dr}{d\tau_{\mathrm{Bob}}}
=-\sqrt{r_{\mathrm s}\left(\frac1r-\frac1{r_0}\right)}
\tag{13.6}
$$

As he falls and $r$ becomes smaller, the absolute value of this change becomes larger.

## Motion in Coordinates and the Speed Measured Locally

Equation (13.4) divided by equation (13.5) gives Bob’s motion on the canvas:

$$
\boxed{
\frac{dr}{dw}
=-\frac{f(r)}{\varepsilon}\sqrt{\varepsilon^2-f(r)}
}
$$

As $r\to r_{\mathrm s}$, $f\to0$, so $dr/dw\to0$.

Looking only at this, Bob seems to stop moving just before the horizon. However, $dr/dw$ was the ratio of changes in numbers attached to a shared coordinate system.

Consider an observer who is stationary at the place Bob passes. This is an observer for considering measurements at each location; it does not mean that Alice, who remains at $r_0$, falls together with Bob.

From the speed-conversion formula (11.6) in Chapter 11, the radial speed of Bob measured by that observer’s own clock and ruler is,

$$
v_{\mathrm{Bob}}
=\frac{c}{f(r)}\frac{dr}{dw}
=-c\sqrt{1-\frac{f(r)}{\varepsilon^2}}.
$$

At every location outside, $|v_{\mathrm{Bob}}|<c$, but an observer stationary closer to the horizon measures Bob’s speed as closer to $c$.

The limit here is a collection of measurements by observers stationary at different locations. Comparisons with stationary observers are made outside the horizon. We have not placed an observer there waiting stationary on the horizon.

## Bob Reaches the Horizon in a Finite Proper Time

During Bob’s fall from $r_0$ to $r<r_0$, the proper time marked by his own clock is found by integrating equation (13.6):

$$
\Delta\tau_{\mathrm{Bob}}
=\int_r^{r_0}
\frac{d\rho}{\sqrt{r_{\mathrm s}(1/\rho-1/r_0)}}.
\tag{13.7}
$$

$\rho$ is the radius variable used inside the integral.

At the horizon, $\rho=r_{\mathrm s}$, the denominator is $\sqrt{1-r_{\mathrm s}/r_0}=\varepsilon>0$, and the integrand does not diverge.

On the other hand, at the starting point, $\rho=r_0$, the denominator becomes zero. Let us use equation (13.7) to check whether the integral over this part is finite.

First, putting the difference inside the square root over a common denominator,

$$
\frac1\rho-\frac1{r_0}
=\frac{r_0-\rho}{\rho r_0}.
$$

Therefore, the integrand in equation (13.7) can be rewritten as,

$$
\begin{aligned}
\frac{d\rho}{\sqrt{r_{\mathrm s}(1/\rho-1/r_0)}}
&=\frac{d\rho}
{\sqrt{r_{\mathrm s}(r_0-\rho)/(\rho r_0)}}\\
&=\sqrt{\frac{\rho r_0}{r_{\mathrm s}}}
\frac{d\rho}{\sqrt{r_0-\rho}}
\end{aligned}
$$

Near the starting point, $\rho\simeq r_0$, so the preceding factor approaches the finite value,

$$
\sqrt{\frac{\rho r_0}{r_{\mathrm s}}}
\simeq\frac{r_0}{\sqrt{r_{\mathrm s}}}
$$

Thus, apart from a constant factor, the integral near this point has the form,

$$
\int\frac{d\rho}{\sqrt{r_0-\rho}}
$$

Let us check this integral too. Let the difference in radius from the starting point to a point slightly inside be $\delta>0$, and set $s=r_0-\rho$. Since $d\rho=-ds$,

$$
\begin{aligned}
\int_{r_0-\delta}^{r_0}
\frac{d\rho}{\sqrt{r_0-\rho}}
&=\int_0^\delta\frac{ds}{\sqrt{s}}\\
&=\lim_{a\to0+}\left[2\sqrt{s}\right]_a^\delta\\
&=2\sqrt{\delta}.
\end{aligned}
$$

Even though the integrand diverges at the starting point, the integral near that point is finite. The factor attached to the original integral is also no greater than $r_0/\sqrt{r_{\mathrm s}}$ on this interval, so the contribution near the starting point in equation (13.7) is finite as well.

Therefore, the integral from the starting point to the horizon is finite, and Bob reaches the horizon in a finite time according to his own clock.

## The Same Fall Drawn in $w$ Makes the Horizon Infinitely Far Away

![Alice seeing Bob off while looking up at the long coordinate scroll and Bob looking at his clock](../../../images/general-relativity/13/alice-bob-coordinate-scroll.png)

*A canvas extending without end, and a clock advancing in hand. An image representing the difference between coordinate time and proper time.*

Meanwhile, from equations (13.4) and (13.5),

$$
\frac{dw}{dr}
=-\frac{\varepsilon}{f(r)\sqrt{\varepsilon^2-f(r)}}.
$$

Near the horizon, $\sqrt{\varepsilon^2-f}\to\varepsilon$, so,

$$
\frac{dw}{dr}\simeq-\frac1f
\simeq-\frac{r_{\mathrm s}}{r-r_{\mathrm s}}.
$$

After integration, the divergent part is,

$$
w\simeq-r_{\mathrm s}\ln\left(\frac{r-r_{\mathrm s}}{r_{\mathrm s}}\right)
+\text{finite terms}
$$

As $r\to r_{\mathrm s}+0$, $w\to+\infty$.

The orbit corresponding to Bob’s finite proper time is being drawn stretched out without limit on this $w$ scale. What we have learned so far is the coordinate description; to understand the image that reaches Charlie, we must also examine light propagation.

---

Alice: “So looking as though I am about to stop on the coordinate chart and Bob’s own clock stopping are not the same thing.”

Bob: “Right. The proper time measured by my clock is finite all the way to the horizon.”

---

## At What Intervals Does Light from Falling Bob Arrive?

![Alice and Bob checking the blinking of the light emitter before departure](../../../images/general-relativity/13/alice-bob-pulse-check.png)

*The two of them checking the blinking before departure. At what intervals will the light sent during the fall reach distant Charlie?*

When Bob is at the outside radius $r$, he sends outward light at coordinate time $w_{\mathrm{emit}}$. In the coordinate-time expression (12.4) for light propagation derived in Chapter 12, replace the emission position $r_{\mathrm{Alice}}$ with Bob’s position $r$ at emission. Adding the coordinate time required for propagation to the emission time, the coordinate time at which the light reaches fixed $r_{\mathrm{Charlie}}$ is,

$$
w_{\mathrm{receive}}
=w_{\mathrm{emit}}
+\int_r^{r_{\mathrm{Charlie}}}\frac{d\rho}{f(\rho)}.
\tag{13.8}
$$

When he sends the next light, Bob has moved farther inward. Therefore, the coordinate time needed for propagation is longer too.

Let us compare two nearby emissions and their corresponding receptions. Differentiating equation (13.8) with respect to Bob’s proper time, the lower limit $r$ of the integral also moves, giving,

$$
\frac{dw_{\mathrm{receive}}}{d\tau_{\mathrm{Bob}}}
=\frac{dw_{\mathrm{emit}}}{d\tau_{\mathrm{Bob}}}
-\frac1{f(r)}\frac{dr}{d\tau_{\mathrm{Bob}}}.
$$

The minus sign in the second term on the right comes from the moving lower limit of the integral. Let us write the integral in equation (13.8) as,

$$
F(r)=\int_r^{r_{\mathrm{Charlie}}}\frac{d\rho}{f(\rho)}
$$

If the lower limit $r$ is made slightly larger while the upper limit $r_{\mathrm{Charlie}}$ remains fixed, the interval being integrated becomes shorter by that amount. Therefore,

$$
\frac{dF}{dr}=-\frac1{f(r)}
$$

The sign is opposite to the case where the upper limit of the integral moves.

Furthermore, the lower limit $r$ changes with Bob’s proper time, so the chain rule gives,

$$
\frac{dF}{d\tau_{\mathrm{Bob}}}
=\frac{dF}{dr}\frac{dr}{d\tau_{\mathrm{Bob}}}
=-\frac1{f(r)}\frac{dr}{d\tau_{\mathrm{Bob}}}
$$

This is the second term on the right.

During the fall, $dr/d\tau_{\mathrm{Bob}}<0$, and outside the horizon $f(r)>0$, so the whole term is positive. It represents the fact that as Bob falls inward, the interval through which the light must travel to reach Charlie outside becomes longer, increasing the coordinate time required for propagation.

Substituting equations (13.4) and (13.5),

$$
\frac{dw_{\mathrm{receive}}}{d\tau_{\mathrm{Bob}}}
=\frac{\varepsilon+\sqrt{\varepsilon^2-f(r)}}{f(r)}.
$$

Charlie is sufficiently far away that he can read the interval of coordinate time between receptions directly as the interval on his own clock. Since $d\tau_{\mathrm{Charlie}}=dw_{\mathrm{receive}}$, we obtain,

$$
\boxed{
\frac{d\tau_{\mathrm{Charlie}}}{d\tau_{\mathrm{Bob}}}
=\frac{\varepsilon+\sqrt{\varepsilon^2-f(r)}}{f(r)}
}
\tag{13.9}
$$

The numerator on the left-hand side is the increment of Charlie’s receiving clock, and the denominator is the increment of Bob’s sending clock.

Unlike the case of a stationary sender in Chapter 12, a term containing a square root has been added. In addition to the advance of Bob’s own clock, this includes the propagation delay caused by sending the next light from farther inside.

### Motion Also Affects the Light Frequency

When the wavelength is sufficiently short that light can be treated as rays, the same calculation applies to nearby wave crests. If the frequencies measured by their own clocks are $\nu_{\mathrm{Bob}}$ and $\nu_{\mathrm{Charlie}}$, their ratio is the reciprocal of equation (13.9).

$$
\boxed{
\frac{\nu_{\mathrm{Charlie}}}{\nu_{\mathrm{Bob}}}
=\frac{f(r)}{\varepsilon+\sqrt{\varepsilon^2-f(r)}}
=\varepsilon-\sqrt{\varepsilon^2-f(r)}
}
\tag{13.10}
$$

For the last transformation, multiply the denominator and numerator by $\varepsilon-\sqrt{\varepsilon^2-f}$.

At the instant of departure, $f(r_0)=\varepsilon^2$, so the ratio is $\varepsilon=\sqrt{f(r_0)}$. This agrees with the equation for a stationary sender in Chapter 12 when the receiver is placed sufficiently far away.

While falling, Bob sends light as he moves away from Charlie outside. Thus, in addition to the gravitational redshift, there is a Doppler effect in which the received frequency decreases because of the motion. Equation (13.10) includes both effects.

### Can Charlie Watch Bob Reach the Horizon?

As the horizon is approached, $f\to0$, so the ratio in equation (13.9) diverges and the frequency ratio in equation (13.10) approaches zero. Light that Bob sends at a constant frequency arrives on Charlie’s clock with increasingly long intervals between oscillations, as a progressively lower frequency.

This is the relation between nearby emissions and receptions. If Bob blinks the light at finite intervals, such as one second, his position changes during that interval, so the arrival time of each signal is found separately from equation (13.8).

The closer to the horizon Bob sends the light, the more its coordinate-time arrival at Charlie is delayed without limit. Since the advance of Charlie’s clock agrees with the advance of coordinate time, even on his own clock he never receives, within a finite time, light announcing that Bob “has passed through the horizon.”

This does not mean that a sharp image of Bob remains permanently on the horizon. The arriving light is strongly redshifted, and actual detection also depends on the sensitivity of the receiving apparatus. Nor does this conflict with the fact that Bob’s proper time until the horizon is finite.

Bob’s own clock does not stop at the horizon. In equation (13.1), as $r=r_{\mathrm s}$ is approached, $f(r)\to0$, so the coefficient of $dw^2$ tends to zero and the coefficient of $dr^2$ tends to infinity. However, this expresses that the representation using Schwarzschild coordinates ceases to work at the horizon; it does not mean that spacetime itself breaks there.

At the horizon, curvature and tidal force do not have coordinate-independent divergences. However, the strength of the tidal force depends on the black hole’s mass, and for a small black hole it can be strong even at the horizon. To draw Bob’s passage through the horizon and his motion inside it in coordinates, we need to use different coordinates that do not break down at the horizon. We will not proceed there in this chapter, and limit ourselves to what can be understood from outside.

What matters here is to distinguish the time Bob experiences, the representation using Schwarzschild coordinates, and what Charlie learns through light.

---

Alice: “Bob’s clock keeps advancing without stopping. But light cannot be sent from inside to tell us, can it?”

Bob: “That’s right. We need to think separately about the elapsed time I experience and the information that can reach Charlie.”

---

## Read the Three Questions Separately

| Question | What we learned this time |
|---|---|
| How long does it take to reach the horizon according to Bob’s clock? | He reaches it in finite proper time |
| How is it drawn in Schwarzschild coordinate $w$? | Reaching the horizon occurs at $w\to\infty$ |
| What does Charlie receive? | Light sent just before the horizon arrives increasingly late and at a lower frequency; light announcing the passage does not arrive |

When using a metric, distinguish which coordinates are being used for the drawing, whose clock is being read, and which light is being received. For the same fall by Bob, these are answers to different questions.

In the next document [“Measuring Changes in the Metric with Light”](./14-MeasuringMetricChangesWithLight.md), let us return to measurements using clocks and light. By sending light back and forth and comparing two paths, we will consider how changes in the metric can be read.
