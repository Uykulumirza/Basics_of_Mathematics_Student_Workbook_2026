# Solution to Problem 2: Powers, Roots, and the Domain

## 1. Problem Statement

For
$$f(x)=2\sqrt{x}-\frac{3}{x^2}+x^{3/2}$$
1. rewrite the function using powers,
2. determine the domain,
3. compute the derivative,
4. compare the domain of the function with the domain of its derivative.

> **Why this problem:** it teaches how to rewrite different forms so that the power rule can be applied and how to keep track of the domain.

---

## 2. Theoretical Background and Concepts

1. **Laws of Rational and Negative Exponents**:
   - A square root (and more generally an $n$-th root) can be written as a fractional power:
     $$\sqrt{x} = x^{1/2}, \qquad x^{m/n} = \sqrt[n]{x^m} = \left(\sqrt[n]{x}\right)^m \quad (\text{for } x \ge 0 \text{ when } n \text{ is even})$$
   - A reciprocal power can be written using a negative exponent:
     $$\frac{1}{x^k} = x^{-k} \quad (\text{for } x \neq 0)$$
2. **Domain of a Sum of Functions**: The natural domain of $f(x) = g_1(x) + g_2(x) + g_3(x)$ is the **intersection** of the domains of its individual terms:
   $$\operatorname{Dom}(f) = \operatorname{Dom}(g_1) \cap \operatorname{Dom}(g_2) \cap \operatorname{Dom}(g_3)$$
3. **General Power Rule**: For any real exponent $\alpha \in \mathbb{R}$ and $x > 0$,
   $$\frac{d}{dx}\left(x^\alpha\right) = \alpha x^{\alpha - 1}$$
   Rewriting roots and fractions as power terms $c x^\alpha$ allows us to apply the single power rule instead of using separate quotient or radical formulas.

---

## 3. Detailed Step-by-Step Solution

### Part 1: Rewrite the function using powers

We convert each term of $f(x) = 2\sqrt{x} - \frac{3}{x^2} + x^{3/2}$ into the standard power form $c \cdot x^\alpha$:
- First term: $\sqrt{x} = x^{1/2}$, so $2\sqrt{x} = 2x^{1/2}$.
- Second term: $\frac{1}{x^2} = x^{-2}$, so $-\frac{3}{x^2} = -3x^{-2}$.
- Third term: $x^{3/2}$ is already in power form (equivalently, $x^{3/2} = (\sqrt{x})^3 = x\sqrt{x}$).

Therefore, the function rewritten in power form is:
$$f(x) = 2x^{1/2} - 3x^{-2} + x^{3/2}$$

---

### Part 2: Determine the domain of $f$

To find $\operatorname{Dom}(f) \subset \mathbb{R}$, we examine the domain restrictions of each term:
1. **Term $2\sqrt{x} = 2x^{1/2}$**: A real square root is defined if and only if the radicand is non-negative, which requires:
   $$x \ge 0$$
2. **Term $-\frac{3}{x^2} = -3x^{-2}$**: Division by zero is undefined, so the denominator $x^2$ must be non-zero, which requires:
   $$x^2 \neq 0 \iff x \neq 0$$
3. **Term $x^{3/2} = \left(\sqrt{x}\right)^3$**: Since the denominator of the rational exponent $\frac{3}{2}$ is even ($2$), it requires a real square root, so:
   $$x \ge 0$$

Taking the intersection of all three conditions:
$$\{x \in \mathbb{R} : x \ge 0\} \cap \{x \in \mathbb{R} : x \neq 0\} \cap \{x \in \mathbb{R} : x \ge 0\} = \{x \in \mathbb{R} : x > 0\}$$
Thus, the domain of $f$ is the open interval of strictly positive real numbers:
$$\operatorname{Dom}(f) = (0, \infty)$$

---

### Part 3: Compute the derivative $f'(x)$

For all $x \in (0, \infty)$, each power term is differentiable. Using the **linearity of differentiation** and the **general power rule** $\frac{d}{dx}(x^\alpha) = \alpha x^{\alpha - 1}$ on $f(x) = 2x^{1/2} - 3x^{-2} + x^{3/2}$:

$$f'(x) = 2\frac{d}{dx}\left(x^{1/2}\right) - 3\frac{d}{dx}\left(x^{-2}\right) + \frac{d}{dx}\left(x^{3/2}\right)$$

Differentiating each term carefully:
1. **First term** ($\alpha = \frac{1}{2}$):
   $$2 \cdot \left(\frac{1}{2} x^{\frac{1}{2} - 1}\right) = 1 \cdot x^{-1/2} = x^{-1/2} = \frac{1}{\sqrt{x}}$$
2. **Second term** ($\alpha = -2$):
   $$-3 \cdot \left(-2 x^{-2 - 1}\right) = +6 x^{-3} = \frac{6}{x^3}$$
   *(Note carefully that subtracting $1$ from the negative exponent $-2$ yields $-2 - 1 = -3$, not $-1$, and the product of $-3$ and $-2$ is $+6$.)*
3. **Third term** ($\alpha = \frac{3}{2}$):
   $$\frac{3}{2} x^{\frac{3}{2} - 1} = \frac{3}{2} x^{1/2} = \frac{3}{2}\sqrt{x}$$

Combining the three terms, we obtain the derivative in both power form and radical/fraction form:
$$f'(x) = x^{-1/2} + 6x^{-3} + \frac{3}{2}x^{1/2} = \frac{1}{\sqrt{x}} + \frac{6}{x^3} + \frac{3}{2}\sqrt{x}$$

---

### Part 4: Compare the domain of $f$ with the domain of $f'$

Let us find the domain of the derivative expression $f'(x) = \frac{1}{\sqrt{x}} + \frac{6}{x^3} + \frac{3}{2}\sqrt{x}$:
- The term $\frac{1}{\sqrt{x}}$ requires $x \ge 0$ (for the square root) **and** $\sqrt{x} \neq 0$ (since it is in the denominator), which together require $x > 0$.
- The term $\frac{6}{x^3}$ requires $x^3 \neq 0 \iff x \neq 0$.
- The term $\frac{3}{2}\sqrt{x}$ requires $x \ge 0$.

Intersecting these conditions gives:
$$\operatorname{Dom}(f') = (0, \infty)$$

**Comparison and Key Insight**:
- Here, the domain of the function and the domain of its derivative are **identical**:
  $$\operatorname{Dom}(f') = \operatorname{Dom}(f) = (0, \infty)$$
- Why didn't differentiating $\sqrt{x}$ shrink the domain in this problem? If we considered the single term $g(x) = 2\sqrt{x}$ in isolation, its domain would be $[0, \infty)$, whereas its derivative $g'(x) = \frac{1}{\sqrt{x}}$ has domain $(0, \infty)$ because the tangent line to $\sqrt{x}$ becomes vertical at $x = 0$ ($x^{-1/2}$ moves the root into the denominator). However, in our function $f(x)$, the presence of the term $-\frac{3}{x^2}$ **already excluded $x = 0$** from $\operatorname{Dom}(f)$ at the outset. Consequently, moving $x^{1/2}$ to $x^{-1/2}$ in the denominator does not remove any additional points from $\operatorname{Dom}(f)$.

---

## 4. Verification and Consistency Checks

1. **Check by Differentiating the Quotient Term via the Quotient Rule**:
   For the second term $h(x) = -\frac{3}{x^2}$, applying the quotient rule gives:
   $$h'(x) = -\frac{0 \cdot x^2 - 3(2x)}{(x^2)^2} = \frac{6x}{x^4} = \frac{6}{x^3} = 6x^{-3}$$
   This matches the result obtained much more quickly via the power rule on $-3x^{-2}$.
2. **Numerical Evaluation and Sign Check at $x = 1$**:
   - At $x = 1$, $f(1) = 2(1) - 3(1) + 1 = 0$.
   - Evaluating the derivative at $x = 1$:
     $$f'(1) = 1 + 6 + \frac{3}{2} = \frac{17}{2} = 8.5$$
   - In fact, for every $x \in (0, \infty)$, all three terms of $f'(x)$ ($\frac{1}{\sqrt{x}} > 0$, $\frac{6}{x^3} > 0$, and $\frac{3}{2}\sqrt{x} > 0$) are strictly positive. This tells us that $f$ is strictly increasing on its entire domain $(0, \infty)$, which is consistent with $\lim_{x \to 0^+} f(x) = -\infty$ and $\lim_{x \to \infty} f(x) = +\infty$.
