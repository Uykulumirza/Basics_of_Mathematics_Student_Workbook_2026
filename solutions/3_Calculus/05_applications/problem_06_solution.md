# Solution to Problem 6: Average Value of a Function

## 1. Problem Statement
Compute the average value of the function
$$
f(x)=x^2
$$
on the interval $[0,3]$.

Find a point $c\in[0,3]$ for which $f(c)$ is equal to this average value, and interpret the result geometrically.

---

## 2. Theoretical Background and Concepts
1. **Average Value of a Continuous Function**:
   For a finite set of numbers $y_1, y_2, \dots, y_n$, the arithmetic mean is $\frac{1}{n}\sum_{i=1}^n y_i$. Generalizing this to a continuous function $f(x)$ on a closed interval $[a, b]$ by partitioning $[a, b]$ into $n$ equal subintervals of width $\Delta x = \frac{b-a}{n}$ and taking the limit as $n \to \infty$:
   $$
   \frac{1}{n}\sum_{i=1}^n f(x_i^*) = \frac{1}{b-a}\sum_{i=1}^n f(x_i^*)\,\Delta x \xrightarrow{n \to \infty} f_{\text{avg}} = \frac{1}{b-a}\int_a^b f(x)\,dx.
   $$
2. **Mean Value Theorem for Definite Integrals**:
   If $f$ is continuous on the closed interval $[a, b]$, then there exists at least one point $c \in [a, b]$ such that $f(c)$ equals the average value of $f$ on $[a, b]$:
   $$
   f(c) = f_{\text{avg}} = \frac{1}{b-a}\int_a^b f(x)\,dx \quad \Longleftrightarrow \quad \int_a^b f(x)\,dx = f(c)(b - a).
   $$
3. **Geometric Meaning**:
   For a non-negative function $f(x) \ge 0$ on $[a, b]$, the integral $\int_a^b f(x)\,dx$ is the area under the curve $y = f(x)$, while $f(c)(b - a)$ is the area of a rectangle with base $[a, b]$ (width $b - a$) and constant height $H = f_{\text{avg}} = f(c)$.

---

## 3. Detailed Step-by-Step Solution

### Choosing Variables and Mathematical Tool
- $x \in [0, 3]$: independent variable on the interval $[a, b] = [0, 3]$ of length $b - a = 3 - 0 = 3$.
- $f(x) = x^2$: continuous function whose average level we seek.
- $f_{\text{avg}}$: average value of $f$ over $[0, 3]$.
- $c \in [0, 3]$: intermediate point guaranteed by the Mean Value Theorem for Integrals.

Because $f(x) = x^2$ varies continuously across $[0, 3]$, computing its continuous mean requires the **definite integral**.

---

### Step 1: Computing the Average Value $f_{\text{avg}}$ on $[0, 3]$
Applying the average value formula on $[a, b] = [0, 3]$:
$$
f_{\text{avg}} = \frac{1}{3 - 0}\int_0^3 x^2\,dx = \frac{1}{3}\int_0^3 x^2\,dx.
$$
First, we compute the definite integral (the area under $y = x^2$ on $[0, 3]$):
$$
\int_0^3 x^2\,dx = \left[\frac{x^3}{3}\right]_0^3 = \frac{3^3}{3} - \frac{0^3}{3} = \frac{27}{3} - 0 = 9.
$$
Dividing by the interval length $3 - 0 = 3$:
$$
f_{\text{avg}} = \frac{1}{3} \times 9 = 3.
$$
Thus, the average value of $f(x) = x^2$ on $[0, 3]$ is **$f_{\text{avg}} = 3$**.

---

### Step 2: Finding the Point $c \in [0, 3]$ Where $f(c) = f_{\text{avg}}$
We solve the equation $f(c) = f_{\text{avg}} = 3$ for $c \in [0, 3]$:
$$
c^2 = 3 \implies c = \pm\sqrt{3}.
$$
Checking membership in the given interval $[0, 3]$:
- $c = -\sqrt{3} \approx -1.732 \notin [0, 3]$ (rejected because it lies outside the domain $[0, 3]$).
- $c = \sqrt{3} \approx 1.732 \in [0, 3]$ (since $0 \le 1 < 3 < 9 \implies 0 \le 1 < \sqrt{3} < 3$).

Therefore, the unique point in $[0, 3]$ where $f(c) = f_{\text{avg}}$ is:
$$
c = \sqrt{3} \approx 1.732.
$$

---

### Step 3: Geometric Interpretation
Geometrically, the equality
$$
\int_0^3 x^2\,dx = f(\sqrt{3}) \cdot (3 - 0) = 3 \times 3 = 9
$$
means that:
1. The **area under the parabola** $y = x^2$ over the interval $[0, 3]$ is equal to **$9$** square units.
2. The **rectangle** with the same base $[0, 3]$ (width $3$) and constant height equal to the average value $y = f_{\text{avg}} = f(\sqrt{3}) = 3$ also has area $3 \times 3 = 9$ square units.
3. The horizontal line $y = 3$ intersects the graph $y = x^2$ at the point $(c, f(c)) = (\sqrt{3}, 3)$. If we imagine the region under $y = x^2$ as water or sand in a container of width $3$, leveling it out to a uniform depth produces a flat surface at height $y = 3$: the portion of the curve above $y = 3$ on $[\sqrt{3}, 3]$ has the exact same area as the empty space below $y = 3$ and above $y = x^2$ on $[0, \sqrt{3}]$.

```
    y ^
  9.0 +                                  * (3, 9)
      |                                 /|
      |                                / |
  6.0 +                               /  |  Area above y = 3
      |                              /   |  on [sqrt(3), 3]
      |                             /    |
  3.0 +----------------------------*-----+  <-- y = f_avg = 3
      |  Area below y = 3       .  |     |      Rectangle height = 3
      |  on [0, sqrt(3)]    .      |     |      Rectangle area = 3 x 3 = 9
  0.0 *------------------*---------+-----+---> x
      0            c = sqrt(3)          3.0
                     (~1.732)
```

---

## 4. Verification and Consistency Checks

1. **Equal-Area Compensation Check (Above vs. Below the Average Level $y = 3$)**:
   - The deficit area between $y = 3$ and $y = x^2$ on $[0, \sqrt{3}]$ is:
     $$
     A_{\text{below}} = \int_0^{\sqrt{3}} (3 - x^2)\,dx = \left[3x - \frac{x^3}{3}\right]_0^{\sqrt{3}} = 3\sqrt{3} - \frac{3\sqrt{3}}{3} = 2\sqrt{3}.
     $$
   - The excess area between $y = x^2$ and $y = 3$ on $[\sqrt{3}, 3]$ is:
     $$
     A_{\text{above}} = \int_{\sqrt{3}}^3 (x^2 - 3)\,dx = \left[\frac{x^3}{3} - 3x\right]_{\sqrt{3}}^3 = (9 - 9) - \left(\frac{3\sqrt{3}}{3} - 3\sqrt{3}\right) = 2\sqrt{3}.
     $$
   Since $A_{\text{below}} = A_{\text{above}} = 2\sqrt{3}$, the signed deviation $\int_0^3 (x^2 - 3)\,dx = 0$, confirming that $f_{\text{avg}} = 3$ is the exact mean value.

2. **Comparison with Endpoint Arithmetic Mean**:
   The arithmetic mean of the endpoint values is $\frac{f(0) + f(3)}{2} = \frac{0 + 9}{2} = 4.5$. Because $f(x) = x^2$ is strictly convex ($f''(x) = 2 > 0$), its graph lies below the secant line connecting $(0, 0)$ and $(3, 9)$, so the true integral average $f_{\text{avg}} = 3$ must be strictly less than $4.5$ ($3 < 4.5$), and the point $c = \sqrt{3} \approx 1.732$ lies to the right of the midpoint $1.5$.
