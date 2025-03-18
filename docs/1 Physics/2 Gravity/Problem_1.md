# Problem 1
# Task 1 : Derivation of Kepler's Third Law for Circular Orbits

Kepler's Third Law states that the square of the orbital period $T$ is proportional to the cube of the orbital radius $r$:

$$
T^2 \propto r^3
$$

In this section, we derive this relationship using Newton's laws of motion and the law of universal gravitation.

## 1. Centripetal Force and Gravitational Force

For a body in a **circular orbit** around a much larger mass (e.g., a planet orbiting a star), the **centripetal force** required to maintain the orbit is provided by the **gravitational force**:

### **Centripetal Force**
The centripetal force acting on a body of mass $m$ moving with velocity $v$ in a circular orbit of radius $r$ is:

$$
F_c = \frac{m v^2}{r}
$$

### **Gravitational Force**
The gravitational force exerted by a central mass $M$ (e.g., the Sun) on the orbiting body is given by Newton's Law of Gravitation:

$$
F_g = \frac{G M m}{r^2}
$$

where:
- $G$ is the universal gravitational constant,
- $M$ is the mass of the central body,
- $m$ is the mass of the orbiting body,
- $r$ is the orbital radius.

## 2. Equating Forces

Since gravity provides the necessary centripetal force, we set $F_c = F_g$:

$$
\frac{m v^2}{r} = \frac{G M m}{r^2}
$$

Canceling $m$ from both sides:

$$
\frac{v^2}{r} = \frac{G M}{r^2}
$$

Multiplying both sides by $r$:

$$
v^2 = \frac{G M}{r}
$$

## 3. Expressing Velocity in Terms of Orbital Period

The orbital velocity $v$ is related to the orbital period $T$ by:

$$
v = \frac{2\pi r}{T}
$$

Substituting this into the equation:

$$
\left(\frac{2\pi r}{T}\right)^2 = \frac{G M}{r}
$$

Expanding:

$$
\frac{4\pi^2 r^2}{T^2} = \frac{G M}{r}
$$

Multiplying both sides by $r$:

$$
4\pi^2 r^3 = G M T^2
$$

## 4. Final Form of Kepler's Third Law

Rearranging for $T^2$:

$$
T^2 = \frac{4\pi^2}{G M} r^3
$$

This shows that the square of the orbital period $T$ is **directly proportional** to the cube of the orbital radius $r$:

$$
T^2 \propto r^3
$$

This is Kepler's Third Law, which describes the relationship between the orbital period and the radius for objects in circular orbits around a massive central body.

---

This derivation is crucial in celestial mechanics, allowing astronomers to determine orbital properties of planets, moons, and satellites based on observational data.
