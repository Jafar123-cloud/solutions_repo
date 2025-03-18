# Problem 3
# Task 1 : Analyzing the Possible Trajectories of a Payload Released Near Earth

When an object is released from a moving rocket near Earth, its trajectory depends on the object's initial conditions (such as velocity and position) and the gravitational forces acting on it. Understanding the possible trajectories is essential for planning space missions, such as deploying payloads or returning objects to Earth. The possible trajectories of the object include parabolic, hyperbolic, and elliptical paths, all governed by the principles of orbital mechanics and gravitational forces.

## 1. **Kepler's Laws and Newton's Law of Gravitation**

The motion of objects near Earth is primarily governed by the following principles:

- **Newton's Law of Gravitation** states that the force of gravity between two objects is proportional to the product of their masses and inversely proportional to the square of the distance between them:
  
  $$ F = \frac{G M m}{r^2} $$

  Where:
  - $F$ is the gravitational force,
  - $G$ is the gravitational constant ($6.67430 \times 10^{-11} \, \text{m}^3 \, \text{kg}^{-1} \, \text{s}^{-2}$),
  - $M$ is the mass of the Earth,
  - $m$ is the mass of the object,
  - $r$ is the distance between the center of the Earth and the object.

- **Kepler's Laws of Planetary Motion** describe the orbits of planets around the Sun. For objects near Earth, these laws can be applied to predict the trajectory, which can take various forms:
  - **Elliptical Orbits:** These are closed orbits where the object moves in an ellipse around the Earth.
  - **Parabolic Trajectories:** The object follows a path shaped like a parabola and will eventually escape Earth's gravitational pull if its speed is greater than the first cosmic velocity.
  - **Hyperbolic Trajectories:** The object follows a hyperbolic trajectory if its speed is greater than the second cosmic velocity, meaning it will escape Earth's gravity and travel away indefinitely.

## 2. **Types of Trajectories**

### 2.1. **Elliptical Trajectory**
An elliptical trajectory occurs when the object has less than the escape velocity but more than the orbital velocity (first cosmic velocity). The object will move in an elliptical orbit around Earth, eventually returning to its starting position unless disturbed by other forces.

The equation for an elliptical orbit is given by the vis-viva equation:

$$ v = \sqrt{GM \left( \frac{2}{r} - \frac{1}{a} \right)} $$

Where:
- $v$ is the velocity of the object,
- $G$ is the gravitational constant,
- $M$ is the mass of the Earth,
- $r$ is the distance from the center of the Earth to the object,
- $a$ is the semi-major axis of the ellipse.

### 2.2. **Parabolic Trajectory**
A parabolic trajectory occurs when the object's velocity is exactly equal to the escape velocity at a given distance from Earth. In this case, the object will travel on a path shaped like a parabola, eventually escaping Earth's gravity but not returning.

The escape velocity is given by:

$$ v_{\text{escape}} = \sqrt{\frac{2GM}{r}} $$

Where:
- $v_{\text{escape}}$ is the escape velocity,
- $G$ is the gravitational constant,
- $M$ is the mass of the Earth,
- $r$ is the distance from the center of Earth to the object.

### 2.3. **Hyperbolic Trajectory**
A hyperbolic trajectory occurs when the object's velocity is greater than the escape velocity. This trajectory is open and non-periodic, meaning the object will escape Earth's gravity and move away indefinitely, never returning.

The equation for a hyperbolic trajectory is similar to that of an elliptical trajectory but with higher velocities and larger energy:

$$ v = \sqrt{GM \left( \frac{2}{r} - \frac{1}{b} \right)} $$

Where:
- $v$ is the velocity of the object,
- $r$ is the distance from the center of Earth,
- $b$ is the distance of closest approach (a parameter describing the trajectory).

## 3. **Summary of Trajectories**

- **Elliptical Orbit**: Occurs when the object's velocity is between the orbital and escape velocities. The object will remain in orbit around Earth.
- **Parabolic Trajectory**: Occurs when the object's velocity is equal to the escape velocity. The object will escape Earth's gravity but will not return.
- **Hyperbolic Trajectory**: Occurs when the object's velocity exceeds the escape velocity. The object will escape Earth's gravitational influence and travel away indefinitely.

## 4. **Real-World Applications**

- **Satellite Deployment**: Satellites are typically launched into elliptical orbits. The initial velocity of the payload determines whether it will enter a stable orbit or escape Earth's gravity entirely.
- **Space Probes**: Space probes, like those sent to other planets, often follow parabolic or hyperbolic trajectories. They are given enough velocity to escape Earth's gravity and head toward their target destination, such as Mars or Jupiter.
- **Payloads Returning to Earth**: If a payload needs to return to Earth, its trajectory must be carefully controlled to ensure it follows a parabolic or elliptical path, eventually re-entering the atmosphere.

# Task 2 : Numerical Analysis of Payload Trajectory Based on Initial Conditions

In this task, we will perform a numerical analysis to compute the path of a payload released near Earth, given initial conditions such as position, velocity, and altitude. Using numerical methods like Euler’s method or the Runge-Kutta method, we can simulate the motion of the payload under the influence of Earth's gravity. This simulation will allow us to visualize the trajectory based on different initial conditions.

## 1. **Gravitational Forces and Equations of Motion**

The motion of the payload is governed by Newton's Law of Gravitation and the following equations:

- **Gravitational Force:** 
  $$ F = \frac{G M m}{r^2} $$

  Where:
  - $F$ is the gravitational force,
  - $G$ is the gravitational constant,
  - $M$ is the mass of the Earth,
  - $m$ is the mass of the object,
  - $r$ is the distance between the center of the Earth and the object.

- **Acceleration due to Gravity:**
  $$ a = \frac{F}{m} = \frac{G M}{r^2} $$

  Using the above force, we can calculate the acceleration at each point in the trajectory.

- **Equations of Motion:**
  Using the second law of motion ($F = ma$), we can determine the acceleration of the payload in both the radial and tangential directions:

  $$ \ddot{r} = - \frac{GM}{r^2} $$

  Where:
  - $\ddot{r}$ is the radial acceleration of the payload.

In our simulation, we will numerically solve the equations of motion using a simple numerical integration technique (Euler’s method) or a more accurate method (Runge-Kutta) to compute the position and velocity at each time step.

## 2. **Python Script for Numerical Simulation**

The following Python code uses Euler's method to simulate the trajectory of the payload based on initial conditions (position, velocity, and altitude). We will track the position and velocity at each time step and visualize the trajectory.

```python
import numpy as np
import matplotlib.pyplot as plt

# Constants
G = 6.67430e-11  # Gravitational constant (m^3 kg^-1 s^-2)
M = 5.972e24     # Mass of Earth (kg)
R = 6371e3       # Radius of Earth (m)

# Initial conditions: position, velocity, and altitude
initial_position = np.array([0, R + 100e3])  # Initial position: 100 km above Earth
initial_velocity = np.array([0, 7500])      # Initial velocity: 7.5 km/s tangential (typical orbital velocity)

# Time settings
dt = 10          # Time step (seconds)
total_time = 20000  # Total simulation time (seconds)
steps = int(total_time / dt)

# Arrays to store position and velocity over time
position = np.zeros((steps, 2))
velocity = np.zeros((steps, 2))
position[0] = initial_position
velocity[0] = initial_velocity

# Numerical simulation using Euler's method
for i in range(1, steps):
    r = np.linalg.norm(position[i-1])  # Distance from the center of Earth
    a = -G * M / r**2  # Radial acceleration (m/s^2)
    direction = position[i-1] / r  # Unit vector in the direction of the position
    
    # Update velocity and position using Euler's method
    velocity[i] = velocity[i-1] + np.array([a * direction[0], a * direction[1]]) * dt
    position[i] = position[i-1] + velocity[i] * dt

# Extract x and y positions for plotting
x_position = position[:, 0]
y_position = position[:, 1]

# Plot the trajectory of the payload
plt.figure(figsize=(8, 6))
plt.plot(x_position, y_position, label='Payload Trajectory')
plt.scatter(0, 0, color='red', label='Earth')  # Earth at the center
plt.title('Trajectory of Payload Released Near Earth')
plt.xlabel('Distance in x (m)')
plt.ylabel('Distance in y (m)')
plt.legend()
plt.grid(True)
plt.axis('equal')
plt.show()
![alt text](image-2.png)

