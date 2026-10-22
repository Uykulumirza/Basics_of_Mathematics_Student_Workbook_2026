# Solution to Problem 13: A Logarithm and an Asymptote

## 1. Problem Statement
Perform a complete analysis of
$$f(x)=\frac{\ln x}{x},\qquad x>0.$$
Find the maximum and the behavior at the ends of the domain. Explain which information is necessary for a correct sketch.

> **Why this problem:** it combines the domain, limits, and derivative in a less obvious example.

---

## 2. Theoretical Background and Concepts
1. **Endpoint Limits of $(0, \infty)$:**
   - Near $x = 0^+$, $\ln x \to -\infty$ and $\frac{1}{x} \to +\infty$, which is a determinate product $[-\infty \cdot (+\infty)] = -\infty$ (giving a vertical asymptote at $x = 0$).
   - Near $x \to +\infty$, $\frac{\ln x}{x}$ is an indeterminate form $\left[\frac{\infty}{\infty}\right]$; logarithmic growth is slower than any positive power of $x$, so $\lim_{x \to +\infty} \frac{\ln x}{x} = 0^+$.
2. **Quotient Rule for Derivatives:** For $f(x) = \frac{u(x)}{v(x)}$, $f'(x) = \frac{u'v - uv'}{v^2}$ and $f''(x) = (f'(x))'$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Domain, Zero, and Sign of $f(x)$
- **Domain:** $D_f = (0, \infty)$ (so there is no symmetry and no $y$-intercept).
- **Zero ($x$-intercept) and Sign:** Since $x > 0$ on $D_f$, the sign of $f(x) = \frac{\ln x}{x}$ is identical to the sign of $\ln x$:
  - $f(x) < 0$ for $x \in (0, 1)$,
  - $f(1) = \frac{\ln 1}{1} = 0$ (unique $x$-intercept at **$(1, 0)$**),
  - $f(x) > 0$ for $x \in (1, \infty)$.

### Step 2: Behavior at the Ends of the Domain (Asymptotes)
1. **Right-hand limit at $x = 0^+$ (Vertical Asymptote):**
   As $x \to 0^+$, we have $\ln x \to -\infty$ and $\frac{1}{x} \to +\infty$. Their product is not indeterminate:
   $$\lim_{x \to 0^+} \frac{\ln x}{x} = \lim_{x \to 0^+} \left(\ln x \cdot \frac{1}{x}\right) = [-\infty \cdot (+\infty)] = -\infty.$$
   Thus, the positive $y$-axis **$x = 0$** is a right-sided **vertical asymptote**.

2. **Limit as $x \to +\infty$ (Horizontal Asymptote):**
   As $x \to +\infty$, both $\ln x \to +\infty$ and $x \to +\infty$. Applying L'Hôpital's Rule (or the elementary bound $0 < \ln x < 2\sqrt{x}$ for $x > 1$, so $0 < \frac{\ln x}{x} < \frac{2}{\sqrt{x}} \to 0$):
   $$\lim_{x \to +\infty} \frac{\ln x}{x} \stackrel{\text{L'H}}{=} \lim_{x \to +\infty} \frac{\frac{1}{x}}{1} = 0^+.$$
   Thus, the positive $x$-axis **$y = 0$** is a **horizontal asymptote** as $x \to +\infty$ (approached from above).

### Step 3: First Derivative, Monotonicity, and Global Maximum
Applying the quotient rule for $x > 0$:
$$f'(x) = \frac{\frac{1}{x} \cdot x - (\ln x) \cdot 1}{x^2} = \frac{1 - \ln x}{x^2}.$$
- **Critical point:** Since $x^2 > 0$ for all $x > 0$,
  $$f'(x) = 0 \iff 1 - \ln x = 0 \iff \ln x = 1 \iff x = e \approx 2.718.$$
- **Sign of $f'(x)$:** Because $\ln x$ is strictly increasing:
  - For $x \in (0, e)$: $\ln x < 1 \implies 1 - \ln x > 0 \implies f'(x) > 0$.
  - For $x \in (e, \infty)$: $\ln x > 1 \implies 1 - \ln x < 0 \implies f'(x) < 0$.

| Interval / Point | $(0, e)$ | $x = e$ | $(e, \infty)$ |
| :---: | :---: | :---: | :---: |
| **Sign of $f'(x)$** | $+$ | $0$ | $-$ |
| **Behavior of $f(x)$** | $\nearrow$ ($-\infty$ to $1/e$) | **Global Maximum** ($1/e$) | $\searrow$ ($1/e$ to $0^+$) |

- **Monotonicity:** $f$ is **strictly increasing** on $(0, e]$ and **strictly decreasing** on $[e, \infty)$.
- **Global Maximum:** At $x = e$, $f$ attains its **strict global maximum**:
  $$f_{\max} = f(e) = \frac{\ln e}{e} = \frac{1}{e} \approx 0.368 \quad \longrightarrow \quad \left(e, \frac{1}{e}\right).$$
  Hence the range of $f$ is $\left(-\infty, \frac{1}{e}\right]$.

### Step 4: Second Derivative, Convexity, and Inflection Point
Differentiating $f'(x) = \frac{1 - \ln x}{x^2}$ via the quotient rule:
$$f''(x) = \frac{\left(-\frac{1}{x}\right)x^2 - (1 - \ln x)(2x)}{x^4} = \frac{-x - 2x + 2x\ln x}{x^4} = \frac{2\ln x - 3}{x^3}.$$
- **Inflection point:** For $x > 0$, $f''(x) = 0 \iff 2\ln x - 3 = 0 \iff \ln x = \frac{3}{2} \iff x = e^{3/2} = e\sqrt{e} \approx 4.482$.
- **Curvature:**
  - On $\left(0, e^{3/2}\right]$: $f''(x) \le 0$, so $f$ is **strictly concave** ($\cap$).
  - On $\left[e^{3/2}, \infty\right)$: $f''(x) \ge 0$, so $f$ is **strictly convex** ($\cup$).
  - **Inflection point:** $\left(e^{3/2}, \frac{3}{2e^{3/2}}\right) \approx (4.482, 0.335)$.

### Step 5: Which Information Is Necessary for a Correct Sketch & Graph Sketch
To draw a qualitatively faithful sketch of $f(x) = \frac{\ln x}{x}$, five pieces of information are indispensable:
1. **Domain restriction $x > 0$ and Vertical Asymptote $\lim_{x \to 0^+} f(x) = -\infty$** (shows the curve plunges down alongside the positive $y$-axis without ever crossing into $x \le 0$).
2. **Unique $x$-intercept at $(1, 0)$** (pins down where the curve passes from negative to positive).
3. **Global maximum at $(e, 1/e)$** (shows the single peak in Quadrant I).
4. **Horizontal asymptote $\lim_{x \to +\infty} f(x) = 0^+$** (shows that after $x = e$, the curve does not fall back below the $x$-axis, but stays positive and approaches $y = 0$ from above).
5. **Inflection point at $x = e^{3/2} > e$** (shows how the curve bends from a downward-curving cap $\cap$ around the maximum to an upward-curving tail $\cup$ that levels off along $y = 0$).

```text
          y
          ^
          |                 (e, 1/e)
          |                    *
          |                .       .    Inflection (e^(3/2), 3/(2e^(3/2)))
          |             .              o
          |           .                     .
      ----+---------*----------------------------' . . . ---> x (y -> 0+)
          |(0,0)  (1,0)
          |       /
          |      /
          |     /
          |    .
          |   .  (x -> 0+, y -> -inf)
```

---

## 4. Verification and Consistency Checks
1. **Second Derivative Test at $x = e$:**
   $$f''(e) = \frac{2\ln e - 3}{e^3} = \frac{2 - 3}{e^3} = -\frac{1}{e^3} < 0,$$
   confirming that $x = e$ is a strict local maximum.
2. **Steiner's Problem Connection:** Since $f(x) = \frac{\ln x}{x}$ has its unique global maximum at $x = e$, for any $x > 0$ with $x \neq e$ we have $\frac{\ln x}{x} < \frac{\ln e}{e} \iff x^{1/x} < e^{1/e}$. In particular, for $x = \pi \approx 3.14 > e$, $\frac{\ln \pi}{\pi} < \frac{\ln e}{e} \implies e^\pi > \pi^e$.
