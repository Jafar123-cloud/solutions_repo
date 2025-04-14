# Problem 1

# Task: Measure the acceleration $g$ due to gravity using a pendulum and analyze uncertainties.

This exercise emphasizes rigorous measurement practices, uncertainty analysis, and their role in experimental physics.

## Procedure

### 1. Materials:

- A string (1 or 1.5 meters long).
- A small weight (e.g., bag of coins, bag of sugar, key chain) mounted on the string.
- Stopwatch (or smartphone timer).
- Ruler or measuring tape.

### 2. Setup:

- Attach the weight to the string and fix the other end to a sturdy support.
- Measure the length of the pendulum, $L$, from the suspension point to the center of the weight using a ruler or measuring tape. Record the resolution of the measuring tool and calculate the uncertainty as half the resolution: 
  $$ \Delta L = \frac{\text{Ruler Resolution}}{2} $$

### 3. Data Collection:

- Displace the pendulum slightly (<15°) and release it.
- Measure the time for 10 full oscillations ($T_{10}$) and repeat this process 10 times. Record all 10 measurements. 
- Calculate the mean time for 10 oscillations ($\overline{T}_{10}$) and the standard deviation ($\sigma_T$). 
- Determine the uncertainty in the mean time as:
  $$ \Delta T_{10} = \frac{\sigma_T}{\sqrt{n}} \quad \text{where} \quad n = 10 $$

## Calculations

### 1. Calculate the period:

- The period $T$ of one oscillation is given by:
  $$ T = \frac{\overline{T}_{10}}{10} $$
  And the uncertainty in the period is:
  $$ \Delta T = \frac{\Delta T_{10}}{10} $$

### 2. Determine $g$:

The acceleration due to gravity $g$ is given by the formula:
$$ g = \frac{4 \pi^2 L}{T^2} $$

### 3. Propagate uncertainties:

The uncertainty in $g$ can be propagated using the following formula:
$$ \Delta g = g \sqrt{\left( \frac{\Delta L}{L} \right)^2 + \left( 2 \frac{\Delta T}{T} \right)^2} $$

## Analysis

### 1. Compare your measured $g$ with the standard value:

The standard value of $g$ is:
$$ g_{\text{standard}} = 9.81 \, \text{m/s}^2 $$

### 2. Discuss:

- The effect of measurement resolution on $\Delta L$.
- Variability in timing and its impact on $\Delta T$.
- Any assumptions or experimental limitations.

## Deliverables:

1. Tabulated data in markdown:
   - $L$, $\Delta L$, $T_{10}$ measurements, $\overline{T}_{10}$, $\sigma_T$, $\Delta T$.
   - Calculated $g$ and $\Delta g$.
   
2. The discussion on sources of uncertainty and their impact on the results.
