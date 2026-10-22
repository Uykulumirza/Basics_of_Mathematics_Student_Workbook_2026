# Solution to Problem 5: An Exponential Function with a Maximum

## 1. Problem Statement
Analyze the monotonicity and extrema of
$$f(x)=xe^{-x}.$$
Also examine the behavior as $x\to\infty$ and explain how the limit affects the shape of the graph on the right-hand side.

> **Why this problem:** it combines the derivative with a limit in the description of the global behavior of a function.

---

## 2. Theoretical Background and Concepts
1. **Product Rule and Exponential Positivity:** For $f(x) = g(x)e^{-x}$, the derivative is $f'(x) = [g'(x) - g(x)]e^{-x}$. Because the exponential function satisfies $e^{-x} > 0$ for all $x \in \mathbb{R}$, the sign of $f'(x)$ is completely determined by the polynomial factor $g'(x) - g(x)$.
2. **Relative Growth Rates at Infinity:** As $x \to +\infty$, the exponential decay $e^{-x} = \frac{1}{e^x}$ dominates any polynomial growth $x^n$, so $\lim_{x \to +\infty} \frac{x}{e^x} = 0$ (which can be proved via L'Hôpital's Rule or the Taylor bound $e^x > \frac{x^2}{2}$ for $x > 0$).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Domain, Zero, and Sign of $f(x)$
- **Domain:** $D_f = \mathbb{R} = (-\infty, \infty)$.
- **Zero and Sign:** Since $e^{-x} > 0$ for all $x \in \mathbb{R}$, $f(x) = xe^{-x}$ has the exact same sign as $x$:
  - $f(x) < 0$ for $x \in (-\infty, 0)$,
  - $f(0) = 0$ (the unique $x$- and $y$-intercept is $(0, 0)$),
  - $f(x) > 0$ for $x \in (0, \infty)$.

### Step 2: First Derivative, Monotonicity, and Extrema
Applying the product rule and chain rule to $f(x) = x \cdot e^{-x}$:
$$f'(x) = (x)' e^{-x} + x (e^{-x})' = 1 \cdot e^{-x} + x(-e^{-x}) = (1 - x)e^{-x}.$$
Since $e^{-x} > 0$ for all $x \in \mathbb{R}$:
- **Critical point:** $f'(x) = 0 \iff 1 - x = 0 \iff x = 1$.
- **Sign of $f'(x)$:**
  - For $x < 1$: $1 - x > 0 \implies f'(x) > 0$.
  - For $x > 1$: $1 - x < 0 \implies f'(x) < 0$.

| Interval / Point | $(-\infty, 1)$ | $x = 1$ | $(1, \infty)$ |
| :---: | :---: | :---: | :---: |
| Sign of $(1 - x)$ | $+$ | $0$ | $-$ |
| Sign of $e^{-x}$ | $+$ | $+$ | $+$ |
| **Sign of $f'(x)$** | **$+$** | **$0$** | **$-$** |
| **Behavior of $f(x)$** | $\nearrow$ ( strictly increasing ) | **Global Maximum** ($1/e$) | $\searrow$ ( strictly decreasing ) |

- **Intervals of Monotonicity:**
  - $f$ is **strictly increasing** on $(-\infty, 1]$.
  - $f$ is **strictly decreasing** on $[1, \infty)$.
- **Local and Global Maximum:** At $x = 1$, $f'(x)$ changes sign from $+$ to $-$, so $f$ attains a strict local (and global) maximum:
  $$f_{\max} = f(1) = 1 \cdot e^{-1} = \frac{1}{e} \approx 0.368.$$
  There are no local minima.

### Step 3: Asymptotic Behavior as $x \to \infty$ (and $x \to -\infty$)
1. **Right-hand behavior ($x \to +\infty$):**
   Writing $f(x) = \frac{x}{e^x}$ gives an indeterminate form $\left[\frac{\infty}{\infty}\right]$. Applying L'Hôpital's Rule (or noting that $0 < \frac{x}{e^x} < \frac{x}{1 + x + x^2/2} < \frac{2}{x}$ for $x > 0$):
   $$\lim_{x \to +\infty} xe^{-x} = \lim_{x \to +\infty} \frac{x}{e^x} \stackrel{\text{L'H}}{=} \lim_{x \to +\infty} \frac{1}{e^x} = 0^+.$$
   Thus, the line **$y = 0$** (the positive $x$-axis) is a horizontal asymptote as $x \to +\infty$.
2. **Left-hand behavior ($x \to -\infty$):**
   As $x \to -\infty$, we have $x \to -\infty$ and $e^{-x} \to +\infty$, so:
   $$\lim_{x \to -\infty} xe^{-x} = [-\infty \cdot (+\infty)] = -\infty.$$

### Step 4: How the Limit Affects the Shape of the Graph on the Right-Hand Side
For $x > 1$, the derivative $f'(x) < 0$ tells us that $f(x)$ is strictly decreasing after reaching its peak at $\left(1, \frac{1}{e}\right)$. However, knowing only that $f$ decreases does not tell us whether $f(x)$ drops to $-\infty$ or levels off.
- The limit $\lim_{x \to +\infty} f(x) = 0$, combined with the fact that $f(x) = xe^{-x} > 0$ for all $x > 0$, forces the graph to remain strictly above the $x$-axis while decreasing toward it.
- Consequently, after peaking at $\left(1, \frac{1}{e}\right)$, the curve falls most steeply at the **inflection point** $x = 2$ (since $f''(x) = (x - 2)e^{-x} = 0 \iff x = 2$, where $f(2) = \frac{2}{e^2} \approx 0.271$ and concavity changes from concave on $(-\infty, 2)$ to convex on $(2, \infty)$) and then flattens out, approaching the horizontal asymptote $y = 0$ asymptotically from above without ever crossing or touching the $x$-axis again.

---

## 4. Verification and Consistency Checks
1. **Second Derivative Test at $x = 1$:**
   $$f''(x) = \frac{d}{dx}\bigl[(1 - x)e^{-x}\bigr] = -e^{-x} - (1 - x)e^{-x} = (x - 2)e^{-x}.$$
   At $x = 1$, $f''(1) = (1 - 2)e^{-1} = -\frac{1}{e} < 0$, confirming a strict local maximum at $x = 1$.
2. **Numerical Trend Check:**
   - $f(0) = 0$,
   - $f(1) = e^{-1} \approx 0.368$ (peak),
   - $f(2) = 2e^{-2} \approx 0.271$ (inflection point),
   - $f(5) = 5e^{-5} \approx 0.034 \to 0^+$.
   This confirms the rise through the origin to $(1, 1/e)$ followed by a smooth asymptotic decay toward $0^+$.
