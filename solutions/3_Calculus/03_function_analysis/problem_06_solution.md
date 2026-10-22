# Solution to Problem 6: A Logarithmic Function

## 1. Problem Statement
Analyze the domain, zero, and monotonicity of
$$f(x)=\ln x-x+1.$$
Explain why the analysis must begin with the domain.

> **Why this problem:** it reinforces the role of the domain and derivative in the analysis of a logarithmic function.

---

## 2. Theoretical Background and Concepts
1. **Domain Priority in Calculus:** A function $f$ and its derivative $f'$ exist only on subsets of the natural domain $D_f$. Any algebraic manipulation of $f'(x)$ (such as solving $f'(x) = 0$ or testing the sign of a rational expression) is mathematically valid **only** for $x \in D_f$.
2. **Natural Logarithm Domain:** In real analysis, the natural logarithm $\ln x$ is defined exclusively for strictly positive arguments: $x > 0$.
3. **Uniqueness of Zeros via Extremum:** If a continuous function $f$ on an interval $I$ attains a strict global maximum $f(x_0) = 0$ at $x_0 \in I$ (being strictly increasing to the left of $x_0$ and strictly decreasing to the right of $x_0$), then $f(x) < 0$ for all $x \in I \setminus \{x_0\}$, which proves that $x_0$ is the **unique** root of $f(x) = 0$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Domain and Why the Analysis Must Begin with It
The expression $f(x) = \ln x - x + 1$ contains the natural logarithm $\ln x$, which is defined in $\mathbb{R}$ if and only if $x > 0$. The linear part $-x + 1$ is defined for all $x \in \mathbb{R}$. Therefore, the domain of $f$ is:
$$D_f = (0, \infty).$$

**Why the analysis must begin with the domain:**
1. **Meaninglessness of Values Outside $D_f$:** For $x \le 0$, $f(x)$ does not exist as a real number, so asking whether $f$ is increasing, decreasing, or has zeros on $(-\infty, 0]$ is meaningless.
2. **Preventing Spurious Sign Changes in $f'(x)$:** When we differentiate $\ln x$, we obtain the algebraic expression $\frac{1}{x}$, which leads to $f'(x) = \frac{1 - x}{x}$. Taken purely as a rational expression on $\mathbb{R} \setminus \{0\}$, $\frac{1-x}{x}$ is defined for $x < 0$ and changes sign at $x = 0$. However, because $D_f = (0, \infty)$, the denominator $x$ is **always strictly positive** ($x > 0$) on the entire domain! Beginning with $D_f = (0, \infty)$ immediately restricts our sign chart to $x > 0$ and prevents the mistake of including $x \le 0$ in intervals of monotonicity.

### Step 2: Derivative, Monotonicity, and Global Maximum
For $x \in (0, \infty)$, differentiating $f(x) = \ln x - x + 1$ gives:
$$f'(x) = \frac{1}{x} - 1 = \frac{1 - x}{x}.$$
- **Critical point:** On $D_f = (0, \infty)$, $f'(x) = 0 \iff \frac{1 - x}{x} = 0 \iff 1 - x = 0 \iff x = 1 \in (0, \infty)$.
- **Sign of $f'(x)$ on $(0, \infty)$:** Since $x > 0$ throughout $D_f$, the sign of $f'(x) = \frac{1 - x}{x}$ is identical to the sign of the numerator $1 - x$:
  - For $x \in (0, 1)$: $1 - x > 0 \implies f'(x) > 0$.
  - For $x \in (1, \infty)$: $1 - x < 0 \implies f'(x) < 0$.

| Interval / Point | $(0, 1)$ | $x = 1$ | $(1, \infty)$ |
| :---: | :---: | :---: | :---: |
| Sign of $(1 - x)$ | $+$ | $0$ | $-$ |
| Sign of $x$ on $D_f$ | $+$ | $+$ | $+$ |
| **Sign of $f'(x)$** | **$+$** | **$0$** | **$-$** |
| **Behavior of $f(x)$** | $\nearrow$ ( strictly increasing ) | **Global Maximum** ($0$) | $\searrow$ ( strictly decreasing ) |

By continuity of $f$ at $x = 1$:
- $f$ is **strictly increasing** on $(0, 1]$.
- $f$ is **strictly decreasing** on $[1, \infty)$.
- At $x = 1$, $f$ attains its **strict global maximum** on $(0, \infty)$:
  $$f_{\max} = f(1) = \ln 1 - 1 + 1 = 0 - 1 + 1 = 0.$$

### Step 3: Finding all Zeros of $f(x)$
The equation $\ln x - x + 1 = 0$ is a transcendental equation that cannot be solved by elementary algebraic isolation of $x$. However, our monotonicity and extremum analysis solves it completely:
1. At $x = 1$, we have $f(1) = 0$, so **$x = 1$ is a zero** of $f(x)$.
2. Because $f$ is strictly increasing on $(0, 1]$ and strictly decreasing on $[1, \infty)$, $f(1) = 0$ is the **strict global maximum** of $f$ on $(0, \infty)$. That is:
   $$f(x) < f(1) = 0 \quad \text{for all } x \in (0, \infty) \setminus \{1\}.$$
3. Therefore, **$x = 1$ is the unique zero** of $f(x)$ on its entire domain $(0, \infty)$. (Note: This also proves the famous fundamental inequality $\ln x \le x - 1$ for all $x > 0$, with equality if and only if $x = 1$.)

---

## 4. Verification and Consistency Checks
1. **Second Derivative and Concavity Check:**
   $$f''(x) = -\frac{1}{x^2} < 0 \quad \text{for all } x \in (0, \infty).$$
   Thus, $f$ is strictly concave on $(0, \infty)$, its tangent line at $x = 1$ is $y = f(1) + f'(1)(x - 1) = 0$, and the graph of a strictly concave function lies strictly below its tangent line everywhere except at the point of tangency $x = 1$.
2. **Boundary Limits:**
   - As $x \to 0^+$: $\lim_{x \to 0^+} (\ln x - x + 1) = -\infty - 0 + 1 = -\infty$ (vertical asymptote $x = 0$).
   - As $x \to +\infty$: $\lim_{x \to +\infty} x\left(\frac{\ln x}{x} - 1 + \frac{1}{x}\right) = +\infty \cdot (0 - 1 + 0) = -\infty$.
   Both boundary limits are $-\infty$, consistent with $f$ rising from $-\infty$ to a single peak of $0$ at $x = 1$ and then falling back to $-\infty$.
