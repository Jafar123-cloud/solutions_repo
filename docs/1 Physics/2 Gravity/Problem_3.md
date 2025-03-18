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

