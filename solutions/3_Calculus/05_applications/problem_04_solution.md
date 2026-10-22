# Solution to Problem 4: Area Between Curves

## 1. Problem Statement
Find the area of the region bounded by the graphs
$$
y=x
$$
and
$$
y=x^2.
$$

First find the intersection points and justify which function is greater on the relevant interval.

---

## 2. Theoretical Background and Concepts
Suppose $f(x)$ and $g(x)$ are continuous functions on a closed interval $[a, b]$.
1. **Intersection Points and Integration Limits**: The points where the graphs $y = f(x)$ and $y = g(x)$ intersect are found by solving the algebraic equation $f(x) = g(x)$. For a closed region bounded solely by these two curves, the $x$-coordinates of the intersection points define the interval of integration $[a, b]$.
2. **Vertical Slice (Riemann Sum) Construction and Function Ordering**:
   At each $x \in [a, b]$, a vertical strip of infinitesimal width $dx$ between the two curves has positive height equal to the vertical distance between the curves:
   $$
   h(x) = |f(x) - g(x)| = y_{\text{upper}}(x) - y_{\text{lower}}(x).
   $$
   If $f(x) \ge g(x)$ for all $x \in [a, b]$, then $y = f(x)$ is the **upper curve** and $y = g(x)$ is the **lower curve**, and the area $A$ of the bounded region is given by the definite integral:
   $$
   A = \int_a^b \left(f(x) - g(x)\right)\,dx.
   $$
   Determining which function is greater on $[a, b]$ before integrating ensures that the integrand $f(x) - g(x)$ is non-negative and that the resulting area is positive.

---

## 3. Detailed Step-by-Step Solution

### Choosing Variables and Mathematical Tool
- $x$: horizontal coordinate (independent variable).
- $f(x) = x$: linear function representing the straight line $y = x$.
- $g(x) = x^2$: quadratic function representing the parabola $y = x^2$.
- $A$: area of the planar region enclosed by the two curves (in square units).

Because the height of the region varies continuously with $x$, we use the **definite integral** to accumulate the areas of infinitesimal vertical strips across the region.

---

### Step 1: Finding the Intersection Points
The graphs of $y = x$ and $y = x^2$ intersect where their $y$-values are equal:
$$
x^2 = x \iff x^2 - x = 0 \iff x(x - 1) = 0.
$$
This gives two solutions for the $x$-coordinate:
$$
x_1 = 0 \quad \text{and} \quad x_2 = 1.
$$
Substituting back into $y = x$ yields the two intersection points in the plane:
$$
(0, 0) \quad \text{and} \quad (1, 1).
$$
Thus, the bounded region lies over the horizontal interval **$x \in [0, 1]$**.

---

### Step 2: Justifying Which Function Is Greater on $[0, 1]$
We compare $f(x) = x$ and $g(x) = x^2$ on the open interval $(0, 1)$ using two methods:

1. **Algebraic Factoring (Rigorous Proof for All $x \in (0, 1)$)**:
   Consider the difference between the two functions:
   $$
   f(x) - g(x) = x - x^2 = x(1 - x).
   $$
   For every $x \in (0, 1)$, we have $x > 0$ and $1 - x > 0$. Therefore, the product of these two positive factors is strictly positive:
   $$
   x(1 - x) > 0 \implies x > x^2 \quad \text{for all } x \in (0, 1).
   $$
   *(Equivalently, multiplying the inequality $x < 1$ by the positive number $x > 0$ preserves the inequality direction and yields $x^2 < x$.)*

2. **Test-Point Verification on $(0, 1)$**:
   Since $f(x) - g(x)$ is continuous and has no zeros inside $(0, 1)$, its sign is constant on $(0, 1)$. Evaluating at the midpoint $x = \frac{1}{2} \in (0, 1)$ gives:
   $$
   f\left(\frac{1}{2}\right) = \frac{1}{2} = 0.5, \qquad g\left(\frac{1}{2}\right) = \left(\frac{1}{2}\right)^2 = \frac{1}{4} = 0.25.
   $$
   Since $\frac{1}{2} > \frac{1}{4}$, the line **$y = x$ is the upper curve** and the parabola **$y = x^2$ is the lower curve** throughout $[0, 1]$.

```
    y ^
  1.0 +                   * (1,1)
      |                . /|
      |     y = x   .   / |
  0.5 +          .     /  |
      |       .  |    /   |  y = x^2
      |    .     |   /    |
  0.0 *----------+--------+---> x
     (0,0)      0.5      1.0
```

---

### Step 3: Setting Up and Computing the Area Integral
Since $x \ge x^2$ on $[0, 1]$, the area $A$ bounded by the two curves is:
$$
A = \int_0^1 \left(y_{\text{upper}} - y_{\text{lower}}\right)\,dx = \int_0^1 \left(x - x^2\right)\,dx.
$$
By the power rule for antiderivatives, an antiderivative of $x - x^2$ is $F(x) = \frac{x^2}{2} - \frac{x^3}{3}$. Applying the Fundamental Theorem of Calculus:
$$
\begin{aligned}
A &= \left[\frac{x^2}{2} - \frac{x^3}{3}\right]_0^1 \\
&= \left(\frac{1^2}{2} - \frac{1^3}{3}\right) - \left(\frac{0^2}{2} - \frac{0^3}{3}\right) \\
&= \frac{1}{2} - \frac{1}{3} = \frac{3 - 2}{6} = \frac{1}{6}.
\end{aligned}
$$
**Interpretation**: The exact area of the region enclosed between the line $y = x$ and the parabola $y = x^2$ is **$A = \frac{1}{6}$** square units (approximately $0.1667\text{ units}^2$).

---

## 4. Verification and Consistency Checks

1. **Geometric Bounding Box / Triangle Sanity Check**:
   - The region between $y = x$ and $y = x^2$ on $[0, 1]$ lies entirely inside the right triangle bounded by $y = x$, $y = 0$, and $x = 1$, whose area is:
     $$
     A_{\text{triangle}} = \frac{1}{2} \times \text{base} \times \text{height} = \frac{1}{2}(1)(1) = \frac{1}{2}.
     $$
   - The area under the parabola $y = x^2$ on $[0, 1]$ is $\int_0^1 x^2\,dx = \frac{1}{3}$.
   - Subtracting the area under the parabola from the area of the right triangle gives $\frac{1}{2} - \frac{1}{3} = \frac{1}{6} > 0$, which satisfies $0 < \frac{1}{6} < \frac{1}{2}$.

2. **Horizontal Slice Integration (Integrating with Respect to $y$)**:
   Solving the equations for $x$ in terms of $y$ on $y \in [0, 1]$ gives $x_{\text{left}} = y$ and $x_{\text{right}} = \sqrt{y}$ (since $\sqrt{y} \ge y$ on $[0, 1]$). Integrating horizontally:
   $$
   A = \int_0^1 \left(\sqrt{y} - y\right)\,dy = \left[\frac{2}{3}y^{3/2} - \frac{y^2}{2}\right]_0^1 = \frac{2}{3} - \frac{1}{2} = \frac{4 - 3}{6} = \frac{1}{6}.
   $$
   Both vertical and horizontal slicing yield the exact same area $A = \frac{1}{6}$.
