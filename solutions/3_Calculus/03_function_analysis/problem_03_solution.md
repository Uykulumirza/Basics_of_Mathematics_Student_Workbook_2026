# Solution to Problem 3: A Rational Function

## 1. Problem Statement
Analyze the domain, zeros, asymptotes, and monotonicity of
$$f(x)=\frac{x+1}{x-2}.$$
Finally, sketch a graph consistent with all the information obtained.

> **Why this problem:** it teaches how to combine the domain, limits, and derivative in the analysis of a rational function.

---

## 2. Theoretical Background and Concepts
For a linear fractional (homographic) rational function $f(x) = \frac{ax+b}{cx+d}$ with $c \neq 0$ and $ad - bc \neq 0$:
1. **Domain:** Defined for all $x \in \mathbb{R}$ where the denominator is non-zero ($cx + d \neq 0$).
2. **Canonical Decomposition:** Dividing the numerator by the denominator writes $f(x) = \frac{a}{c} + \frac{R}{cx+d}$, which makes limits and derivatives transparent.
3. **Asymptotes:**
   - A **vertical asymptote** $x = x_0$ occurs at the zero of the denominator where the numerator is non-zero, so $\lim_{x \to x_0^\pm} f(x) = \pm\infty$.
   - A **horizontal asymptote** $y = L$ occurs when $\lim_{x \to \pm\infty} f(x) = L$.
4. **Monotonicity:** Determined by the sign of $f'(x)$ separately on each connected interval of the domain.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Domain and Algebraic Decomposition
The denominator vanishes when $x - 2 = 0 \iff x = 2$. Therefore, the domain is:
$$D_f = \mathbb{R} \setminus \{2\} = (-\infty, 2) \cup (2, \infty).$$
Rewriting the numerator as $x + 1 = (x - 2) + 3$, we decompose $f(x)$ into:
$$f(x) = \frac{(x - 2) + 3}{x - 2} = 1 + \frac{3}{x - 2}.$$

### Step 2: Zeros and $y$-Intercept
- **Zero ($x$-intercept):** For $x \neq 2$, $f(x) = 0 \iff x + 1 = 0 \iff x = -1 \in D_f$. Thus, the graph crosses the $x$-axis at **$(-1, 0)$**.
- **$y$-intercept:** Setting $x = 0 \in D_f$ gives $f(0) = \frac{0 + 1}{0 - 2} = -\frac{1}{2}$. Thus, the graph crosses the $y$-axis at **$(0, -1/2)$**.

### Step 3: Asymptotes
1. **Vertical Asymptote at $x = 2$:**
   We examine the one-sided limits as $x \to 2^-$ and $x \to 2^+$:
   - As $x \to 2^-$ ($x < 2$), the numerator $x + 1 \to 3 > 0$ and the denominator $x - 2 \to 0^-$:
     $$\lim_{x \to 2^-} \frac{x + 1}{x - 2} = \left[\frac{3}{0^-}\right] = -\infty.$$
   - As $x \to 2^+$ ($x > 2$), the numerator $x + 1 \to 3 > 0$ and the denominator $x - 2 \to 0^+$:
     $$\lim_{x \to 2^+} \frac{x + 1}{x - 2} = \left[\frac{3}{0^+}\right] = +\infty.$$
   Hence, the line **$x = 2$** is a two-sided vertical asymptote.

2. **Horizontal Asymptote at $y = 1$:**
   Using the decomposed form $f(x) = 1 + \frac{3}{x - 2}$:
   $$\lim_{x \to -\infty} \left(1 + \frac{3}{x - 2}\right) = 1 + 0 = 1, \qquad \lim_{x \to +\infty} \left(1 + \frac{3}{x - 2}\right) = 1 + 0 = 1.$$
   Hence, the line **$y = 1$** is a horizontal asymptote as $x \to -\infty$ and as $x \to +\infty$ (and there are no oblique asymptotes).

### Step 4: Derivative, Monotonicity, and Extrema
Differentiating $f(x) = 1 + 3(x - 2)^{-1}$ (or applying the quotient rule to $\frac{x+1}{x-2}$) for $x \neq 2$:
$$f'(x) = \frac{1 \cdot (x - 2) - (x + 1) \cdot 1}{(x - 2)^2} = \frac{-3}{(x - 2)^2}.$$
For every $x \in \mathbb{R} \setminus \{2\}$, we have $(x - 2)^2 > 0$, so:
$$f'(x) = \frac{-3}{(x - 2)^2} < 0 \quad \text{for all } x \in (-\infty, 2) \cup (2, \infty).$$

| Interval / Point | $(-\infty, 2)$ | $x = 2$ | $(2, \infty)$ |
| :---: | :---: | :---: | :---: |
| **Sign of $f'(x)$** | $-$ | undefined (VA) | $-$ |
| **Behavior of $f(x)$** | $\searrow$ from $1^-$ to $-\infty$ | Vertical Asymptote | $\searrow$ from $+\infty$ to $1^+$ |

- **Monotonicity:** $f$ is **strictly decreasing on $(-\infty, 2)$** and **strictly decreasing on $(2, \infty)$**. (Note: $f$ is *not* decreasing on the union $(-\infty, 2) \cup (2, \infty)$ as a whole because $f(0) = -1/2 < f(3) = 4$.)
- **Extrema:** Since $f'(x) \neq 0$ everywhere on $D_f$, $f$ has **no local extrema**.

### Step 5: Graph Sketch
Below is an accurately aligned coordinate sketch showing the vertical asymptote $x = 2$, the horizontal asymptote $y = 1$, the $x$-intercept $(-1, 0)$ on the horizontal axis (`-`), the $y$-intercept $(0, -1/2)$ on the vertical axis (`|`), and the point $(3, 4)$ on the right branch:

```text
                      y
                      ^
                      |       : x = 2
                      |       : .
                      |       :  * (3,4)
                      |       :   \
                      |       :    \
                      |       :     \
                      |       :       \
      ================+=======:=========\=========  y = 1
      ...___          |       :            \___...
            ---___    |       :
        (-1,0)    \   |       :
      -------------*--+-------+------------------> x
                      * (0,-1/2)
                      |\      :
                      | \     :
                      |  \    :
                      |   \   :
                      |    .  :
```

---

## 4. Verification and Consistency Checks
1. **Sign and Value Check:**
   - For $x = -1$: $f(-1) = 0$, matching the $x$-intercept.
   - For $x = 0$: $f(0) = -1/2$, matching the $y$-intercept and showing $f(-1) > f(0)$ (decreasing on $(-\infty, 2)$).
   - For $x = 1$: $f(1) = \frac{2}{-1} = -2 < -1/2$, confirming that $f(x) \to -\infty$ as $x \to 2^-$.
   - For $x = 3$: $f(3) = \frac{4}{1} = 4 > 1$, and for $x = 5$: $f(5) = \frac{6}{3} = 2 \in (1, 4)$, confirming that the right branch decreases from $+\infty$ toward the horizontal asymptote $y = 1$ from above.
