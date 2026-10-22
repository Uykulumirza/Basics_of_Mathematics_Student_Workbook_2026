# Solution to Problem 9: An Oblique Asymptote

## 1. Problem Statement
Analyze the asymptotes of
$$f(x)=\frac{x^2+1}{x-1}.$$
Perform polynomial division and explain why the remainder term vanishes for large $|x|$.

> **Why this problem:** it teaches how to recognize an oblique asymptote and interpret the decomposition of a function.

---

## 2. Theoretical Background and Concepts
1. **Rational Functions and Oblique Asymptotes:** For a rational function $f(x) = \frac{P(x)}{Q(x)}$ where $\deg P = \deg Q + 1$, Euclidean polynomial division yields:
   $$f(x) = (mx + b) + \frac{R(x)}{Q(x)}, \qquad \text{with } \deg R < \deg Q.$$
   Because $\deg R < \deg Q$, the proper rational remainder satisfies $\lim_{x \to \pm\infty} \frac{R(x)}{Q(x)} = 0$, which proves that the line $y = mx + b$ is an **oblique (slant) asymptote** as $x \to \pm\infty$.
2. **General Cauchy Formulas for an Oblique Asymptote $y = mx + b$:**
   $$m = \lim_{x \to \pm\infty} \frac{f(x)}{x}, \qquad b = \lim_{x \to \pm\infty} \bigl[f(x) - mx\bigr].$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Domain and Polynomial Division
The denominator $x - 1$ vanishes at $x = 1$, so the domain of $f$ is:
$$D_f = \mathbb{R} \setminus \{1\} = (-\infty, 1) \cup (1, \infty).$$

We divide the numerator $x^2 + 1$ by the denominator $x - 1$. Using algebraic identity $x^2 - 1 = (x - 1)(x + 1)$, we write $x^2 + 1 = (x^2 - 1) + 2 = (x - 1)(x + 1) + 2$:
$$f(x) = \frac{x^2 + 1}{x - 1} = \frac{(x - 1)(x + 1) + 2}{x - 1} = x + 1 + \frac{2}{x - 1}.$$
Here:
- **Linear quotient:** $q(x) = x + 1$,
- **Remainder term:** $r(x) = \frac{2}{x - 1}$.

### Step 2: Vertical Asymptote
At the boundary point $x = 1$ of the domain, the numerator approaches $1^2 + 1 = 2 > 0$, while the denominator $x - 1$ approaches $0$:
- **Left-hand limit ($x \to 1^-$):** Since $x < 1$, we have $x - 1 \to 0^-$, so:
  $$\lim_{x \to 1^-} \frac{x^2 + 1}{x - 1} = \left[\frac{2}{0^-}\right] = -\infty.$$
- **Right-hand limit ($x \to 1^+$):** Since $x > 1$, we have $x - 1 \to 0^+$, so:
  $$\lim_{x \to 1^+} \frac{x^2 + 1}{x - 1} = \left[\frac{2}{0^+}\right] = +\infty.$$
Therefore, the vertical line **$x = 1$** is a two-sided **vertical asymptote**.

### Step 3: Oblique Asymptote and Why the Remainder Term Vanishes for Large $|x|$
From the decomposition $f(x) = (x + 1) + \frac{2}{x - 1}$, the vertical distance (with sign) between the graph of $y = f(x)$ and the straight line $y = x + 1$ at any $x \neq 1$ is given by the remainder term:
$$f(x) - (x + 1) = \frac{2}{x - 1}.$$

**Why the remainder term vanishes for large $|x|$:**
1. **Constant Numerator vs. Unbounded Denominator:** In the fraction $\frac{2}{x - 1}$, the numerator is the fixed constant $2$, whereas the magnitude of the denominator $|x - 1| \ge |x| - 1$ grows without bound ($\to +\infty$) as $|x| \to \infty$. Dividing a fixed constant by an arbitrarily large number produces a result arbitrarily close to $0$:
   $$\lim_{x \to -\infty} \frac{2}{x - 1} = 0^-, \qquad \lim_{x \to +\infty} \frac{2}{x - 1} = 0^+.$$
2. **Geometric Meaning:** Because $\lim_{x \to \pm\infty} \bigl[f(x) - (x + 1)\bigr] = 0$, the line **$y = x + 1$** is a two-sided **oblique asymptote** of $f(x)$ (and consequently $f$ has no horizontal asymptote, since $\lim_{x \to \pm\infty} f(x) = \pm\infty$).
   - Furthermore, the sign of the remainder $\frac{2}{x - 1}$ tells us which side of the asymptote the curve lies on:
     - For $x > 1$ (and in particular as $x \to +\infty$), $\frac{2}{x - 1} > 0$, so the graph of $f(x)$ approaches the line $y = x + 1$ **from above**.
     - For $x < 1$ (and in particular as $x \to -\infty$), $\frac{2}{x - 1} < 0$, so the graph of $f(x)$ approaches the line $y = x + 1$ **from below**.

---

## 4. Verification and Consistency Checks
1. **Verification via General Limit Formulas ($y = mx + b$):**
   $$m = \lim_{x \to \pm\infty} \frac{f(x)}{x} = \lim_{x \to \pm\infty} \frac{x^2 + 1}{x^2 - x} = \lim_{x \to \pm\infty} \frac{1 + \frac{1}{x^2}}{1 - \frac{1}{x}} = 1,$$
   $$b = \lim_{x \to \pm\infty} \bigl[f(x) - 1 \cdot x\bigr] = \lim_{x \to \pm\infty} \frac{x^2 + 1 - x(x - 1)}{x - 1} = \lim_{x \to \pm\infty} \frac{x + 1}{x - 1} = 1.$$
   This confirms the oblique asymptote $y = x + 1$.
2. **Numerical Decay of Remainder:**
   - At $x = 11$: $f(11) = 12 + \frac{2}{10} = 12.2$ vs. $y_{\text{asymp}}(11) = 12$ (error $+0.2$).
   - At $x = 101$: $f(101) = 102 + \frac{2}{100} = 102.02$ vs. $y_{\text{asymp}}(101) = 102$ (error $+0.02$).
   - At $x = -99$: $f(-99) = -98 + \frac{2}{-100} = -98.02$ vs. $y_{\text{asymp}}(-99) = -98$ (error $-0.02$).
