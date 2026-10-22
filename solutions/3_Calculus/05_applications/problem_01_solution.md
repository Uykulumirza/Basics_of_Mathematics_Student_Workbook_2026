# Solution to Problem 1: Motion — from Position to Velocity

## 1. Problem Statement
The position of a point is described by
$$
s(t)=t^3-6t^2+9t+2,\qquad t\ge0.
$$

1. Determine the velocity and acceleration.
2. Find the times at which the point stops.
3. Determine on which intervals the point moves in the positive direction of the axis and on which intervals it moves in the negative direction.

---

## 2. Theoretical Background and Concepts
In one-dimensional kinematics along a coordinate axis, the motion of a point is described by its **position function** $s(t)$ as a function of time $t \ge 0$. Differential calculus provides the instantaneous rates of change of motion:
1. **Instantaneous Velocity**: Velocity is the first derivative of position with respect to time:
   $$
   v(t) = s'(t) = \frac{ds}{dt}.
   $$
   - The **magnitude** $|v(t)|$ is the instantaneous speed of the point.
   - The **sign** of $v(t)$ indicates the direction of motion along the coordinate axis:
     - If $v(t) > 0$ on an interval, $s(t)$ is strictly increasing, and the point moves in the **positive direction** of the axis.
     - If $v(t) < 0$ on an interval, $s(t)$ is strictly decreasing, and the point moves in the **negative direction** of the axis.
     - If $v(t) = 0$, the point is **instantaneously at rest** (stops). If $v(t)$ changes sign at such an instant, the point reverses its direction of motion (a turning point).
2. **Instantaneous Acceleration**: Acceleration is the derivative of velocity (the second derivative of position) with respect to time:
   $$
   a(t) = v'(t) = s''(t) = \frac{d^2s}{dt^2}.
   $$
   It measures how rapidly the velocity itself changes with time.

---

## 3. Detailed Step-by-Step Solution

### Variable Definitions and Physical Domain
- $t \ge 0$: time (measured in standard time units, e.g., seconds $\text{s}$), with physical domain $D_t = [0, \infty)$.
- $s(t)$: coordinate (position) of the moving point along the axis at time $t$ (e.g., in meters $\text{m}$).
- $v(t) = s'(t)$: instantaneous velocity at time $t$ (e.g., in $\text{m/s}$).
- $a(t) = s''(t)$: instantaneous acceleration at time $t$ (e.g., in $\text{m/s}^2$).

Since we want to analyze instantaneous rates of change of position and velocity, **differentiation** is the appropriate mathematical tool.

---

### Part 1: Velocity and Acceleration Functions
Differentiating the polynomial position function $s(t) = t^3 - 6t^2 + 9t + 2$ term-by-term using the power rule $\frac{d}{dt}(t^n) = nt^{n-1}$ gives the **velocity function**:
$$
v(t) = s'(t) = \frac{d}{dt}\left(t^3 - 6t^2 + 9t + 2\right) = 3t^2 - 12t + 9.
$$
Factoring out the common factor $3$ yields:
$$
v(t) = 3(t^2 - 4t + 3) = 3(t - 1)(t - 3),\qquad t \ge 0.
$$

Differentiating the velocity function $v(t) = 3t^2 - 12t + 9$ with respect to $t$ gives the **acceleration function**:
$$
a(t) = v'(t) = s''(t) = \frac{d}{dt}\left(3t^2 - 12t + 9\right) = 6t - 12 = 6(t - 2),\qquad t \ge 0.
$$

---

### Part 2: Times at Which the Point Stops
The point stops (is instantaneously at rest) whenever its instantaneous velocity is zero:
$$
v(t) = 0 \iff 3(t - 1)(t - 3) = 0.
$$
Since a product of factors is zero if and only if at least one factor is zero, we obtain:
$$
t_1 = 1 \quad \text{or} \quad t_2 = 3.
$$
Both values belong to the physical domain $t \ge 0$. At these stopping times, the positions and accelerations of the point are:
- At $t_1 = 1$:
  $$
  s(1) = 1^3 - 6(1)^2 + 9(1) + 2 = 1 - 6 + 9 + 2 = 6, \qquad a(1) = 6(1) - 12 = -6 < 0.
  $$
- At $t_2 = 3$:
  $$
  s(3) = 3^3 - 6(3)^2 + 9(3) + 2 = 27 - 54 + 27 + 2 = 2, \qquad a(3) = 6(3) - 12 = 6 > 0.
  $$

Thus, the point stops at **$t = 1$** (at position $s = 6$) and at **$t = 3$** (at position $s = 2$).

---

### Part 3: Intervals of Motion in the Positive and Negative Directions
To determine the direction of motion on $[0, \infty)$, we analyze the sign of the factored velocity function
$$
v(t) = 3(t - 1)(t - 3)
$$
across the subintervals determined by the stopping times $t = 1$ and $t = 3$:

1. **On the interval $[0, 1)$**:
   For $0 \le t < 1$, we have $t - 1 < 0$ and $t - 3 < 0$. The product of two negative factors is positive:
   $$
   v(t) = 3(\underbrace{t - 1}_{<0})(\underbrace{t - 3}_{<0}) > 0.
   $$
   Therefore, on **$[0, 1)$** the point moves in the **positive direction** of the axis (from $s(0) = 2$ to $s(1) = 6$).

2. **On the interval $(1, 3)$**:
   For $1 < t < 3$, we have $t - 1 > 0$ and $t - 3 < 0$. The product of a positive and a negative factor is negative:
   $$
   v(t) = 3(\underbrace{t - 1}_{>0})(\underbrace{t - 3}_{<0}) < 0.
   $$
   Therefore, on **$(1, 3)$** the point moves in the **negative direction** of the axis (from $s(1) = 6$ back to $s(3) = 2$).

3. **On the interval $(3, \infty)$**:
   For $t > 3$, we have $t - 1 > 0$ and $t - 3 > 0$. The product of two positive factors is positive:
   $$
   v(t) = 3(\underbrace{t - 1}_{>0})(\underbrace{t - 3}_{>0}) > 0.
   $$
   Therefore, on **$(3, \infty)$** the point moves in the **positive direction** of the axis (from $s(3) = 2$ toward $+\infty$).

#### Summary Sign Chart for Velocity and Motion
| Time Interval / Instant | $t = 0$ | $0 \le t < 1$ | $t = 1$ | $1 < t < 3$ | $t = 3$ | $t > 3$ |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Sign of $t - 1$ | $-$ | $-$ | $0$ | $+$ | $+$ | $+$ |
| Sign of $t - 3$ | $-$ | $-$ | $-$ | $-$ | $0$ | $+$ |
| Velocity $v(t)$ | $+9$ | $+$ | $0$ | $-$ | $0$ | $+$ |
| Position $s(t)$ | $2$ | $\nearrow$ (increases) | $6$ (local max) | $\searrow$ (decreases) | $2$ (local min) | $\nearrow$ (increases) |
| Direction of Motion | Positive | **Positive ($+$)** | **Stopped** | **Negative ($-$)** | **Stopped** | **Positive ($+$)** |

---

## 4. Verification and Consistency Checks

1. **Displacement Consistency Check on Each Subinterval**:
   - At $t = 0$: $s(0) = 0^3 - 6(0)^2 + 9(0) + 2 = 2$.
   - Over $[0, 1]$: $\Delta s_{[0,1]} = s(1) - s(0) = 6 - 2 = +4 > 0$, confirming motion in the **positive direction** by $4$ units.
   - Over $[1, 3]$: $\Delta s_{[1,3]} = s(3) - s(1) = 2 - 6 = -4 < 0$, confirming motion in the **negative direction** by $4$ units (returning to $s = 2$).
   - Over $[3, 4]$ (test interval in $(3, \infty)$): $s(4) = 4^3 - 6(4)^2 + 9(4) + 2 = 64 - 96 + 36 + 2 = 6$, so $\Delta s_{[3,4]} = s(4) - s(3) = 6 - 2 = +4 > 0$, confirming motion in the **positive direction**.

2. **Test-Point Evaluation of $v(t)$**:
   - At $t = 0.5 \in [0, 1)$: $v(0.5) = 3(0.5 - 1)(0.5 - 3) = 3(-0.5)(-2.5) = +3.75 > 0$.
   - At $t = 2 \in (1, 3)$: $v(2) = 3(2 - 1)(2 - 3) = 3(1)(-1) = -3 < 0$ (this is also the inflection point where $a(2) = 0$ and the negative velocity is most negative).
   - At $t = 4 \in (3, \infty)$: $v(4) = 3(4 - 1)(4 - 3) = 3(3)(1) = +9 > 0$.

3. **Fundamental Theorem of Calculus Check**:
   Integrating $v(t) = 3t^2 - 12t + 9$ from $0$ to $t$ with initial position $s(0) = 2$ recovers:
   $$
   s(t) = s(0) + \int_0^t (3\tau^2 - 12\tau + 9)\,d\tau = 2 + \left[\tau^3 - 6\tau^2 + 9\tau\right]_0^t = t^3 - 6t^2 + 9t + 2,
   $$
   which matches the original position function identically.
