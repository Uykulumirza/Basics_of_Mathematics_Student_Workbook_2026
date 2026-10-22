# Solution to Problem 2: Powers, Roots, and the Domain

## 1. Problem Statement

Compute
$$\int\left(2\sqrt{x}+\frac{3}{x^2}-x^{1/3}\right)\,dx.$$
First rewrite the terms as powers, determine the domain of the original expression, and verify the result by differentiation.

> **Why this problem:** it reinforces the power rule and reminds the student to keep track of the domain.

---

## 2. Theoretical Background and Concepts

### Conversion of Radicals and Reciprocals to Power Form
To apply the standard power rule of integration, algebraic expressions involving roots and fractions of $x$ are rewritten in the standard power form $x^p$ using the laws of exponents:
$$\sqrt[n]{x^m} = x^{m/n}, \qquad \frac{1}{x^p} = x^{-p} \quad (x \neq 0).$$

### Power Rule for Indefinite Integrals
For any real constant exponent $p \neq -1$, on any interval where $x^p$ is defined and continuous:
$$\int x^p\,dx = \frac{x^{p+1}}{p+1} + C, \quad C \in \mathbb{R}.$$

### Domain Considerations
An integrand $f(x) = f_1(x) + f_2(x) + f_3(x)$ is defined on the intersection of the domains of its constituent terms:
$$\operatorname{Dom}(f) = \operatorname{Dom}(f_1) \cap \operatorname{Dom}(f_2) \cap \operatorname{Dom}(f_3).$$
When an indefinite integral is computed, the resulting antiderivative is valid as an antiderivative of $f$ only on the connected intervals contained within $\operatorname{Dom}(f)$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Determining the Domain of the Original Expression
Let the integrand be
$$f(x) = 2\sqrt{x} + \frac{3}{x^2} - x^{1/3}.$$
We examine the domain restriction imposed by each term over the real numbers $\mathbb{R}$:
1. **First term ($2\sqrt{x}$):** The square root $\sqrt{x}$ is defined in $\mathbb{R}$ if and only if the radicand is non-negative:
   $$x \ge 0 \implies x \in [0, \infty).$$
2. **Second term ($\frac{3}{x^2}$):** Division by zero is undefined, so the denominator $x^2$ must be non-zero:
   $$x^2 \neq 0 \iff x \neq 0 \implies x \in (-\infty, 0) \cup (0, \infty).$$
3. **Third term ($-x^{1/3} = -\sqrt[3]{x}$):** The real cube root is defined for all real numbers ( note that in standard calculus conventions, when combined with $x > 0$ from the first two terms, fractional powers $x^{1/3}$ are unambiguously defined on $(0, \infty)$).

Taking the intersection of all three conditions:
$$\operatorname{Dom}(f) = [0, \infty) \cap \big((-\infty, 0) \cup (0, \infty)\big) \cap \mathbb{R} = (0, \infty).$$
Thus, the domain of the integrand is the single open interval:
$$D = (0, \infty) = \{x \in \mathbb{R} : x > 0\}.$$
Because $D = (0, \infty)$ is a single connected interval, the family of antiderivatives on $D$ is parameterized by a single constant $C \in \mathbb{R}$.

### Step 2: Rewriting the Integrand in Power Form
For $x \in (0, \infty)$, we rewrite each term of the integrand as a constant multiple of $x^p$:
- $2\sqrt{x} = 2x^{1/2}$
- $\frac{3}{x^2} = 3x^{-2}$
- $-x^{1/3}$ is already in power form with $p = \frac{1}{3}$

Therefore, the integral becomes:
$$\int\left(2\sqrt{x}+\frac{3}{x^2}-x^{1/3}\right)\,dx = \int\left(2x^{1/2} + 3x^{-2} - x^{1/3}\right)\,dx.$$

### Step 3: Integrating Term-by-Term Using the Power Rule
Since none of the exponents $\left(\frac{1}{2}, -2, \frac{1}{3}\right)$ is equal to $-1$, we recognize that **direct term-by-term integration via the power rule** $\int x^p\,dx = \frac{x^{p+1}}{p+1}$ applies to each component:

1. **First term ($p = \frac{1}{2}$):**
   $$\int 2x^{1/2}\,dx = 2 \cdot \frac{x^{\frac{1}{2}+1}}{\frac{1}{2}+1} = 2 \cdot \frac{x^{3/2}}{\frac{3}{2}} = 2 \cdot \frac{2}{3}x^{3/2} = \frac{4}{3}x^{3/2}.$$

2. **Second term ($p = -2$):**
   $$\int 3x^{-2}\,dx = 3 \cdot \frac{x^{-2+1}}{-2+1} = 3 \cdot \frac{x^{-1}}{-1} = -3x^{-1} = -\frac{3}{x}.$$

3. **Third term ($p = \frac{1}{3}$):**
   $$\int \left(-x^{1/3}\right)\,dx = -\frac{x^{\frac{1}{3}+1}}{\frac{1}{3}+1} = -\frac{x^{4/3}}{\frac{4}{3}} = -\frac{3}{4}x^{4/3}.$$

Combining all three terms and adding the constant of integration $C \in \mathbb{R}$ gives the general antiderivative on $(0, \infty)$:
$$F(x) = \frac{4}{3}x^{3/2} - 3x^{-1} - \frac{3}{4}x^{4/3} + C = \frac{4}{3}x\sqrt{x} - \frac{3}{x} - \frac{3}{4}x\sqrt[3]{x} + C, \quad x \in (0, \infty).$$

### Step 4: Verification by Differentiation
We differentiate $F(x) = \frac{4}{3}x^{3/2} - 3x^{-1} - \frac{3}{4}x^{4/3} + C$ on $(0, \infty)$ term by term using $\frac{d}{dx}(x^q) = qx^{q-1}$:
$$\begin{aligned}
F'(x) &= \frac{d}{dx}\left(\frac{4}{3}x^{3/2} - 3x^{-1} - \frac{3}{4}x^{4/3} + C\right) \\
&= \frac{4}{3} \cdot \frac{3}{2}x^{\frac{3}{2}-1} - 3(-1)x^{-1-1} - \frac{3}{4} \cdot \frac{4}{3}x^{\frac{4}{3}-1} + 0 \\
&= 2x^{1/2} + 3x^{-2} - x^{1/3} \\
&= 2\sqrt{x} + \frac{3}{x^2} - x^{1/3}.
\end{aligned}$$
This matches the original integrand identically for all $x \in (0, \infty)$.

---

## 4. Verification and Consistency Checks

1. **Sign Check on the Reciprocal Term:** A common error when integrating $\frac{3}{x^2} = 3x^{-2}$ is to write $\frac{3}{3}x^{-3}$ instead of adding $1$ to the negative exponent ($-2 + 1 = -1$). Differentiating $-\frac{3}{x} = -3x^{-1}$ yields $(-3)(-1)x^{-2} = +\frac{3}{x^2}$, confirming both the exponent $-1$ and the minus sign in $-\frac{3}{x}$.
2. **Domain Consistency Check:** Notice that while $F(x) = \frac{4}{3}x^{3/2} - \frac{3}{x} - \frac{3}{4}x^{4/3} + C$ is also undefined at $x = 0$ (due to $-\frac{3}{x}$) and for $x < 0$ (due to $x^{3/2}$), even if a single term like $x^{3/2}$ were defined at $x = 0$, the complete antiderivative $F(x)$ and its derivative $F'(x)$ are only valid on the open interval $(0, \infty)$.
