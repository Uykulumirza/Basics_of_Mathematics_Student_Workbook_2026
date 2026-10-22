# Solution to Problem 5: Distance from Velocity

## 1. Problem Statement
The velocity of a car during the first five seconds is described by the function
$$
v(t)=4t+2\quad [\mathrm{m/s}].
$$

Compute the distance traveled and explain why the integral of velocity gives the change in position.

Then answer what would have to be changed in the reasoning if the velocity also took negative values.

---

## 2. Theoretical Background and Concepts
In one-dimensional kinematics, position $s(t)$ and instantaneous velocity $v(t)$ are linked by both operations of calculus:
1. **Derivative Relation**: Instantaneous velocity is the rate of change of position with respect to time:
   $$
   v(t) = s'(t) = \frac{ds}{dt}.
   $$
2. **Accumulation of Change (Fundamental Theorem of Calculus)**:
   Because $s(t)$ is an antiderivative of $v(t)$, the definite integral of velocity over a time interval $[t_1, t_2]$ gives the **net change in position** (also called **net displacement**):
   $$
   \Delta s = s(t_2) - s(t_1) = \int_{t_1}^{t_2} s'(t)\,dt = \int_{t_1}^{t_2} v(t)\,dt.
   $$
3. **Displacement vs. Total Distance Traveled**:
   - **Net Displacement**: $\Delta s = \int_{t_1}^{t_2} v(t)\,dt$ is a signed quantity (positive if final position is ahead of initial position, negative if behind).
   - **Total Distance Traveled**: Distance $D$ is the total length of the path covered by the odometer, which is always non-negative and accumulates the **speed** $|v(t)|$:
     $$
     D = \int_{t_1}^{t_2} |v(t)|\,dt.
     $$
   - When $v(t) \ge 0$ throughout $[t_1, t_2]$, we have $|v(t)| = v(t)$, so total distance traveled and net displacement are identical.

---

## 3. Detailed Step-by-Step Solution

### Variable Definitions and Physical Domain
- $t \in [0, 5]\text{ [s]}$: time elapsed during the first five seconds of motion.
- $v(t) = 4t + 2\text{ [m/s]}$: instantaneous velocity of the car at time $t$.
- $s(t)\text{ [m]}$: position of the car along the road at time $t$.
- $D\text{ [m]}$: total distance traveled during $[0, 5]\text{ s}$.

Since we are given a rate of change $v(t) = s'(t)$ and want to find the total accumulated change over $[0, 5]$, the **definite integral** is the required mathematical tool.

---

### Part 1: Checking the Sign of Velocity and Computing the Distance Traveled
First, we check the sign of $v(t) = 4t + 2$ on the time interval $t \in [0, 5]$:
$$
\text{For } t \ge 0:\quad 4t \ge 0 \implies v(t) = 4t + 2 \ge 2 > 0.
$$
Because $v(t) > 0$ for all $t \in [0, 5]$, the car moves continuously forward in the positive direction without ever reversing. Consequently, $|v(t)| = v(t)$, and the **total distance traveled** $D$ equals the **net displacement** $\Delta s = s(5) - s(0)$:
$$
D = \int_0^5 |v(t)|\,dt = \int_0^5 (4t + 2)\,dt.
$$
We compute the definite integral using the Fundamental Theorem of Calculus (an antiderivative of $4t + 2$ is $2t^2 + 2t$):
$$
\begin{aligned}
D &= \left[2t^2 + 2t\right]_0^5 \\
&= \left(2(5)^2 + 2(5)\right) - \left(2(0)^2 + 2(0)\right) \\
&= (50 + 10) - 0 = 60\text{ m}.
\end{aligned}
$$
**Interpretation**: During the first $5$ seconds, the car travels a total distance of **$60\text{ m}$** (accelerating uniformly from $v(0) = 2\text{ m/s}$ to $v(5) = 22\text{ m/s}$ at constant acceleration $a = v'(t) = 4\text{ m/s}^2$).

---

### Part 2: Why the Integral of Velocity Gives the Change in Position
There are two complementary ways to understand why $\int_{t_1}^{t_2} v(t)\,dt = s(t_2) - s(t_1)$:

1. **Physical / Riemann Sum Explanation (Accumulation of Infinitesimal Displacements)**:
   Partition the time interval $[t_1, t_2]$ into many very short subintervals $[t_{i-1}, t_i]$ of duration $\Delta t_i$. On each tiny time interval $\Delta t_i$, the continuously varying velocity $v(t)$ is nearly constant and approximately equal to $v(t_i^*)$. For approximately constant velocity, the small change in position is:
   $$
   \Delta s_i \approx v(t_i^*)\,\Delta t_i \quad \left(\text{since } \text{displacement} = \text{velocity} \times \text{time}\right).
   $$
   Summing these small displacements over all subintervals gives the total change in position:
   $$
   s(t_2) - s(t_1) = \sum_{i=1}^n \Delta s_i \approx \sum_{i=1}^n v(t_i^*)\,\Delta t_i.
   $$
   Taking the limit as $\max \Delta t_i \to 0$, the Riemann sum converges to the definite integral $\int_{t_1}^{t_2} v(t)\,dt$.

2. **Analytical Explanation (Fundamental Theorem of Calculus)**:
   By definition, velocity is the derivative of position, $v(t) = s'(t)$. Therefore, $s(t)$ is an antiderivative of $v(t)$. By Part 2 of the Fundamental Theorem of Calculus (the Net Change Theorem):
   $$
   \int_{t_1}^{t_2} v(t)\,dt = \int_{t_1}^{t_2} s'(t)\,dt = s(t_2) - s(t_1).
   $$

---

### Part 3: What Changes If Velocity Also Takes Negative Values
If $v(t)$ takes both positive and negative values on $[t_1, t_2]$ (meaning the car moves forward when $v(t) > 0$ and moves backward/in reverse when $v(t) < 0$):
- The direct integral $\int_{t_1}^{t_2} v(t)\,dt = s(t_2) - s(t_1)$ still gives the **net displacement** (change in coordinate), where negative contributions from backward motion **subtract from (cancel)** positive contributions from forward motion.
- To compute the actual **total distance traveled** $D$, backward motion must **add** positively to the distance rather than subtract. Therefore, we must integrate the **speed** $|v(t)|$ instead of the signed velocity $v(t)$:
  $$
  D = \int_{t_1}^{t_2} |v(t)|\,dt.
  $$
- **Practical Procedure**:
  1. Find all stopping/turning times $c_1, c_2, \dots \in (t_1, t_2)$ where $v(t) = 0$ and $v(t)$ changes sign.
  2. Split the interval $[t_1, t_2]$ at those roots into subintervals on which $v(t)$ has a constant sign.
  3. Integrate $v(t)$ on the subintervals where $v(t) \ge 0$, and integrate $-v(t)$ (take the absolute value of the integral) on the subintervals where $v(t) < 0$, then sum the absolute values of the displacements on each subinterval.

---

## 4. Verification and Consistency Checks

1. **Dimensional (Unit) Analysis**:
   $$
   [D] = [v(t)] \cdot [dt] = \left[\frac{\text{m}}{\text{s}}\right] \cdot [\text{s}] = \text{m},
   $$
   confirming that the integral of velocity with respect to time has units of length (meters).

2. **Kinematic Formula & Trapezoidal Area Check**:
   Since $v(t) = 4t + 2$ is linear (constant acceleration $a = 4\text{ m/s}^2$ and initial velocity $v_0 = 2\text{ m/s}$):
   - By the classical kinematics formula for uniform acceleration:
     $$
     D = v_0 t + \frac{1}{2}a t^2 = 2(5) + \frac{1}{2}(4)(5)^2 = 10 + 50 = 60\text{ m}.
     $$
   - Geometrically, the region under $v(t) = 4t + 2$ on $[0, 5]$ is a trapezoid of width $5\text{ s}$ and parallel bases $v(0) = 2\text{ m/s}$ and $v(5) = 22\text{ m/s}$:
     $$
     \text{Area} = \frac{v(0) + v(5)}{2} \times 5 = \frac{2 + 22}{2} \times 5 = 12 \times 5 = 60\text{ m}.
     $$
   All three methods agree exactly.
