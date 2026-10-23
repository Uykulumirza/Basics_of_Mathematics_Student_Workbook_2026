# Solution to Problem 10: Complete Function Analysis

## 1. Problem Statement
Perform a complete analysis of
$$f(x)=\frac{x}{x^2+1}.$$
Include the domain, symmetry, zeros, limits, monotonicity, extrema, and convexity. Finally, produce a sketch based only on this information.

> **Why this problem:** it combines all the basic elements of function analysis into one organized process.

---

## 2. Theoretical Background and Concepts
A complete analysis (curve sketching) of a smooth function $f$ follows a systematic 7-step protocol:
1. **Domain and Continuity:** Identify where $f(x)$ is defined and continuous.
2. **Symmetry and Periodicity:** Check parity ($f(-x) = f(x)$ even vs. $f(-x) = -f(x)$ odd).
3. **Intercepts and Sign:** Find zeros ($f(x) = 0$), $y$-intercept ($f(0)$), and intervals of positive/negative sign.
4. **Limits and Asymptotes:** Check vertical, horizontal, and oblique asymptotes.
5. **First Derivative ($f'$):** Find critical points, intervals of monotonicity, and local/global extrema.
6. **Second Derivative ($f''$):** Find intervals of convexity ($\cup$), concavity ($\cap$), and inflection points.
7. **Graph Synthesis:** Combine all features into an accurate coordinate sketch.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Domain and Continuity
Since $x^2 + 1 \ge 1 > 0$ for all $x \in \mathbb{R}$, the denominator never vanishes. Thus:
$$D_f = \mathbb{R} = (-\infty, \infty),$$
and $f$ is continuous and infinitely differentiable on all of $\mathbb{R}$.

### Step 2: Symmetry
For every $x \in \mathbb{R}$:
$$f(-x) = \frac{-x}{(-x)^2 + 1} = -\frac{x}{x^2 + 1} = -f(x).$$
Therefore, $f$ is an **odd function**, and its graph is symmetric with respect to the origin $(0, 0)$.

### Step 3: Zeros, Intercepts, and Sign of $f(x)$
- **Zeros and $y$-intercept:** $f(x) = 0 \iff \frac{x}{x^2 + 1} = 0 \iff x = 0$. The origin **$(0, 0)$** is the unique $x$- and $y$-intercept.
- **Sign of $f(x)$:** Because $x^2 + 1 > 0$ everywhere, the sign of $f(x)$ matches the sign of $x$:
  - $f(x) < 0$ on $(-\infty, 0)$,
  - $f(0) = 0$,
  - $f(x) > 0$ on $(0, \infty)$.

### Step 4: Limits and Asymptotes
- **Vertical Asymptotes:** None, because $D_f = \mathbb{R}$.
- **Horizontal Asymptote:** Taking limits as $x \to \pm\infty$:
  $$\lim_{x \to -\infty} \frac{x}{x^2 + 1} = \lim_{x \to -\infty} \frac{\frac{1}{x}}{1 + \frac{1}{x^2}} = 0^-, \qquad \lim_{x \to +\infty} \frac{x}{x^2 + 1} = \lim_{x \to +\infty} \frac{\frac{1}{x}}{1 + \frac{1}{x^2}} = 0^+.$$
  Hence, the line **$y = 0$** (the $x$-axis) is a two-sided **horizontal asymptote** (approached from below as $x \to -\infty$ and from above as $x \to +\infty$). There are no oblique asymptotes.

### Step 5: First Derivative, Monotonicity, and Extrema
Applying the quotient rule:
$$f'(x) = \frac{1 \cdot (x^2 + 1) - x \cdot (2x)}{(x^2 + 1)^2} = \frac{1 - x^2}{(x^2 + 1)^2} = \frac{(1 - x)(1 + x)}{(x^2 + 1)^2}.$$
- **Critical points:** $f'(x) = 0 \iff 1 - x^2 = 0 \iff x = -1 \text{ or } x = 1$.
- **Sign of $f'(x)$:** Since $(x^2 + 1)^2 > 0$, the sign of $f'(x)$ is determined by $1 - x^2$:

| Interval / Point | $(-\infty, -1)$ | $x = -1$ | $(-1, 1)$ | $x = 1$ | $(1, \infty)$ |
| :---: | :---: | :---: | :---: | :---: | :---: |
| **Sign of $f'(x)$** | $-$ | $0$ | $+$ | $0$ | $-$ |
| **Behavior of $f(x)$** | $\searrow$ ($0^-$ to $-1/2$) | **Global Min** ($-1/2$) | $\nearrow$ ($-1/2$ to $1/2$) | **Global Max** ($1/2$) | $\searrow$ ($1/2$ to $0^+$) |

- **Monotonicity:**
  - $f$ is **strictly decreasing** on $(-\infty, -1]$ and on $[1, \infty)$.
  - $f$ is **strictly increasing** on $[-1, 1]$.
- **Extrema:**
  - **Local and Global Minimum** at $x = -1$: $f_{\min} = f(-1) = -\frac{1}{2} \longrightarrow \left(-1, -\frac{1}{2}\right)$.
  - **Local and Global Maximum** at $x = 1$: $f_{\max} = f(1) = \frac{1}{2} \longrightarrow \left(1, \frac{1}{2}\right)$.
  (Thus, the range of $f$ is $\left[-\frac{1}{2}, \frac{1}{2}\right]$.)

### Step 6: Second Derivative, Convexity, and Inflection Points
Differentiating $f'(x) = \frac{1 - x^2}{(x^2 + 1)^2}$ via the quotient rule:
$$f''(x) = \frac{(-2x)(x^2 + 1)^2 - (1 - x^2) \cdot 2(x^2 + 1)(2x)}{(x^2 + 1)^4} = \frac{-2x(x^2 + 1) - 4x(1 - x^2)}{(x^2 + 1)^3} = \frac{2x^3 - 6x}{(x^2 + 1)^3} = \frac{2x(x^2 - 3)}{(x^2 + 1)^3}.$$
- **Potential inflection points:** $f''(x) = 0 \iff 2x(x - \sqrt{3})(x + \sqrt{3}) = 0 \iff x = -\sqrt{3}, \; 0, \; \sqrt{3}$ (where $\sqrt{3} \approx 1.732$).
- **Sign of $f''(x)$:** Since $(x^2 + 1)^3 > 0$, the sign of $f''(x)$ matches the cubic $2x(x^2 - 3)$:

| Interval / Point | $(-\infty, -\sqrt{3})$ | $x = -\sqrt{3}$ | $(-\sqrt{3}, 0)$ | $x = 0$ | $(0, \sqrt{3})$ | $x = \sqrt{3}$ | $(\sqrt{3}, \infty)$ |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Sign of $f''(x)$** | $-$ | $0$ | $+$ | $0$ | $-$ | $0$ | $+$ |
| **Curvature of $f(x)$** | $\cap$ (Concave) | **Inflection** | $\cup$ (Convex) | **Inflection** | $\cap$ (Concave) | **Inflection** | $\cup$ (Convex) |

- **Convexity and Concavity:**
  - $f$ is **strictly concave** ($\cap$) on $(-\infty, -\sqrt{3}]$ and on $[0, \sqrt{3}]$.
  - $f$ is **strictly convex** ($\cup$) on $[-\sqrt{3}, 0]$ and on $[\sqrt{3}, \infty)$.
- **Three Inflection Points:**
  $$\left(-\sqrt{3}, -\frac{\sqrt{3}}{4}\right) \approx (-1.732, -0.433), \qquad (0, 0), \qquad \left(\sqrt{3}, \frac{\sqrt{3}}{4}\right) \approx (1.732, 0.433).$$

### Step 7: Graph Sketch
Below is an accurately aligned coordinate sketch showing the origin $(0,0)$ at the intersection of `|` and `-`, the global minimum $(-1, -1/2)$, the global maximum $(1, 1/2)$, the inflection points at $x = \pm\sqrt{3}, 0$, and the horizontal asymptote $y = 0$:

```text
                               y
                               ^
                               |       (1, 1/2)
                               |         *
                               |      .     .    I3(sqrt(3), sqrt(3)/4)
                               |    .         o
                               |  .             ' . . . (stays > 0, y -> 0+)
      -------------------------*-----------------------------> x
      (y -> 0-) . . . '        |(0,0)
                  o         .  |
     I1(-sqrt(3),-sqrt(3)/4)   |
                    .     .    |
                       *       |
                  (-1, -1/2)   |
```

---

## 4. Verification and Consistency Checks
1. **AM-GM Inequality Bound:** For $x > 0$, $x^2 + 1 \ge 2x \implies 0 < \frac{x}{x^2 + 1} \le \frac{1}{2}$ with equality iff $x = 1$. By odd symmetry, $-\frac{1}{2} \le f(x) \le \frac{1}{2}$ for all $x \in \mathbb{R}$, confirming our global extrema $(\pm 1, \pm 1/2)$.
2. **Odd Symmetry of Derivatives:** Since $f(x)$ is odd, $f'(x) = \frac{1-x^2}{(x^2+1)^2}$ is **even** (extrema at symmetric points $x = \pm 1$) and $f''(x) = \frac{2x(x^2-3)}{(x^2+1)^3}$ is **odd** (inflection points symmetric about $0$ at $x = 0, \pm\sqrt{3}$).
