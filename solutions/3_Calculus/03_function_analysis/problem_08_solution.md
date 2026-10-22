# Solution to Problem 8: The Second Derivative

## 1. Problem Statement
For
$$f(x)=x^4-4x^2$$
find the local extrema, intervals of convexity and concavity, and inflection points. Sketch the graph and mark all the identified features on it.

> **Why this problem:** it introduces the second derivative as a tool for describing the curvature of a graph.

---

## 2. Theoretical Background and Concepts
For a twice-differentiable function $f: \mathbb{R} \to \mathbb{R}$:
1. **First Derivative and Local Extrema:** Critical points satisfy $f'(x) = 0$. Sign changes of $f'(x)$ (or the sign of $f''(x_0) \neq 0$ at a critical point $x_0$) classify local maxima and minima.
2. **Second Derivative, Convexity, and Concavity:**
   - If $f''(x) > 0$ on an open interval $I$, then $f'(x)$ is strictly increasing on $I$, and $f$ is **strictly convex** (concave upward, $\cup$) on $I$.
   - If $f''(x) < 0$ on an open interval $I$, then $f'(x)$ is strictly decreasing on $I$, and $f$ is **strictly concave** (concave downward, $\cap$) on $I$.
3. **Inflection Points:** A point $(x_0, f(x_0))$ is an **inflection point** if $f$ is continuous at $x_0$ and $f''(x)$ changes sign as $x$ passes through $x_0$ (meaning the graph switches between convex and concave).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Domain, Symmetry, Zeros, and End Behavior
- **Domain:** $D_f = \mathbb{R}$.
- **Symmetry:** $f(-x) = (-x)^4 - 4(-x)^2 = x^4 - 4x^2 = f(x)$, so $f$ is an **even function** (symmetric about the $y$-axis).
- **Zeros ($x$-intercepts):** Factoring $f(x)$ gives:
  $$f(x) = x^2(x^2 - 4) = x^2(x - 2)(x + 2) = 0 \iff x = -2, \quad x = 0 \text{ (double root)}, \quad x = 2.$$
- **Limits at Infinity:** $\lim_{x \to \pm\infty} (x^4 - 4x^2) = +\infty$.

### Step 2: First Derivative, Monotonicity, and Local Extrema
Differentiating $f(x) = x^4 - 4x^2$:
$$f'(x) = 4x^3 - 8x = 4x(x^2 - 2) = 4x(x - \sqrt{2})(x + \sqrt{2}).$$
Setting $f'(x) = 0$ yields three critical points:
$$x_1 = -\sqrt{2} \approx -1.414, \qquad x_2 = 0, \qquad x_3 = \sqrt{2} \approx 1.414.$$

| Interval / Point | $(-\infty, -\sqrt{2})$ | $x = -\sqrt{2}$ | $(-\sqrt{2}, 0)$ | $x = 0$ | $(0, \sqrt{2})$ | $x = \sqrt{2}$ | $(\sqrt{2}, \infty)$ |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Sign of $f'(x)$** | $-$ | $0$ | $+$ | $0$ | $-$ | $0$ | $+$ |
| **Behavior of $f(x)$** | $\searrow$ | **Local/Global Min** ($-4$) | $\nearrow$ | **Local Max** ($0$) | $\searrow$ | **Local/Global Min** ($-4$) | $\nearrow$ |

- **Monotonicity:**
  - Strictly decreasing on $(-\infty, -\sqrt{2}]$ and on $[0, \sqrt{2}]$.
  - Strictly increasing on $[-\sqrt{2}, 0]$ and on $[\sqrt{2}, \infty)$.
- **Local Extrema:**
  - **Local (and Global) Minima** at $x = -\sqrt{2}$ and $x = \sqrt{2}$:
    $$f(\pm\sqrt{2}) = (\pm\sqrt{2})^4 - 4(\pm\sqrt{2})^2 = 4 - 8 = -4 \quad \longrightarrow \quad (-\sqrt{2}, -4) \text{ and } (\sqrt{2}, -4).$$
  - **Local Maximum** at $x = 0$:
    $$f(0) = 0 \quad \longrightarrow \quad (0, 0).$$

### Step 3: Second Derivative, Convexity/Concavity, and Inflection Points
Differentiating $f'(x) = 4x^3 - 8x$:
$$f''(x) = 12x^2 - 8 = 4(3x^2 - 2).$$
Setting $f''(x) = 0$:
$$3x^2 - 2 = 0 \iff x^2 = \frac{2}{3} \iff x = \pm\sqrt{\frac{2}{3}} = \pm\frac{\sqrt{6}}{3} \approx \pm 0.816.$$

We analyze the sign of the upward-opening quadratic $f''(x) = 12x^2 - 8$:

| Interval / Point | $\left(-\infty, -\sqrt{\frac{2}{3}}\right)$ | $x = -\sqrt{\frac{2}{3}}$ | $\left(-\sqrt{\frac{2}{3}}, \sqrt{\frac{2}{3}}\right)$ | $x = \sqrt{\frac{2}{3}}$ | $\left(\sqrt{\frac{2}{3}}, \infty\right)$ |
| :---: | :---: | :---: | :---: | :---: | :---: |
| **Sign of $f''(x)$** | $+$ | $0$ | $-$ | $0$ | $+$ |
| **Curvature of $f(x)$** | $\cup$ (Convex) | **Inflection Point** | $\cap$ (Concave) | **Inflection Point** | $\cup$ (Convex) |

- **Intervals of Convexity and Concavity:**
  - $f$ is **strictly convex** ($\cup$, $f''(x) > 0$) on $\left(-\infty, -\sqrt{\frac{2}{3}}\right]$ and on $\left[\sqrt{\frac{2}{3}}, \infty\right)$.
  - $f$ is **strictly concave** ($\cap$, $f''(x) < 0$) on $\left[-\sqrt{\frac{2}{3}}, \sqrt{\frac{2}{3}}\right]$.
- **Inflection Points:** Because $f''(x)$ changes sign at both $x = -\sqrt{\frac{2}{3}}$ and $x = \sqrt{\frac{2}{3}}$, we evaluate $f$ at these points:
  $$f\left(\pm\sqrt{\frac{2}{3}}\right) = \left(\frac{2}{3}\right)^2 - 4\left(\frac{2}{3}\right) = \frac{4}{9} - \frac{24}{9} = -\frac{20}{9} \approx -2.222.$$
  Thus, the two **inflection points** are:
  $$I_1 = \left(-\sqrt{\frac{2}{3}}, -\frac{20}{9}\right) \quad \text{and} \quad I_2 = \left(\sqrt{\frac{2}{3}}, -\frac{20}{9}\right).$$

### Step 4: Graph Sketch
Below is a symmetric W-shaped coordinate sketch of $f(x) = x^4 - 4x^2$. Notice that the local maximum and double root $(0, 0)$ lies directly at the intersection of the vertical $y$-axis (`|`) and horizontal $x$-axis (`-`), the roots $(-2, 0)$ and $(2, 0)$ lie on the $x$-axis (`-`), the inflection points $I_1, I_2$ lie at $y = -20/9$, and the global minima $(-\sqrt{2}, -4)$ and $(\sqrt{2}, -4)$ lie symmetrically at the bottom of the two troughs:

```text
                            y
                            ^
       \                    |                    /
        \                   |                   /
         \  (-2,0)          |(0,0)      (2,0)  /
      ----*-----------------*-----------------*----> x
           \              . | .              /
            \           .   |   .           /
             \   I1   .     |     .   I2   /
              \   o .       |       . o   /    <-- Inflection pts (-sqrt(2/3), -20/9)
               \ .          |          . /         and (+sqrt(2/3), -20/9)
                *           |           *
        (-sqrt(2), -4)      |      (sqrt(2), -4)
```

---

## 4. Verification and Consistency Checks
1. **Second Derivative Test at Critical Points:**
   - $f''(0) = -8 < 0 \implies (0, 0)$ is a strict local maximum (in the concave region).
   - $f''(\pm\sqrt{2}) = 12(2) - 8 = 16 > 0 \implies (\pm\sqrt{2}, -4)$ are strict local minima (in the convex regions).
2. **Ordering of $x$-Coordinates:**
   $$0 < \sqrt{\frac{2}{3}} \approx 0.816 < \sqrt{2} \approx 1.414 < 2,$$
   and correspondingly for the $y$-values on $[0, \sqrt{2}]$:
   $$f(0) = 0 > f\left(\sqrt{\frac{2}{3}}\right) = -\frac{20}{9} > f(\sqrt{2}) = -4,$$
   confirming that each inflection point lies strictly between the central local maximum $(0, 0)$ and the adjacent local minimum $(\pm\sqrt{2}, -4)$.
