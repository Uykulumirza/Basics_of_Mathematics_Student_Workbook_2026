# Solution to Problem 12: A Function with an Absolute Value

## 1. Problem Statement
Analyze
$$f(x)=|x^2-4|.$$
First sketch $x^2-4$, then explain the effect of the absolute value. Indicate the points where the derivative does not exist and justify the reason geometrically.

> **Why this problem:** it shows the limits of mechanical application of calculus and the importance of the geometry of the graph.

---

## 2. Theoretical Background and Concepts
1. **Piecewise Definition of $|g(x)|$:** For any real-valued function $g(x)$,
   $$|g(x)| = \begin{cases} g(x), & \text{if } g(x) \ge 0, \\ -g(x), & \text{if } g(x) < 0. \end{cases}$$
   Geometrically, the graph of $y = |g(x)|$ is obtained from $y = g(x)$ by keeping all points on or above the $x$-axis unchanged and **reflecting all portions below the $x$-axis upward across the $x$-axis**.
2. **Non-Differentiability at Simple Zeros (Corners):** A function $f$ is differentiable at $x_0$ if and only if its left-hand derivative $f'_-(x_0)$ and right-hand derivative $f'_+(x_0)$ both exist, are finite, and are equal. If $g(x_0) = 0$ and $g'(x_0) \neq 0$, then $|g(x)|$ has one-sided derivatives of opposite signs ($\pm g'(x_0)$) at $x_0$, forming a **sharp corner (angular point)** where the derivative does not exist.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Analysis and Sketch of the Base Parabola $g(x) = x^2 - 4$
The inner function $g(x) = x^2 - 4 = (x - 2)(x + 2)$ is an even upward-opening parabola with:
- **Zeros ($x$-intercepts):** $x = -2$ and $x = 2$,
- **Vertex (global minimum):** $(0, -4)$ on the negative $y$-axis,
- **Sign:** $g(x) \ge 0$ on $(-\infty, -2] \cup [2, \infty)$, and $g(x) < 0$ on $(-2, 2)$.

```text
                      y   Graph of g(x) = x^2 - 4
                      ^
       \              |              /
        \             |             /
         \  (-2,0)    |    (2,0)   /
      ----*-----------+-----------*----> x
           \          |          /
            \         |         /
             \        |        /
              ' .     |     . '
                  ' - * - ' (0,-4)
```

### Step 2: Effect of the Absolute Value and Piecewise Formula for $f(x) = |x^2 - 4|$
Applying the absolute value leaves the outer branches $(-\infty, -2] \cup [2, \infty)$ unchanged, because $x^2 - 4 \ge 0$ there, and **reflects the middle arc on $(-2, 2)$ (where $x^2 - 4 < 0$) across the $x$-axis**, turning the vertex $(0, -4)$ into a local maximum at $(0, +4)$:
$$f(x) = |x^2 - 4| = \begin{cases} x^2 - 4, & \text{for } x \in (-\infty, -2] \cup [2, \infty), \\ 4 - x^2, & \text{for } x \in (-2, 2). \end{cases}$$

```text
                      y   Graph of f(x) = |x^2 - 4|
                      ^
       \              |              /
        \         . - * - . (0,4)   /
         \      /     |     \      /
          \    /      |      \    /
           \  /       |       \  /
      ------*---------+---------*------> x
          (-2,0)      |(0,0)  (2,0)
           Corner     |       Corner
```

### Step 3: Differentiability and Points Where the Derivative Does Not Exist
1. **On the open intervals $(-\infty, -2) \cup (2, \infty)$ and $(-2, 2)$:**
   $$f'(x) = \begin{cases} 2x, & \text{for } x \in (-\infty, -2) \cup (2, \infty), \\ -2x, & \text{for } x \in (-2, 2). \end{cases}$$
   In particular, at $x = 0 \in (-2, 2)$, $f$ is differentiable with $f'(0) = 0$.

2. **At the transition points $x = -2$ and $x = 2$ (One-Sided Derivatives):**
   - **At $x = -2$:**
     $$f'_-(-2) = \lim_{h \to 0^-} \frac{((-2+h)^2 - 4) - 0}{h} = \lim_{h \to 0^-} (-4 + h) = -4,$$
     $$f'_+(-2) = \lim_{h \to 0^+} \frac{(4 - (-2+h)^2) - 0}{h} = \lim_{h \to 0^+} (4 - h) = +4.$$
     Since $f'_-(-2) = -4 \neq +4 = f'_+(-2)$, **$f'(x)$ does not exist at $x = -2$**.
   - **At $x = 2$:**
     $$f'_-(2) = \lim_{h \to 0^-} \frac{(4 - (2+h)^2) - 0}{h} = \lim_{h \to 0^-} (-4 - h) = -4,$$
     $$f'_+(2) = \lim_{h \to 0^+} \frac{((2+h)^2 - 4) - 0}{h} = \lim_{h \to 0^+} (4 + h) = +4.$$
     Since $f'_-(2) = -4 \neq +4 = f'_+(2)$, **$f'(x)$ does not exist at $x = 2$**.

3. **Geometric Justification:**
   The parabola $y = x^2 - 4$ crosses the $x$-axis at $x = \pm 2$ **transversally** with non-zero slopes $\mp 4$. When the bottom portion is reflected across the $x$-axis, the tangent slope on the reflected side is negated (from $-4$ to $+4$ at $x = -2$, and from $+4$ to $-4$ at $x = 2$). Consequently, the graph forms **sharp corners (angular points)** at $(-2, 0)$ and $(2, 0)$ where the left-hand and right-hand half-tangents meet at an angle rather than forming a single smooth tangent line.

### Step 4: Monotonicity and Extrema Summary
| Interval / Point | $(-\infty, -2)$ | $x = -2$ | $(-2, 0)$ | $x = 0$ | $(0, 2)$ | $x = 2$ | $(2, \infty)$ |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **$f'(x)$** | $2x < 0$ ($-$) | DNE ($\mp 4$) | $-2x > 0$ ($+$) | $0$ | $-2x < 0$ ($-$) | DNE ($\mp 4$) | $2x > 0$ ($+$) |
| **Behavior of $f(x)$** | $\searrow$ | **Global Min** ($0$) | $\nearrow$ | **Local Max** ($4$) | $\searrow$ | **Global Min** ($0$) | $\nearrow$ |

- **Monotonicity:** Strictly decreasing on $(-\infty, -2]$ and $[0, 2]$; strictly increasing on $[-2, 0]$ and $[2, \infty)$.
- **Extrema:**
  - **Local and Global Minima** at $x = -2$ and $x = 2$ with $f(\pm 2) = 0$ (critical points where $f'$ does not exist!).
  - **Local Maximum** at $x = 0$ with $f(0) = 4$ (stationary critical point where $f'(0) = 0$).

---

## 4. Verification and Consistency Checks
1. **Non-Negativity Bound:** Since $|x^2 - 4| \ge 0$ for all $x \in \mathbb{R}$ and $f(\pm 2) = 0$, the points $x = \pm 2$ are guaranteed to be global minima even though $f'(\pm 2)$ does not exist. This demonstrates why critical points are defined as points in $D_f$ where $f'(x) = 0$ **or** $f'(x)$ does not exist.
2. **Even Function Consistency:** $f(-x) = |(-x)^2 - 4| = |x^2 - 4| = f(x)$, which matches the symmetric corners at $x = \pm 2$ and symmetric slopes $f'_\pm(-2) = -f'_\mp(2)$.
