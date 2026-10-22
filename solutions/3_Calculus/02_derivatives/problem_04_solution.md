# Solution to Problem 4: A Quotient and Domain Control

## 1. Problem Statement

For
$$f(x)=\frac{x^2+1}{x-1}$$
determine the domain, compute the derivative, simplify the result, and explain why the restriction $x\neq1$ remains important.

> **Why this problem:** it practices the quotient rule together with domain control.

---

## 2. Theoretical Background and Concepts

1. **Domain of a Rational Function**: A rational function $f(x) = \frac{u(x)}{v(x)}$, where $u(x)$ and $v(x)$ are polynomials, is defined for all real numbers $x$ where the denominator is non-zero:
   $$\operatorname{Dom}(f) = \{x \in \mathbb{R} : v(x) \neq 0\}$$
2. **The Quotient Rule**: If $u(x)$ and $v(x)$ are differentiable at $x$ and $v(x) \neq 0$, then the quotient $f(x) = \frac{u(x)}{v(x)}$ is differentiable at $x$, and its derivative is given by:
   $$f'(x) = \frac{d}{dx}\left[\frac{u(x)}{v(x)}\right] = \frac{u'(x)v(x) - u(x)v'(x)}{\left[v(x)\right]^2}$$
   *(Note the minus sign in the numerator: the derivative of the numerator $u'(x)$ multiplied by the denominator $v(x)$ comes first.)*
3. **Domain Preservation and Vertical Asymptotes**: A derivative $f'(x)$ can only exist at points belonging to the domain of $f$. Furthermore, a point where $v(x) = 0$ and $u(x) \neq 0$ produces a vertical asymptote, splitting the graph and the domain into separate intervals.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Determine the domain of $f$

The numerator $u(x) = x^2 + 1$ and the denominator $v(x) = x - 1$ are polynomials defined for all $x \in \mathbb{R}$. The fraction is undefined if and only if the denominator equals zero:
$$x - 1 = 0 \iff x = 1$$

Therefore, the domain of $f$ consists of all real numbers except $1$:
$$\operatorname{Dom}(f) = \mathbb{R} \setminus \{1\} = (-\infty, 1) \cup (1, \infty)$$

---

### Step 2: Compute the derivative using the quotient rule

For any $x \neq 1$, we identify the numerator and denominator functions and their derivatives:
- Numerator: $u(x) = x^2 + 1 \implies u'(x) = \frac{d}{dx}(x^2 + 1) = 2x$
- Denominator: $v(x) = x - 1 \implies v'(x) = \frac{d}{dx}(x - 1) = 1$

Applying the **quotient rule** $f'(x) = \frac{u'(x)v(x) - u(x)v'(x)}{[v(x)]^2}$:
$$f'(x) = \frac{(2x)(x - 1) - (x^2 + 1)(1)}{(x - 1)^2}$$

---

### Step 3: Simplify the derivative expression

We expand the products in the numerator (being careful to distribute the minus sign across all terms of $x^2 + 1$):
$$f'(x) = \frac{2x^2 - 2x - x^2 - 1}{(x - 1)^2}$$

Combining like terms ($2x^2 - x^2 = x^2$) in the numerator gives the simplified derivative:
$$f'(x) = \frac{x^2 - 2x - 1}{(x - 1)^2} \quad \text{for } x \neq 1$$

---

### Step 4: Explain why the restriction $x \neq 1$ remains important

The restriction $x \neq 1$ remains essential for three closely related mathematical reasons:
1. **Algebraic Undefinedness of $f(1)$ and $f'(1)$**:
   At $x = 1$, both the original denominator $(x - 1)$ and the derivative's denominator $(x - 1)^2$ equal zero, while their numerators equal $1^2 + 1 = 2 \neq 0$ and $1^2 - 2(1) - 1 = -2 \neq 0$, respectively. Neither $f(1)$ nor $f'(1)$ exists as a real number:
   $$\operatorname{Dom}(f') = \mathbb{R} \setminus \{1\} = (-\infty, 1) \cup (1, \infty)$$
2. **Geometric Singularity (Vertical Asymptote)**:
   As $x \to 1^-$, $f(x) \to -\infty$, and as $x \to 1^+$, $f(x) \to +\infty$. The line $x = 1$ is a **vertical asymptote**, so there is no point on the graph at $x = 1$ at which a tangent line could even be drawn.
3. **Topological Separation of Intervals (Monotonicity Trap)**:
   Notice that near $x = 1$, the numerator of $f'(x)$ is $x^2 - 2x - 1 \approx -2 < 0$, while $(x - 1)^2 > 0$, so $f'(x) < 0$ on $(1 - \sqrt{2}, 1)$ and also $f'(x) < 0$ on $(1, 1 + \sqrt{2})$. Because $x = 1$ separates the domain into two disconnected intervals, we **cannot** say that $f$ is decreasing on the combined interval $(1 - \sqrt{2}, 1 + \sqrt{2})$. Indeed, if we pick $x_1 = 0.5 < 1 < x_2 = 1.5$, we have $f(0.5) = -2.5 < f(1.5) = 6.5$, because the function jumps across the vertical asymptote at $x = 1$. Keeping track of $x \neq 1$ prevents false conclusions about global monotonicity.

---

## 4. Verification and Consistency Checks

1. **Verification by Polynomial Long Division (Algebraic Rewriting)**:
   We can rewrite $f(x)$ by dividing $x^2 + 1$ by $x - 1$ for $x \neq 1$:
   $$f(x) = \frac{(x^2 - 1) + 2}{x - 1} = \frac{(x - 1)(x + 1) + 2}{x - 1} = x + 1 + \frac{2}{x - 1} = x + 1 + 2(x - 1)^{-1}$$
   Differentiating this rewritten form term by term using the power rule gives:
   $$f'(x) = 1 + 0 + 2(-1)(x - 1)^{-2} = 1 - \frac{2}{(x - 1)^2}$$
   Putting this over the common denominator $(x - 1)^2$:
   $$f'(x) = \frac{(x - 1)^2 - 2}{(x - 1)^2} = \frac{x^2 - 2x + 1 - 2}{(x - 1)^2} = \frac{x^2 - 2x - 1}{(x - 1)^2}$$
   This matches our quotient rule calculation identically.
2. **Point Check at $x = 0$ and $x = 2$**:
   - At $x = 0$: $f'(0) = \frac{0 - 0 - 1}{(0 - 1)^2} = -1$. Using $f'(x) = 1 - \frac{2}{(x-1)^2}$, we also get $1 - \frac{2}{1} = -1$.
   - At $x = 2$: $f'(2) = \frac{4 - 4 - 1}{(2 - 1)^2} = -1$. Using $f'(x) = 1 - \frac{2}{(x-1)^2}$, we also get $1 - \frac{2}{1} = -1$.
