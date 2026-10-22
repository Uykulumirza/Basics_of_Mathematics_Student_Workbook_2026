# Solution to Problem 4: A Function with Two Vertical Asymptotes

## 1. Problem Statement
Analyze
$$f(x)=\frac1{x^2-1}.$$
Determine the domain, asymptotes, sign, and monotonicity on the intervals of the domain. Explain why each interval must be analyzed separately.

> **Why this problem:** it practices the analysis of a function on several disjoint intervals.

---

## 2. Theoretical Background and Concepts
1. **Disjoint Connected Components of the Domain:** When a rational function has vertical asymptotes at $x = a$ and $x = b$ ($a < b$), its domain breaks into three disjoint open intervals: $(-\infty, a)$, $(a, b)$, and $(b, \infty)$.
2. **Interval-Wise Monotonicity Theorem:** The Mean Value Theorem (which links the sign of $f'(x)$ to monotonicity) holds only on **intervals** where $f$ is continuous and differentiable. If a domain is a union of disjoint intervals $I_1 \cup I_2$, having $f'(x) > 0$ on $I_1$ and $I_2$ means $f$ is increasing on $I_1$ and increasing on $I_2$ separately, **not** necessarily on $I_1 \cup I_2$.
3. **Symmetry:** If $f(-x) = f(x)$ for all $x \in D_f$, then $f$ is an **even function**, and its graph is symmetric with respect to the $y$-axis.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Domain and Symmetry
The denominator factors as $x^2 - 1 = (x - 1)(x + 1)$, which vanishes at $x = -1$ and $x = 1$. Thus, the domain consists of three disjoint open intervals:
$$D_f = \mathbb{R} \setminus \{-1, 1\} = (-\infty, -1) \cup (-1, 1) \cup (1, \infty).$$
Note that $D_f$ is symmetric about $0$ and $f(-x) = \frac{1}{(-x)^2 - 1} = \frac{1}{x^2 - 1} = f(x)$, so $f$ is **even**.

### Step 2: Sign of the Function and Intercepts
Since the numerator is $1 > 0$, the sign of $f(x)$ is identical to the sign of the quadratic denominator $x^2 - 1 = (x + 1)(x - 1)$:
- **$f(x) > 0$** for $x \in (-\infty, -1) \cup (1, \infty)$ (where $x^2 > 1$).
- **$f(x) < 0$** for $x \in (-1, 1)$ (where $x^2 < 1$).
- **Zeros:** None ($1 \neq 0$, so $f(x) = 0$ has no solutions).
- **$y$-intercept:** At $x = 0$, $f(0) = \frac{1}{0 - 1} = -1$, giving the point **$(0, -1)$**.

### Step 3: Asymptotes
1. **Vertical Asymptotes ($x = -1$ and $x = 1$):**
   Using the sign of $x^2 - 1$ found above, we compute all four one-sided limits:
   - At **$x = -1$**:
     $$\lim_{x \to -1^-} \frac{1}{x^2 - 1} = \left[\frac{1}{0^+}\right] = +\infty, \qquad \lim_{x \to -1^+} \frac{1}{x^2 - 1} = \left[\frac{1}{0^-}\right] = -\infty.$$
   - At **$x = 1$**:
     $$\lim_{x \to 1^-} \frac{1}{x^2 - 1} = \left[\frac{1}{0^-}\right] = -\infty, \qquad \lim_{x \to 1^+} \frac{1}{x^2 - 1} = \left[\frac{1}{0^+}\right] = +\infty.$$
   Therefore, both **$x = -1$** and **$x = 1$** are two-sided vertical asymptotes.

2. **Horizontal Asymptote ($y = 0$):**
   As $x \to \pm\infty$, $x^2 - 1 \to +\infty$, so:
   $$\lim_{x \to -\infty} \frac{1}{x^2 - 1} = 0, \qquad \lim_{x \to +\infty} \frac{1}{x^2 - 1} = 0.$$
   Thus, **$y = 0$** (the $x$-axis) is a horizontal asymptote at both $-\infty$ and $+\infty$.

### Step 4: Derivative, Monotonicity, and Local Extrema
Differentiating $f(x) = (x^2 - 1)^{-1}$ via the chain rule for $x \neq \pm 1$:
$$f'(x) = -1 \cdot (x^2 - 1)^{-2} \cdot (2x) = \frac{-2x}{(x^2 - 1)^2}.$$
- **Critical point:** $f'(x) = 0 \iff -2x = 0 \iff x = 0 \in (-1, 1)$.
- **Sign of $f'(x)$:** Since $(x^2 - 1)^2 > 0$ for all $x \in D_f$, the sign of $f'(x)$ is determined solely by $-2x$:
  - For $x < 0$ ($x \neq -1$), $-2x > 0 \implies f'(x) > 0$.
  - For $x > 0$ ($x \neq 1$), $-2x < 0 \implies f'(x) < 0$.

| Interval / Point | $(-\infty, -1)$ | $x = -1$ | $(-1, 0)$ | $x = 0$ | $(0, 1)$ | $x = 1$ | $(1, \infty)$ |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Sign of $f(x)$** | $+$ | undefined | $-$ | $-1$ | $-$ | undefined | $+$ |
| **Sign of $f'(x)$** | $+$ | undefined | $+$ | $0$ | $-$ | undefined | $-$ |
| **Behavior of $f(x)$** | $\nearrow$ ($0^+$ to $+\infty$) | VA | $\nearrow$ ($-\infty$ to $-1$) | **Local Max** ($-1$) | $\searrow$ ($-1$ to $-\infty$) | VA | $\searrow$ ($+\infty$ to $0^+$) |

Consequently:
- $f$ is **strictly increasing** on $(-\infty, -1)$ and **strictly increasing** on $(-1, 0]$.
- $f$ is **strictly decreasing** on $[0, 1)$ and **strictly decreasing** on $(1, \infty)$.
- At $x = 0$, $f'(x)$ changes sign from $+$ to $-$, so $f$ has a **local maximum** of $f(0) = -1$.

### Step 5: Why Each Interval Must Be Analyzed Separately
Monotonicity is deduced from the sign of $f'(x)$ via the **Mean Value Theorem**: for $x_1 < x_2$, $f(x_2) - f(x_1) = f'(c)(x_2 - x_1)$ requires $f$ to be continuous on the entire closed interval $[x_1, x_2]$ and differentiable on $(x_1, x_2)$.
- Because $f$ has discontinuities (vertical asymptotes) at $x = -1$ and $x = 1$, we **cannot** apply the Mean Value Theorem across $x = -1$ or $x = 1$.
- Even though $f'(x) > 0$ on both $(-\infty, -1)$ and $(-1, 0)$, the function is **not** increasing on the combined set $(-\infty, -1) \cup (-1, 0]$. For example, taking $x_1 = -2 \in (-\infty, -1)$ and $x_2 = -0.5 \in (-1, 0)$, we have $x_1 < x_2$, yet:
  $$f(-2) = \frac{1}{(-2)^2 - 1} = \frac{1}{3} > f(-0.5) = \frac{1}{(-0.5)^2 - 1} = -\frac{4}{3}.$$
  At the vertical asymptote $x = -1$, the graph jumps from $+\infty$ on the left to $-\infty$ on the right, breaking global monotonicity. Thus, monotonicity must always be stated separately on each connected component of the domain.

---

## 4. Verification and Consistency Checks
1. **Even Symmetry Check:** The interval $(-\infty, -1)$ where $f$ is positive and increasing is the exact mirror image across the $y$-axis of $(1, \infty)$ where $f$ is positive and decreasing. Similarly, $(-1, 0]$ (increasing to $-1$) mirrors $[0, 1)$ (decreasing from $-1$).
2. **Second Derivative Check at $x = 0$:**
   $$f''(x) = \frac{-2(x^2-1)^2 - (-2x)\cdot 2(x^2-1)(2x)}{(x^2-1)^4} = \frac{6x^2 + 2}{(x^2-1)^3} \implies f''(0) = \frac{2}{(-1)^3} = -2 < 0,$$
   confirming that $x = 0$ is a strict local maximum (and that $f$ is concave on $(-1, 1)$ and convex on $(-\infty, -1)$ and $(1, \infty)$).
