# **Task 1 : Circular Wave Interference from a Point Source**

## **Wave Equation**
A circular wave on the water surface, emanating from a point source located at $ (x_0, y_0) $, can be described by:

$$
\eta(x, y, t) = \frac{A}{\sqrt{r}} \cdot \cos (kr - \omega t + \phi)
$$

where:

- $ \eta(x, y, t) $ = displacement of the water surface at point $ (x, y) $ and time $ t $.
- $ A $ = amplitude of the wave.
- $ k = \frac{2\pi}{\lambda} $ = wave number, related to the wavelength $ \lambda $.
- $ \omega = 2\pi f $ = angular frequency, related to the frequency $ f $.
- $ r = \sqrt{(x - x_0)^2 + (y - y_0)^2} $ = distance from the source to point $ (x, y) $.
- $ \phi $ = initial phase.

---

## **Wave Properties**
### **1. Relationship Between Wavelength, Frequency, and Speed**
The wave speed $ v $ is related to frequency and wavelength:

$$
v = f \lambda
$$

### **2. Wave Energy**
The energy of a wave is proportional to the square of the amplitude:

$$
E \propto A^2
$$

### **3. Superposition of Multiple Waves**
If multiple wave sources exist, the total displacement is given by:

$$
\eta_{\text{sum}}(x, y, t) = \sum_{i=1}^{N} \eta_i(x, y, t)
$$

where $ N $ is the number of sources.

---

---

## **Deliverables**
1. **Mathematical Model**:
   - Formulate the equations describing the waves from multiple sources.
   - Apply the **principle of superposition** to determine total displacement.
   
2. **Graphical Representation**:
   - Generate **visual simulations** showing interference patterns.
   - Identify **constructive** and **destructive** interference regions.
   
3. **Code Implementation**:
   - A Python script (or Jupyter Notebook) implementing the simulation.
   - Well-commented code for clarity.

---

## **Wave Equation for a Single Source**
A circular wave on the water surface, emanating from a point source located at $(x_0, y_0)$, is described by:

$$
\eta(x, y, t) = \frac{A}{\sqrt{r}} \cdot \cos (kr - \omega t + \phi)
$$

where:
- $A$ = amplitude of the wave.
- $k = \frac{2\pi}{\lambda}$ = wave number.
- $\omega = 2\pi f$ = angular frequency.
- $r = \sqrt{(x - x_0)^2 + (y - y_0)^2}$ = distance from the source.
- $\phi$ = initial phase.

---

## **Superposition of Waves from Multiple Sources**
For a polygon with $N$ sources at coordinates $(x_i, y_i)$, the total wave displacement is:

$$
\eta_{\text{sum}}(x, y, t) = \sum_{i=1}^{N} \frac{A}{\sqrt{r_i}} \cos (k r_i - \omega t + \phi)
$$

where $r_i$ is the distance from the $i$th source.

---

---

### **. Wave Equations**
Each wave source at position $ (x_i, y_i) $ emits a wave described by:

$$
\eta_i(x, y, t) = \frac{A}{\sqrt{r_i}} \cos (k r_i - \omega t + \phi)
$$

where:
- $ A $ = wave amplitude.
- $ k = \frac{2\pi}{\lambda} $ = wave number.
- $ \omega = 2\pi f $ = angular frequency.
- $ r_i = \sqrt{(x - x_i)^2 + (y - y_i)^2} $ = distance from source $ i $ to point $ (x, y) $.
- $ \phi $ = initial phase.

---

### **. Superposition of Waves**
The total wave displacement at each point on the water surface is given by the **principle of superposition**:

$$
\eta_{\text{sum}}(x, y, t) = \sum_{i=1}^{N} \eta_i(x, y, t)
$$

where $ N $ is the number of wave sources (vertices of the polygon).

---

### **. Analyze Interference Patterns**
- Examine the resulting displacement $ \eta_{\text{sum}}(x, y, t) $ as a function of position $ (x, y) $ and time $ t $.
- Identify:
  - **Constructive Interference**: Regions where waves reinforce each other (higher amplitude).
  - **Destructive Interference**: Regions where waves cancel out (lower amplitude).

---

### **1. Circular Wave from a Single Source**
```python
import numpy as np
import matplotlib.pyplot as plt

# Define parameters
A = 1
lambda_ = 1
f = 1
omega = 2 * np.pi * f
k = 2 * np.pi / lambda_
x0, y0 = 0, 0
phi = 0

# Create grid
x = np.linspace(-5, 5, 200)
y = np.linspace(-5, 5, 200)
X, Y = np.meshgrid(x, y)

# Compute distance from source
R = np.sqrt((X - x0)**2 + (Y - y0)**2)

# Compute wave displacement at t=0
eta = (A / np.sqrt(R + 1e-6)) * np.cos(k * R + phi)

# Plot
plt.figure(figsize=(6, 6))
plt.contourf(X, Y, eta, levels=50, cmap='coolwarm')
plt.colorbar(label="Wave Displacement")
plt.scatter(x0, y0, color='black', marker='o', label="Wave Source")
plt.legend()
plt.xlabel("X")
plt.ylabel("Y")
plt.title("Circular Wave from a Point Source")
plt.show()
```
![alt text](image.png)

```
# Define second source position
x1, y1 = 2, 0

# Compute distances
R1 = np.sqrt((X - x0)**2 + (Y - y0)**2)
R2 = np.sqrt((X - x1)**2 + (Y - y1)**2)

# Compute superposed wave displacement
eta_sum = (A / np.sqrt(R1 + 1e-6)) * np.cos(k * R1 + phi) + (A / np.sqrt(R2 + 1e-6)) * np.cos(k * R2 + phi)

# Plot
plt.figure(figsize=(6, 6))
plt.contourf(X, Y, eta_sum, levels=50, cmap='coolwarm')
plt.colorbar(label="Wave Displacement")
plt.scatter([x0, x1], [y0, y1], color='black', marker='o', label="Wave Sources")
plt.legend()
plt.xlabel("X")
plt.ylabel("Y")
plt.title("Superposition of Two Circular Waves")
plt.show()
```
![alt text](image-1.png)
```
# Define third source position
x2, y2 = 1, np.sqrt(3)

# Compute distances
R3 = np.sqrt((X - x2)**2 + (Y - y2)**2)

# Compute superposed wave displacement
eta_sum = (A / np.sqrt(R1 + 1e-6)) * np.cos(k * R1 + phi) + \
          (A / np.sqrt(R2 + 1e-6)) * np.cos(k * R2 + phi) + \
          (A / np.sqrt(R3 + 1e-6)) * np.cos(k * R3 + phi)

# Plot
plt.figure(figsize=(6, 6))
plt.contourf(X, Y, eta_sum, levels=50, cmap='coolwarm')
plt.colorbar(label="Wave Displacement")
plt.scatter([x0, x1, x2], [y0, y1, y2], color='black', marker='o', label="Wave Sources")
plt.legend()
plt.xlabel("X")
plt.ylabel("Y")
plt.title("Interference from Three Point Sources")
plt.show()
```
![alt text](image-2.png)