# Problem 2
# Task 1: Theoretical Foundation: Forced Damped Pendulum

## Governing Equation

The motion of a forced damped pendulum is governed by the following second-order nonlinear differential equation:

$$
\frac{d^2\theta}{dt^2} + b\frac{d\theta}{dt} + \frac{g}{L} \sin\theta = A\cos(\omega t)
$$

where:  
- $\theta$ is the angular displacement,  
- $b$ is the damping coefficient,  
- $g$ is the acceleration due to gravity,  
- $L$ is the length of the pendulum,  
- $A$ is the amplitude of the external driving force,  
- $\omega$ is the driving frequency,  
- $t$ is time.

## Small-Angle Approximation

For small angles, we use the approximation:

$$
\sin\theta \approx \theta
$$

Substituting this into the equation simplifies it to:

$$
\frac{d^2\theta}{dt^2} + b\frac{d\theta}{dt} + \frac{g}{L} \theta = A\cos(\omega t)
$$

This is a linear, non-homogeneous differential equation, which can be solved using the method of undetermined coefficients or by considering the system's natural and forced response.

### General Solution

The solution consists of two parts:  

1. **Homogeneous solution** (solution to the undriven equation):

   $$
   \theta_h(t) = C_1 e^{r_1 t} + C_2 e^{r_2 t}
   $$

   where $r_1$ and $r_2$ are the roots of the characteristic equation:

   $$
   r^2 + br + \frac{g}{L} = 0
   $$

2. **Particular solution** (steady-state response due to the driving force):

   $$
   \theta_p(t) = \Theta_0 \cos(\omega t - \delta)
   $$

   where $\Theta_0$ is the amplitude of oscillation, and $\delta$ is the phase shift.

The full solution is:

$$
\theta(t) = C_1 e^{r_1 t} + C_2 e^{r_2 t} + \Theta_0 \cos(\omega t - \delta)
$$

For long times ($t \to \infty$), the transient terms ($C_1 e^{r_1 t} + C_2 e^{r_2 t}$) vanish due to damping, leaving only the steady-state oscillation.

## Resonance Condition

Resonance occurs when the driving frequency $\omega$ matches the system's natural frequency:

$$
\omega_0 = \sqrt{\frac{g}{L}}
$$

At resonance, the amplitude $\Theta_0$ of oscillations reaches a maximum:

$$
\Theta_0 = \frac{A}{\sqrt{(\omega_0^2 - \omega^2)^2 + (b\omega)^2}}
$$

As damping ($b$) decreases, the resonance peak becomes sharper, meaning the system absorbs more energy from the driving force.

### Implications of Resonance
- At resonance, the pendulum oscillates with large amplitude, potentially leading to chaotic motion for large angles.
- In real systems, excessive oscillations may lead to structural failure (e.g., bridges, buildings).
- Similar behavior is seen in electrical RLC circuits, where resonance maximizes current.

---


# Task 3 : Practical Applications of the Forced Damped Pendulum

The forced damped pendulum serves as a model for various real-world systems where periodic forces interact with damping and restoring forces.

## 1. Energy Harvesting Devices  
- Used in **vibration-based energy harvesters**, where mechanical motion is converted into electrical energy.  
- Examples: Piezoelectric and electromagnetic harvesters in smart sensors.

## 2. Suspension Bridges  
- Large structures like the **Tacoma Narrows Bridge** exhibit forced oscillations due to wind forces.  
- Understanding resonance helps in designing damping mechanisms to prevent catastrophic failures.

## 3. Oscillating Circuits  
- Electrical **RLC circuits** with alternating current behave analogously to the pendulum.  
- The driving force corresponds to an AC voltage, damping is due to resistance, and inductance plays the role of inertia.

## 4. Clocks and Timekeeping  
- **Pendulum clocks** rely on periodic motion but require controlled damping to maintain accuracy.  
- External forcing (e.g., escapement mechanism) ensures consistent oscillations.

## 5. Human Movement & Biomechanics  
- **Gait dynamics** in walking and running exhibit forced oscillatory behavior.  
- Studying these dynamics helps in prosthetic design and rehabilitation.

---

# Task 4 : Implementation: Simulating the Forced Damped Pendulum

To understand the complex behavior of the forced damped pendulum, we implement a computational model using Python. This model solves the equation of motion numerically and visualizes key dynamical features.

## 1. Governing Equation

The equation describing the motion is:

$$
\frac{d^2\theta}{dt^2} + b\frac{d\theta}{dt} + \frac{g}{L} \sin\theta = A\cos(\omega t)
$$

Rewriting as a system of first-order differential equations:

$$
\frac{d\theta}{dt} = \omega
$$

$$
\frac{d\omega}{dt} = -b\omega - \frac{g}{L} \sin\theta + A\cos(\Omega t)
$$

where:
- $\theta$ is the angular displacement,
- $\omega$ is the angular velocity,
- $b$ is the damping coefficient,
- $A$ is the driving amplitude,
- $\Omega$ is the driving frequency.

## 2. Numerical Simulation

We use the **fourth-order Runge-Kutta (RK4) method** to solve these equations. This approach ensures accurate integration of nonlinear dynamics.

### Python Implementation

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.integrate import solve_ivp

# Parameters
g, L = 9.81, 1.0  # Gravity and pendulum length
b = 0.2           # Damping coefficient
A = 1.2           # Driving amplitude
Omega = 2.0       # Driving frequency
theta0, omega0 = 0.2, 0.0  # Initial conditions
t_max, dt = 100, 0.01      # Simulation time

# Equations of motion
def pendulum(t, y):
    theta, omega = y
    dtheta_dt = omega
    domega_dt = -b * omega - (g / L) * np.sin(theta) + A * np.cos(Omega * t)
    return [dtheta_dt, domega_dt]

# Solve system
t_span = (0, t_max)
t_eval = np.arange(0, t_max, dt)
sol = solve_ivp(pendulum, t_span, [theta0, omega0], t_eval=t_eval, method='RK45')

# Extract results
theta, omega = sol.y
t = sol.t

# Plot time evolution
plt.figure(figsize=(10, 4))
plt.plot(t, theta, label=r'$\theta(t)$')
plt.xlabel('Time')
plt.ylabel('Angular Displacement')
plt.title('Time Evolution of the Forced Damped Pendulum')
plt.legend()
plt.grid()
plt.show()
```
![alt text](image-1.png)