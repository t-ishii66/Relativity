# Gravitational Redshift and the Propagation of Light

![At an observatory at dusk, Alice holds a clock while Bob adjusts a light-emitting device as they prepare an experiment to send light signals](../../../images/general-relativity/12/alice-bob-light-signals.png)

*Alice and Bob prepare to send light while watching a clock. How will the interval between transmissions read on the clock of someone receiving them far away?*

## Introduction

In the previous document [“Coordinates as a Canvas and Local Measurements”](./11-CoordinatesAndLocalMeasurements.md), we connected coordinate differences with the readings of clocks and rulers carried by observers at rest at those locations.

In this chapter as well, we consider the static vacuum region outside a spherically symmetric star, where $r>r_{\mathrm s}$.

$$
f(r)=1-\frac{r_{\mathrm s}}r,\qquad
r_{\mathrm s}=\frac{2GM}{c^2}
$$

Writing this, the metric is

$$
ds^2=-f(r)dw^2+\frac{dr^2}{f(r)}
+r^2(d\theta^2+\sin^2\theta\,d\phi^2)
\qquad (12.1)
$$

The scale of $w$ is chosen so that it advances by the same amount as the proper time of a clock at rest far away.

The proper time of an observer at rest at that location and the reading of a ruler in the radial direction were

$$
d\tau=\sqrt{f(r)}\,dw,\qquad
d\ell=\frac{|dr|}{\sqrt{f(r)}}
\qquad (12.2)
$$

Both $w$ and $\tau$ have units of distance, but since they are times multiplied by the same constant $c$, their ratio lets us compare how clocks advance.

This time, let us use this correspondence to actually send light and compare clocks. We will also check the relationship between the propagation of light on the canvas and the speed of light measured with instruments held locally.

---

Alice: “I understand the relationship between my clock and the coordinate scale. But if I send light to someone far away, how is the rate of my clock conveyed?”

Bob: “Let us also examine the path the light takes before it arrives. If we measure the sending interval and the receiving interval with the respective clocks, we can compare them.”

---

## Alice Sends Light and Charlie Receives It

Suppose Alice is at rest at $r_{\mathrm{Alice}}$ near the star, while Charlie is at rest farther out at $r_{\mathrm{Charlie}}$.

$$
r_{\mathrm s}<r_{\mathrm{Alice}}<r_{\mathrm{Charlie}}
$$

Both are outside the star’s surface, supported by a platform, rocket, or something similar, and remain in place without changing $r,\theta,\phi$. They are aligned in the same angular direction, with Charlie receiving the light Alice sends outward.

| Character | Location and role | Equipment |
|---|---|---|
| Alice | At rest at $r_{\mathrm{Alice}}$, sending light outward | Clock and light-emitting device |
| Charlie | At rest at $r_{\mathrm{Charlie}}$, receiving the light | Clock and light-receiving device |

Unlike Bob, who was in free fall in the previous chapter, both the sender and receiver in this case are at rest with respect to the coordinates.

First, suppose Alice sends two short light signals while watching her own clock. Charlie measures the interval between the arrivals of the two signals with his own clock.

What we compare here is the interval between two events called transmissions and the interval between another two events called receptions. We need to use the path of the light to connect these two pairs.

## The Light Path Has $ds^2=0$

Consider light traveling in the $X$ direction in a local inertial frame. If the time coordinate in distance units is $W$, the invariance of the speed of light can be written as

$$
|dX|=dW
$$

Therefore, the infinitesimal interval along the light’s path is

$$
ds^2=-dW^2+dX^2=0
$$

Since $ds^2$ has the same value even when the coordinates are changed, $ds^2=0$ on the light’s path in the original $(w,r,\theta,\phi)$ coordinates as well.

This time the light travels radially, so $d\theta=d\phi=0$. Substituting into equation (12.1) gives

$$
0=-f(r)dw^2+\frac{dr^2}{f(r)}
$$

Multiplying both sides by $f(r)$ and rearranging gives

$$
dr^2=f(r)^2dw^2
$$

Taking the future-directed $dw>0$, we obtain

$$
\boxed{\frac{dr}{dw}=\pm f(r)}
\qquad (12.3)
$$

The plus sign represents outward-moving light, and the minus sign inward-moving light.

On a canvas with $r$ as the horizontal axis and $w$ as the vertical axis, the slope of outward-moving light is $dw/dr=1/f(r)$. Far away, $f(r)\to1$, so the light line approaches 45 degrees when drawn at the same scale. Near the star, $f(r)<1$, so the line stands more vertically.

This is the coordinate relationship on the canvas. We will later convert it into clock and ruler readings to check the speed of light measured locally.

## The Two Signals Arrive After the Same Coordinate-Time Interval

For outward-moving light, rewrite equation (12.3) as

$$
dw=\frac{dr}{f(r)}
$$

Integrating from Alice’s location to Charlie’s location, the coordinate time taken for one signal to travel from transmission to reception is

$$
\mathcal D
=\int_{r_{\mathrm{Alice}}}^{r_{\mathrm{Charlie}}}\frac{dr}{f(r)}
\qquad (12.4)
$$

$\mathcal D$ is the increment in $w$ and has units of distance.

The $f(r)$ used in this integral does not depend on $w$. Also, the two people’s positions do not change. Therefore, for light traveling along the same path, the coordinate-time increment $\mathcal D$ until arrival is the same even when the departure coordinate time differs.

If the first signal is sent at $w_1$ and the next at $w_2$, the coordinates of the events are as follows.

| Signal | Coordinate time Alice sends it | Coordinate time Charlie receives it |
|---|---|---|
| First | $w_1$ | $w_1+\mathcal D$ |
| Second | $w_2$ | $w_2+\mathcal D$ |

Comparing the coordinate-time intervals between reception and transmission, the common $\mathcal D$ cancels:

$$
\begin{aligned}
\Delta w_{\mathrm{receive}}
&=(w_2+\mathcal D)-(w_1+\mathcal D)\\
&=w_2-w_1
=\Delta w_{\mathrm{send}}
\end{aligned}
$$

In other words, the interval between the two signals is equal for the sender and receiver in the common coordinate time $w$. Below, we write this interval as $\Delta w$.

---

Alice: “It takes time for the light to arrive, but since both signals take the same amount of time, the interval does not change.”

Bob: “That is true for the interval in coordinate time. Next, let us read that interval with Alice’s and Charlie’s clocks.”

---

## The Signal Intervals Differ When Read on the Two Clocks

For short, let us write

$$
f_{\mathrm{Alice}}=f(r_{\mathrm{Alice}}),\qquad
f_{\mathrm{Charlie}}=f(r_{\mathrm{Charlie}})
$$

Since both remain at the same locations, these two factors are constant. Integrating equation (12.2) along each clock, the proper time marked by Alice’s clock between the two transmissions and the proper time marked by Charlie’s clock between the two receptions are

$$
\Delta\tau_{\mathrm{Alice}}
=\sqrt{f_{\mathrm{Alice}}}\,\Delta w,
\qquad
\Delta\tau_{\mathrm{Charlie}}
=\sqrt{f_{\mathrm{Charlie}}}\,\Delta w
$$

Eliminating the same $\Delta w$ gives

$$
\boxed{
\frac{\Delta\tau_{\mathrm{Charlie}}}{\Delta\tau_{\mathrm{Alice}}}
=\sqrt{\frac{f_{\mathrm{Charlie}}}{f_{\mathrm{Alice}}}}
}
\qquad (12.5)
$$

The farther out we go, the larger $f(r)$ is, so in this arrangement $f_{\mathrm{Charlie}}>f_{\mathrm{Alice}}$. Therefore, the interval between receptions measured by Charlie’s clock is longer than the interval between transmissions measured by Alice’s clock.

For example, if $f_{\mathrm{Alice}}=0.81$ and $f_{\mathrm{Charlie}}=0.9025$, their square roots are $0.9$ and $0.95$, so

$$
\Delta\tau_{\mathrm{Charlie}}
=\frac{0.95}{0.9}\Delta\tau_{\mathrm{Alice}}
\simeq1.056\,\Delta\tau_{\mathrm{Alice}}
$$

In seconds, signals sent by Alice at one-second intervals on her clock are received by Charlie at intervals of about 1.056 seconds on his clock. Dividing both proper times by $c$ does not change this ratio.

Here, for the first time, we have connected the difference in the rates of clocks with the intervals between signals arriving from a distant counterpart.

## From Flash Intervals to Light Frequency

So far, we have considered two short signals sent by a light-emitting device. Next, consider a continuous light wave and follow wave crests instead of two signals. We assume here that the wavelength is sufficiently short compared with the scale over which spacetime curvature changes, so that light propagation can be treated as rays. The same discussion of equal coordinate-time intervals applies to wave crests traveling through vacuum along the same path.

Suppose Alice sends $N$ oscillations during some interval, and Charlie receives the same $N$ oscillations. Write the frequencies measured by each on their own clocks as $\nu_{\mathrm{Alice}},\nu_{\mathrm{Charlie}}$.

Frequency is the number of oscillations per second. Since proper time is in distance units, using the elapsed time in seconds, $\Delta\tau/c$, we can write

$$
\nu_{\mathrm{Alice}}
=\frac{N}{\Delta\tau_{\mathrm{Alice}}/c},\qquad
\nu_{\mathrm{Charlie}}
=\frac{N}{\Delta\tau_{\mathrm{Charlie}}/c}
$$

Taking the ratio cancels $N$ and $c$, and from equation (12.5) we obtain

$$
\boxed{
\frac{\nu_{\mathrm{Charlie}}}{\nu_{\mathrm{Alice}}}
=\frac{\Delta\tau_{\mathrm{Alice}}}{\Delta\tau_{\mathrm{Charlie}}}
=\sqrt{\frac{f_{\mathrm{Alice}}}{f_{\mathrm{Charlie}}}}
=\sqrt{\frac{1-r_{\mathrm s}/r_{\mathrm{Alice}}}
{1-r_{\mathrm s}/r_{\mathrm{Charlie}}}}
}
\qquad (12.6)
$$

The frequency measured by Charlie outside is lower than the frequency measured by Alice on the transmitting side. This change is called **gravitational redshift**. In visible light, the lower-frequency side is the redder side, which is why it has this name.

In the limit where Charlie is placed sufficiently far away, $f_{\mathrm{Charlie}}\to1$, so

$$
\frac{\nu_{\mathrm{Charlie}}}{\nu_{\mathrm{Alice}}}
\longrightarrow\sqrt{1-\frac{r_{\mathrm s}}{r_{\mathrm{Alice}}}}
$$

Here, it is the ratio of frequencies that is being taken to the far-away limit. This does not mean that light propagation to infinity takes only a finite amount of time.

Conversely, if Charlie outside sends light to Alice inside, the frequency measured by Alice upon reception is higher. This is gravitational blueshift, and it can be found by exchanging the sender and receiver in equation (12.6).

---

Charlie: “Even though I received the same light as Alice’s device sent, when I count the oscillations on my clock, there are fewer per second.”

Alice: “So my clock and light-emitting device are not malfunctioning at the place where I am.”

Bob: “That’s right. It is the result of reading, on the clocks at the two locations, the intervals between transmission and reception connected by light.”

---

## What Happens to the Locally Measured Speed of Light?

In equation (12.3), the coordinate change of light was $dr/dw=\pm f(r)$. Using $w=ct$ to convert to coordinate time in seconds gives

$$
\frac{dr}{dt}=\pm c f(r)
$$

Near the star, its absolute value is smaller than $c$. Does this mean that the speed of light measured by Alice with her own clock and ruler also becomes smaller?

At Alice’s point, use local components adapted to the clock and ruler. From Chapter 11,

$$
dW=\sqrt{f(r)}\,dw,\qquad
dX=\frac{dr}{\sqrt{f(r)}}
$$

Take the positive direction of $X$ to be outward. Comparing these along the light’s path gives

$$
\frac{dX}{dW}
=\frac{dr/\sqrt{f(r)}}{\sqrt{f(r)}\,dw}
=\frac1{f(r)}\frac{dr}{dw}
=\pm1
$$

The local time increment in seconds is $dW/c$, so the speed of light measured by Alice locally is

$$
\boxed{\frac{|dX|}{dW/c}=c}
$$

Charlie also obtains $c$ by doing the same calculation at his own location.

When the coordinate differences $dr,dw$ are converted into the ruler and clock readings at that location, the factors of $f(r)$ cancel. The fact that the slope on the canvas changes from place to place is compatible with the fact that the locally measured speed of light is constant.

### As Frequency Decreases, Wavelength Increases

![Alice and Bob compare the colors of light separated by a prism on a screen](../../../images/general-relativity/12/alice-bob-light-spectrum.png)

*Alice and Bob examine the colors of light. The figure illustrates dispersion by a prism and is not an experiment reproducing gravitational redshift itself.*

For both of them, the locally measured speed of light is $c$. If the locally measured wavelengths are written as $\lambda_{\mathrm{Alice}},\lambda_{\mathrm{Charlie}}$, then from $\lambda\nu=c$,

$$
\frac{\lambda_{\mathrm{Charlie}}}{\lambda_{\mathrm{Alice}}}
=\frac{\nu_{\mathrm{Alice}}}{\nu_{\mathrm{Charlie}}}
=\sqrt{\frac{f_{\mathrm{Charlie}}}{f_{\mathrm{Alice}}}}
$$

For light arriving farther out, local measurements by the receiver find a lower frequency and a longer wavelength. Redshift does not mean that the speed of light becomes smaller at the receiver.

## Conditions Supporting This Comparison

Let us organize the path that led to the result.

| What we examined | Result | What we used |
|---|---|---|
| Path of radial light | $dr/dw=\pm f(r)$ | $ds^2=0$ along the light path |
| Coordinate-time interval of two signals | $\Delta w_{\mathrm{receive}}=\Delta w_{\mathrm{send}}$ | The metric does not depend on time, and the sender and receiver are at rest |
| Interval measured by the two clocks | $\Delta\tau_{\mathrm{Charlie}}/\Delta\tau_{\mathrm{Alice}}=\sqrt{f_{\mathrm{Charlie}}/f_{\mathrm{Alice}}}$ | $d\tau=\sqrt f\,dw$ at each location |
| Frequencies measured by the two people | $\nu_{\mathrm{Charlie}}/\nu_{\mathrm{Alice}}=\sqrt{f_{\mathrm{Alice}}/f_{\mathrm{Charlie}}}$ | Each counts the same number of oscillations with their own clock |
| Locally measured speed of light | $c$ | Convert both clock and ruler readings into local readings |

This time, the coordinate time required for the two signals to propagate was equal because neither the light path nor the positions at its two ends changed with the departure time.

If freely falling Bob sends signals, his position has changed by the time he sends the next signal. Since the coordinate time required for propagation also changes, the formula for the stationary sender and receiver in this case cannot be used as it stands. In addition to the rate of Bob’s own clock, we must also consider the Doppler effect due to his motion.

In the next document [“Free Fall and the Event Horizon”](./13-FreeFallAndEventHorizon.md), we will find the motion of freely falling Bob and examine what happens to Bob’s clock and to the light reaching far away as he approaches the event horizon.
