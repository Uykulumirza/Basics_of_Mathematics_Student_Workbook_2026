# Solution to Problem 1: A Cubic Polynomial

## 1. Problem Statement
Analyze the monotonicity and extrema of
$$f(x)=x^3-3x^2+2.$$
Sketch the graph based on the results and mark the critical points.

> **Why this problem:** it teaches how to use the first derivative to describe the shape of a polynomial.

---

## 2. Theoretical Background and Concepts
To analyze the monotonicity and local extrema of a differentiable function $f: \mathbb{R} \to \mathbb{R}$:
1. **Domain and Continuity:** Every polynomial is defined, continuous, and infinitely differentiable on the entire real line $\mathbb{R}$.
2. **Critical Points:** By Fermat's Theorem on stationary points, if $f$ has a local extremum at an interior point $x_0$ where $f$ is differentiable, then $f'(x_0) = 0$. The solutions to $f'(x) = 0$ are the **stationary (critical) points**.
3. **Monotonicity Criterion:** On any interval $I \subseteq \mathbb{R}$:
   - If $f'(x) > 0$ for all interior points of $I$, then $f$ is **strictly increasing** on $I$.
   - If $f'(x) < 0$ for all interior points of $I$, then $f$ is **strictly decreasing** on $I$.
4. **First Derivative Test for Local Extrema:**
   - If $f'(x)$ changes sign from positive ($+$) to negative ($-$) as $x$ passes through $x_0$ from left to right, then $f$ has a **strict local maximum** at $x_0$.
   - If $f'(x)$ changes sign from negative ($-$) to positive ($+$) as $x$ passes through $x_0$ from left to right, then $f$ has a **strict local minimum** at $x_0$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Domain and End Behavior
- **Domain:** $D_f = \mathbb{R} = (-\infty, \infty)$.
- **Limits at Infinity:** Since the leading term is $x^3$ with a positive leading coefficient ($+1$):
  $$\lim_{x \to -\infty} (x^3 - 3x^2 + 2) = -\infty, \qquad \lim_{x \to +\infty} (x^3 - 3x^2 + 2) = +\infty.$$

### Step 2: First Derivative and Critical Points
Differentiating $f(x) = x^3 - 3x^2 + 2$ term by term yields:
$$f'(x) = 3x^2 - 6x = 3x(x - 2).$$
To find the critical points, we solve $f'(x) = 0$:
$$3x(x - 2) = 0 \iff x_1 = 0 \quad \text{or} \quad x_2 = 2.$$
Thus, the critical points are $x = 0$ and $x = 2$.

### Step 3: Sign Analysis of $f'(x)$ and Monotonicity
The critical points $x = 0$ and $x = 2$ partition $\mathbb{R}$ into three intervals: $(-\infty, 0)$, $(0, 2)$, and $(2, \infty)$. Because $f'(x) = 3x(x-2)$ is a quadratic function with a positive leading coefficient ($3 > 0$), its parabola opens upward:

| Interval / Point | $(-\infty, 0)$ | $x = 0$ | $(0, 2)$ | $x = 2$ | $(2, \infty)$ |
| :---: | :---: | :---: | :---: | :---: | :---: |
| Sign of $3x$ | $-$ | $0$ | $+$ | $+$ | $+$ |
| Sign of $(x - 2)$ | $-$ | $-$ | $-$ | $0$ | $+$ |
| **Sign of $f'(x)$** | **$+$** | **$0$** | **$-$** | **$0$** | **$+$** |
| **Behavior of $f(x)$** | $\nearrow$ ( strictly increasing ) | **Local Max** ($2$) | $\searrow$ ( strictly decreasing ) | **Local Min** ($-2$) | $\nearrow$ ( strictly increasing ) |

By continuity of $f(x)$ at the endpoints $x = 0$ and $x = 2$:
- $f$ is **strictly increasing** on $(-\infty, 0]$ and on $[2, \infty)$.
- $f$ is **strictly decreasing** on $[0, 2]$.

### Step 4: Local Extrema and Key Points for Sketching
Evaluating $f(x)$ at the critical points:
- At $x = 0$: $f'(x)$ changes sign from $+$ to $-$, so $f$ attains a **local maximum**:
  $$f_{\max} = f(0) = 0^3 - 3(0)^2 + 2 = 2 \quad \longrightarrow \quad \text{Point } (0, 2).$$
- At $x = 2$: $f'(x)$ changes sign from $-$ to $+$, so $f$ attains a **local minimum**:
  $$f_{\min} = f(2) = 2^3 - 3(2)^2 + 2 = 8 - 12 + 2 = -2 \quad \longrightarrow \quad \text{Point } (2, -2).$$

**Additional Features (Inflection Point and Zeros):**
- **Second Derivative & Inflection Point:** $f''(x) = 6x - 6 = 6(x - 1)$. Setting $f''(x) = 0$ gives $x = 1$, where $f''(x)$ changes sign from $-$ (concave on $(-\infty, 1)$) to $+$ (convex on $(1, \infty)$). Thus $(1, f(1)) = (1, 0)$ is the **inflection point** and the center of point symmetry of the cubic.
- **Zeros ($x$-intercepts):** Since $f(1) = 1 - 3 + 2 = 0$, we factor $f(x)$ by dividing by $(x - 1)$:
  $$x^3 - 3x^2 + 2 = (x - 1)(x^2 - 2x - 2) = 0.$$
  Solving $x^2 - 2x - 2 = 0$ gives $x = 1 \pm \sqrt{3}$. Hence the three real roots are:
  $$x \approx -0.732 \quad (1 - \sqrt{3}), \qquad x = 1, \qquad x \approx 2.732 \quad (1 + \sqrt{3}).$$

### Step 5: Graph Sketch
Below is an accurately aligned coordinate sketch of $f(x) = x^3 - 3x^2 + 2$, showing the local maximum $(0, 2)$ directly on the $y$-axis (`|`), the roots $(1-\sqrt{3}, 0)$, $(1, 0)$, and $(1+\sqrt{3}, 0)$ directly on the $x$-axis (`-`), and the local minimum $(2, -2)$ in Quadrant IV:

```text
                      y
                      ^
                      |                /
                      |               /
              (0,2)   *              /
                    . | .           /
                  .   |   .        /
                .     |     .     /
      ---------*------+------*---*---------> x
              /       |    (1,0)  \ (1+sqrt(3),0)
     (1-sqrt(3),0)    |        .   .
            /         |          . .
           /          |            * (2,-2)
          /           |
```

---

## 4. Verification and Consistency Checks
1. **Second Derivative Test at Critical Points:**
   - $f''(0) = 6(0) - 6 = -6 < 0 \implies x = 0$ is indeed a strict local maximum.
   - $f''(2) = 6(2) - 6 = +6 > 0 \implies x = 2$ is indeed a strict local minimum.
2. **Test Point Check for $f'(x)$:**
   - $x = -1 \in (-\infty, 0) \implies f'(-1) = 3(-1)(-3) = +9 > 0$ (increasing).
   - $x = 1 \in (0, 2) \implies f'(1) = 3(1)(-1) = -3 < 0$ (decreasing).
   - $x = 3 \in (2, \infty) \implies f'(3) = 3(3)(1) = +9 > 0$ (increasing).
3. **Intermediate Value Theorem Consistency:** Since $f(0) = 2 > 0$ and $f(2) = -2 < 0$, while $\lim_{x\to-\infty} f(x) = -\infty$ and $\lim_{x\to+\infty} f(x) = +\infty$, the continuous function $f$ must cross the $x$-axis exactly once in $(-\infty, 0)$, once in $(0, 2)$, and once in $(2, \infty)$, matching our roots $1-\sqrt{3} \in (-\infty, 0)$, $1 \in (0, 2)$, and $1+\sqrt{3} \in (2, \infty)$.
