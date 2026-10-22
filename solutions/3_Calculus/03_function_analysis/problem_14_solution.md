# Solution to Problem 14: Reconstructing Information from the Derivative

## 1. Problem Statement
It is known that
$$f'(x)=(x-1)(x+2).$$
Determine the monotonicity and the locations of the extrema, and sketch a possible qualitative shape of the function. Then, for
$$g(x)=\frac{x^3}{3}+\frac{x^2}{2}-2x$$
verify that $g'(x)=(x-1)(x+2)$, and compare the specific graph with the earlier qualitative sketch.

> **Why this problem:** it teaches how to read the behavior of a function directly from its derivative.

---

## 2. Theoretical Background and Concepts
1. **Reading Behavior Directly from $f'(x)$:** Even without an explicit formula for $f(x)$, knowing $f'(x)$ on $\mathbb{R}$ completely determines:
   - The critical points ($f'(x) = 0$),
   - The intervals of monotonicity (where $f'(x) > 0$ vs. $f'(x) < 0$),
   - The $x$-coordinates and types (maximum vs. minimum) of all local extrema, and
   - The intervals of convexity/concavity and $x$-coordinate of the inflection point (from $f''(x) = (f'(x))'$).
2. **Antiderivatives Differ by a Constant:** By the Mean Value Theorem, if $f'(x) = g'(x)$ for all $x \in \mathbb{R}$, then $f(x) = g(x) + C$ for some constant $C \in \mathbb{R}$. Geometrically, the graphs of all such functions $f$ are **vertical translations** of the graph of $g$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Monotonicity and Extrema Locations from $f'(x) = (x - 1)(x + 2)$
The derivative $f'(x) = (x - 1)(x + 2) = x^2 + x - 2$ is defined for all $x \in \mathbb{R}$, so $f$ is differentiable (and hence continuous) on $\mathbb{R}$.
- **Critical points:** Solving $f'(x) = 0$:
  $$(x - 1)(x + 2) = 0 \iff x_1 = -2 \quad \text{or} \quad x_2 = 1.$$
- **Sign chart of $f'(x)$:** Because $f'(x) = x^2 + x - 2$ is a quadratic with a positive leading coefficient ($+1 > 0$), its parabola opens upward—it is positive outside the roots and negative between them:

| Interval / Point | $(-\infty, -2)$ | $x = -2$ | $(-2, 1)$ | $x = 1$ | $(1, \infty)$ |
| :---: | :---: | :---: | :---: | :---: | :---: |
| Sign of $(x + 2)$ | $-$ | $0$ | $+$ | $+$ | $+$ |
| Sign of $(x - 1)$ | $-$ | $-$ | $-$ | $0$ | $+$ |
| **Sign of $f'(x)$** | **$+$** | **$0$** | **$-$** | **$0$** | **$+$** |
| **Behavior of $f(x)$** | $\nearrow$ (strictly increasing) | **Local Maximum** | $\searrow$ (strictly decreasing) | **Local Minimum** | $\nearrow$ (strictly increasing) |

- **Intervals of Monotonicity:**
  - $f$ is **strictly increasing** on $(-\infty, -2]$ and on $[1, \infty)$.
  - $f$ is **strictly decreasing** on $[-2, 1]$.
- **Locations of Local Extrema:**
  - **Local Maximum** at **$x = -2$** (since $f'$ changes sign from $+$ to $-$).
  - **Local Minimum** at **$x = 1$** (since $f'$ changes sign from $-$ to $+$).
- **Inflection Point Location:** Differentiating $f'(x) = x^2 + x - 2$ gives $f''(x) = 2x + 1 = 0 \iff x = -\frac{1}{2}$ (the midpoint between $-2$ and $1$). Thus $f$ is concave ($\cap$) on $\left(-\infty, -\frac{1}{2}\right]$ and convex ($\cup$) on $\left[-\frac{1}{2}, \infty\right)$.

### Step 2: Verification for $g(x) = \frac{x^3}{3} + \frac{x^2}{2} - 2x$
Differentiating $g(x)$ term by term using the power rule:
$$g'(x) = \frac{d}{dx}\left(\frac{x^3}{3} + \frac{x^2}{2} - 2x\right) = \frac{3x^2}{3} + \frac{2x}{2} - 2 = x^2 + x - 2.$$
Factoring the quadratic trinomial:
$$g'(x) = x^2 + 2x - x - 2 = x(x + 2) - 1(x + 2) = (x - 1)(x + 2).$$
This confirms that $g'(x) = f'(x)$ for all $x \in \mathbb{R}$.

### Step 3: Exact Values for $g(x)$ and Comparison with the General Qualitative Sketch
Evaluating $g(x) = \frac{x^3}{3} + \frac{x^2}{2} - 2x$ at the key points fixes the vertical position of the curve:
- **Local Maximum at $x = -2$:**
  $$g(-2) = \frac{(-2)^3}{3} + \frac{(-2)^2}{2} - 2(-2) = -\frac{8}{3} + 2 + 4 = \frac{10}{3} \approx 3.333 \quad \longrightarrow \quad \left(-2, \frac{10}{3}\right).$$
- **Inflection Point at $x = -\frac{1}{2}$:**
  $$g\left(-\frac{1}{2}\right) = \frac{-1/8}{3} + \frac{1/4}{2} - 2\left(-\frac{1}{2}\right) = -\frac{1}{24} + \frac{3}{24} + 1 = \frac{13}{12} \approx 1.083 \quad \longrightarrow \quad \left(-\frac{1}{2}, \frac{13}{12}\right).$$
- **Origin Intercept at $x = 0$:**
  $$g(0) = 0 \quad \longrightarrow \quad (0, 0).$$
- **Local Minimum at $x = 1$:**
  $$g(1) = \frac{1}{3} + \frac{1}{2} - 2 = \frac{2 + 3 - 12}{6} = -\frac{7}{6} \approx -1.167 \quad \longrightarrow \quad \left(1, -\frac{7}{6}\right).$$

**Comparison between the qualitative sketch of $f(x)$ and the specific graph of $g(x)$:**
- Because $f'(x) = g'(x)$, every possible function $f(x)$ satisfies $f(x) = g(x) + C$ for an arbitrary real constant $C = f(0)$.
- **What is identical for all $f$ and $g$:** The $x$-coordinates of the local maximum ($x = -2$), the inflection point ($x = -1/2$), and the local minimum ($x = 1$); the intervals of monotonicity and convexity; and even the **vertical drop** between the local maximum and local minimum:
  $$f(-2) - f(1) = g(-2) - g(1) = \frac{10}{3} - \left(-\frac{7}{6}\right) = \frac{27}{6} = \frac{9}{2} = 4.5.$$
- **What differs:** Only the vertical placement ($y$-coordinates and $x$-intercepts). Choosing $g(x)$ corresponds to setting the integration constant $C = 0$, which anchors the curve so that it passes directly through the origin $(0, 0)$.

```text
                              y   Graph of g(x) = x^3/3 + x^2/2 - 2x
                              ^   (and qualitative shape of f(x) = g(x) + C)
            (-2, 10/3)        |
                 *            |                  /
              .     .         |                 /
            .         .       |                /
           /            o (-1/2, 13/12)       /
          /               .   |              /
      ---*--------------------*-------------*---------> x
        /                     |(0,0)       /
       /                      |  .       .
      /                       |     * (1, -7/6)
```

---

## 4. Verification and Consistency Checks
1. **Second Derivative Check:** $g''(x) = 2x + 1 \implies g''(-2) = -3 < 0$ (local maximum) and $g''(1) = 3 > 0$ (local minimum).
2. **Fundamental Theorem of Calculus Check:** The net change of any antiderivative $f$ from $x = -2$ to $x = 1$ is $\int_{-2}^1 (x^2 + x - 2)\,dx = \left[\frac{x^3}{3} + \frac{x^2}{2} - 2x\right]_{-2}^1 = -\frac{7}{6} - \frac{10}{3} = -\frac{9}{2}$, matching $g(1) - g(-2) = -4.5$.
