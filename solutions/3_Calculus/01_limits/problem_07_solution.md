# Exercise 7: Limit at a Point and Canceling a Factor

## 1. Problem Statement

Compute
$$\lim_{x\to3}\frac{x^2-4x+3}{x-3}.$$
Explain why the value of the function at $x=3$ is not needed to compute the limit.

> **Why this exercise:** separates the concept of a limit from the value of a function at a point.

---

## 2. Theoretical Background and Concepts

### Definition of the Limit of a Function at a Point ($\varepsilon$-$\delta$ Definition)
Let $f$ be a function defined on a **punctured neighborhood** of $x_0$, that is, on $(x_0 - r, x_0) \cup (x_0, x_0 + r)$ for some $r > 0$. We write
$$\lim_{x\to x_0} f(x) = L$$
if for every $\varepsilon > 0$, there exists a $\delta > 0$ such that for all $x$ in the domain of $f$:
$$0 < |x - x_0| < \delta \implies |f(x) - L| < \varepsilon.$$
Notice the strict inequality $0 < |x - x_0|$, which is equivalent to $x \neq x_0$.

### Equality of Limits for Functions Agreeing Away from $x_0$
A direct consequence of the condition $0 < |x - x_0|$ is the **Local Replacement Principle**:
If two functions $f(x)$ and $g(x)$ satisfy $f(x) = g(x)$ for all $x \neq x_0$ in some punctured neighborhood of $x_0$, then:
$$\lim_{x\to x_0} f(x) = \lim_{x\to x_0} g(x)$$
(meaning one limit exists if and only if the other exists, and their values are equal).

### Resolving the $\left[\frac{0}{0}\right]$ Indeterminate Form for Rational Functions
If $P(x)$ and $Q(x)$ are polynomials such that $P(x_0) = 0$ and $Q(x_0) = 0$, then by **Bézout's Little Theorem (the Factor Theorem)**, $(x - x_0)$ is a common factor of both $P(x)$ and $Q(x)$. Factoring out and canceling $(x - x_0)$ for $x \neq x_0$ removes the zero from the denominator.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Check the Behavior at $x = 3$ and Identify the Indeterminate Form
Let
$$f(x) = \frac{x^2-4x+3}{x-3}, \quad D_f = \mathbb{R} \setminus \{3\}.$$
If we test what happens to the numerator and denominator as $x \to 3$:
- Numerator: $\lim_{x\to 3} (x^2 - 4x + 3) = 3^2 - 4(3) + 3 = 9 - 12 + 3 = 0$.
- Denominator: $\lim_{x\to 3} (x - 3) = 3 - 3 = 0$.

Thus, the limit has the indeterminate form $\left[\frac{0}{0}\right]$. Because both numerator and denominator vanish at $x = 3$, the Factor Theorem guarantees that $(x - 3)$ is a factor of the quadratic numerator $x^2 - 4x + 3$.

### Step 2: Factor the Numerator and Cancel $(x - 3)$ for $x \neq 3$
We factor the quadratic polynomial $x^2 - 4x + 3$ by finding two numbers whose sum is $-4$ and whose product is $+3$, namely $-3$ and $-1$:
$$x^2 - 4x + 3 = (x - 3)(x - 1).$$

For every $x \neq 3$, the factor $x - 3$ is strictly non-zero ($x - 3 \neq 0$), so we can legitimately divide both numerator and denominator by $x - 3$:
$$f(x) = \frac{x^2 - 4x + 3}{x - 3} = \frac{(x - 3)(x - 1)}{x - 3} = x - 1 \quad \text{for all } x \neq 3.$$

### Step 3: Compute the Limit
Define the linear function $g(x) = x - 1$ for all $x \in \mathbb{R}$. Since $f(x) = g(x)$ for every $x \neq 3$, and $g(x) = x - 1$ is a polynomial (hence continuous everywhere, including at $x = 3$), we have:
$$\lim_{x\to 3} \frac{x^2 - 4x + 3}{x - 3} = \lim_{x\to 3} (x - 1) = 3 - 1 = 2.$$

---

### Step 4: Explain Why the Value of $f$ at $x = 3$ Is Not Needed
Why does it not matter that $f(3)$ is undefined (or what value $f(3)$ would be assigned if we defined it)?

1. **The Definition of Limit Excludes $x = x_0$:**
   In the definition of $\lim_{x\to 3} f(x) = L$, we only examine inputs $x$ satisfying the punctured neighborhood condition
   $$0 < |x - 3| < \delta \iff x \in (3 - \delta, 3) \cup (3, 3 + \delta).$$
   The condition $0 < |x - 3|$ explicitly forbids $x = 3$. A limit describes how the outputs $f(x)$ behave as $x$ gets **arbitrarily close** to $3$, not what happens **at** $x = 3$ itself.
2. **Justification of Factor Cancellation:**
   Because $x = 3$ is excluded when taking the limit $x \to 3$, we are guaranteed that $x - 3 \neq 0$ throughout the entire limiting process. This makes canceling $\frac{x-3}{x-3} = 1$ an exact algebraic identity at every single point $x$ inspected by the limit.
3. **Geometric Interpretation (Removable Discontinuity / Hole in the Graph):**
   The graph of $f(x) = \frac{x^2-4x+3}{x-3}$ is the straight line $y = x - 1$ with a single missing point (a "hole" or **removable discontinuity**) at $(3, 2)$. Whether that point is missing ($3 \notin D_f$) or moved to some other height (e.g., setting $f(3) = 100$), a traveler walking along the line toward $x = 3$ from either side still approaches the height $y = 2$.

---

## 4. Verification and Consistency Checks

### Numerical Check Near $x = 3$
Let us evaluate $f(x) = \frac{x^2-4x+3}{x-3}$ directly from the original unsimplified formula for values of $x$ approaching $3$ from the left ($x < 3$) and from the right ($x > 3$):

| $x$ | Numerator $x^2 - 4x + 3$ | Denominator $x - 3$ | $f(x) = \frac{x^2-4x+3}{x-3}$ | Distance $|f(x) - 2|$ |
| :--- | :--- | :--- | :--- | :--- |
| $2.9$ | $-0.19$ | $-0.1$ | $1.9$ | $0.1$ |
| $2.99$ | $-0.0199$ | $-0.01$ | $1.99$ | $0.01$ |
| $2.999$ | $-0.001999$ | $-0.001$ | $1.999$ | $0.001$ |
| $3.001$ | $+0.002001$ | $+0.001$ | $2.001$ | $0.001$ |
| $3.01$ | $+0.0201$ | $+0.01$ | $2.01$ | $0.01$ |
| $3.1$ | $+0.21$ | $+0.1$ | $2.1$ | $0.1$ |

Both left-hand and right-hand values converge linearly to $2$.

### Independent Substitution Check ($h = x - 3 \to 0$)
Let $h = x - 3$, so $x = 3 + h$. As $x \to 3$ with $x \neq 3$, we have $h \to 0$ with $h \neq 0$. Substituting $x = 3 + h$ into the numerator gives:
$$(3+h)^2 - 4(3+h) + 3 = (9 + 6h + h^2) - (12 + 4h) + 3 = 2h + h^2 = h(2 + h).$$
Dividing by $x - 3 = h \neq 0$ yields:
$$\lim_{x\to 3}\frac{x^2-4x+3}{x-3} = \lim_{h\to 0} \frac{h(2 + h)}{h} = \lim_{h\to 0} (2 + h) = 2 + 0 = 2.$$
This independently confirms the result.

### Final Conclusion
$$\boxed{\lim_{x\to3}\frac{x^2-4x+3}{x-3} = 2}$$
