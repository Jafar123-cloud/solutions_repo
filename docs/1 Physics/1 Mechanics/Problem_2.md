# Theoretical Foundation: Forced Damped Pendulum

## Governing Equation

The motion is described by:

$$
\frac{d^2\theta}{dt^2} + b\frac{d\theta}{dt} + \frac{g}{L} \sin\theta = A\cos(\omega t)
$$

For small angles ($\sin\theta \approx \theta$), this simplifies to:

$$
\frac{d^2\theta}{dt^2} + b\frac{d\theta}{dt} + \frac{g}{L} \theta = A\cos(\omega t)
$$

## Solution

The general solution consists of:

1. **Homogeneous solution** (natural response):

   $$
   \theta_h(t) = C_1 e^{r_1 t} + C_2 e^{r_2 t}, \quad r^2 + br + \frac{g}{L} = 0
   $$

2. **Particular solution** (steady-state response):

   $$
   \theta_p(t) = \Theta_0 \cos(\omega t - \delta)
   $$

For long times, transient terms vanish, leaving only $\theta_p(t)$.

## Resonance Condition

Resonance occurs when $\omega = \sqrt{g/L}$, leading to maximum amplitude:

$$
\Theta_0 = \frac{A}{\sqrt{(\omega_0^2 - \omega^2)^2 + (b\omega)^2}}
$$

As damping $b$ decreases, oscillations grow sharper, seen in real-world systems like bridges and RLC circuits.

---

