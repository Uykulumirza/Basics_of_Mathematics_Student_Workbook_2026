# Solution to Problem 9: Definite Integral and Geometric Area

## 1. Problem Statement

Compute
$$\int_{-1}^{2}x\,dx.$$
Then separately compute the areas of the parts of the graph below and above the $x$-axis and explain the difference between the definite integral and geometric area.

> **Why this problem:** it clarifies the difference between signed accumulation and area.

---

## 2. Theoretical Background and Concepts

### The Fundamental Theorem of Calculus (Newton–Leibniz Formula)
If $f: [a, b] \to \mathbb{R}$ is continuous and $F$ is any antiderivative of $f$ on $[a, b]$ ($F'(x) = f(x)$), then the definite integral of $f$ from $a$ to $b$ is given by:
$$\int_a^b f(x)\,dx = \big[F(x)\big]_a^b = F(b) - F(a).$$

### Net Signed Area vs. Total Geometric Area
1. **Definite Integral (Net Signed Area):**
   In the Riemann sum definition $\int_a^b f(x)\,dx = \lim_{\|\Delta\|\to 0} \sum_i f(x_i^*)\,\Delta x_i$, the width $\Delta x_i > 0$ is multiplied by the signed function value $f(x_i^*)$. Consequently:
   - Regions where $f(x) \ge 0$ (above the $x$-axis) contribute **positively** ($+A_{\text{above}}$).
   - Regions where $f(x) \le 0$ (below the $x$-axis) contribute **negatively** ($-A_{\text{below}}$).
   $$\int_a^b f(x)\,dx = A_{\text{above}} - A_{\text{below}}.$$

2. **Total Geometric Area:**
   Geometric area is an intrinsically non-negative measure. The total area enclosed between the graph $y = f(x)$ and the $x$-axis over $[a, b]$ sums both regions with a positive sign:
   $$A_{\text{total}} = \int_a^b |f(x)|\,dx = A_{\text{above}} + A_{\text{below}}.$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Computing the Definite Integral $\int_{-1}^2 x\,dx$
Using the power rule, an antiderivative of $f(x) = x$ is $F(x) = \frac{x^2}{2}$ (verified by $F'(x) = \frac{d}{dx}\left(\frac{x^2}{2}\right) = \frac{2x}{2} = x$).

Applying the Fundamental Theorem of Calculus on $[-1, 2]$:
$$\begin{aligned}
\int_{-1}^2 x\,dx &= \left[\frac{x^2}{2}\right]_{-1}^2 \\
&= \frac{2^2}{2} - \frac{(-1)^2}{2} \\
&= \frac{4}{2} - \frac{1}{2} \\
&= 2 - \frac{1}{2} = \frac{3}{2} = 1.5.
\end{aligned}$$

### Step 2: Computing the Geometric Areas Below and Above the $x$-Axis Separately
The function $f(x) = x$ crosses the $x$-axis at $x = 0$, splitting the interval $[-1, 2]$ into two subintervals:
- On $[-1, 0]$, we have $f(x) = x \le 0$ (the graph lies **below** the $x$-axis).
- On $[0, 2]$, we have $f(x) = x \ge 0$ (the graph lies **above** the $x$-axis).

```
      y
    2 +                   /| (2, 2)
      |                 /  |
    1 +               /    |   A_above = 2
      |             /  (+) |
  ----+-----+-----/--------+---> x
     -1     |   0/    1    2
      | (-) |  /
   -1 +-----+
     (-1,-1)   A_below = 1/2
```

1. **Geometric area of the part below the $x$-axis on $[-1, 0]$ ($A_{\text{below}}$):**
   - *By integration:* Since $x \le 0$ on $[-1, 0]$, the positive geometric area is:
     $$A_{\text{below}} = -\int_{-1}^0 x\,dx = -\left[\frac{x^2}{2}\right]_{-1}^0 = -\left(0 - \frac{(-1)^2}{2}\right) = \frac{1}{2} = 0.5.$$
   - *By elementary geometry:* The region on $[-1, 0]$ is a right triangle with base $b_1 = 1$ (from $x = -1$ to $x = 0$) and height $h_1 = |-1| = 1$:
     $$A_{\text{below}} = \frac{1}{2} \cdot b_1 \cdot h_1 = \frac{1}{2} \cdot 1 \cdot 1 = \frac{1}{2}.$$

2. **Geometric area of the part above the $x$-axis on $[0, 2]$ ($A_{\text{above}}$):**
   - *By integration:* Since $x \ge 0$ on $[0, 2]$, the geometric area equals the definite integral:
     $$A_{\text{above}} = \int_0^2 x\,dx = \left[\frac{x^2}{2}\right]_0^2 = \frac{2^2}{2} - 0 = 2.$$
   - *By elementary geometry:* The region on $[0, 2]$ is a right triangle with base $b_2 = 2$ (from $x = 0$ to $x = 2$) and height $h_2 = 2$:
     $$A_{\text{above}} = \frac{1}{2} \cdot b_2 \cdot h_2 = \frac{1}{2} \cdot 2 \cdot 2 = 2.$$

### Step 3: Explaining the Difference Between the Definite Integral and Geometric Area
Comparing the results:
- **Definite Integral (Net Signed Area):**
  $$\int_{-1}^2 x\,dx = \int_{-1}^0 x\,dx + \int_0^2 x\,dx = -\frac{1}{2} + 2 = A_{\text{above}} - A_{\text{below}} = 2 - \frac{1}{2} = \frac{3}{2} = 1.5.$$
  The definite integral measures the **net signed accumulation** of $f(x)$ over $[-1, 2]$. The negative contribution $-\frac{1}{2}$ from $[-1, 0]$ partially cancels the positive contribution $+2$ from $[0, 2]$.
- **Total Geometric Area:**
  $$A_{\text{total}} = \int_{-1}^2 |x|\,dx = A_{\text{above}} + A_{\text{below}} = 2 + \frac{1}{2} = \frac{5}{2} = 2.5.$$
  Geometric area measures the total two-dimensional surface enclosed between the curve and the $x$-axis regardless of whether the curve is above or below the axis, so both triangles add positively.

---

## 4. Verification and Consistency Checks

1. **Additivity Check:** Splitting the definite integral at the root $x = 0$ gives $\int_{-1}^0 x\,dx + \int_0^2 x\,dx = -\frac{1}{2} + 2 = \frac{3}{2}$, which agrees with the single-step evaluation $\left[\frac{x^2}{2}\right]_{-1}^2 = \frac{3}{2}$.
2. **Sign Error Check:** Note that $(-1)^2 = +1$, so at the lower limit $x = -1$ we have $F(-1) = \frac{(-1)^2}{2} = +\frac{1}{2}$, and $-F(-1) = -\frac{1}{2}$. If a student mistakenly wrote $(-1)^2 = -1$, they would get $2 - (-\frac{1}{2}) = \frac{5}{2}$, confusing the definite integral with the total unsigned area.
