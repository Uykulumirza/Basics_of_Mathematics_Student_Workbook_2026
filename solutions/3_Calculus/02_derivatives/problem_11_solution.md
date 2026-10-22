# Solution to Problem 11: Derivative from the Definition

## 1. Problem Statement

Using only
$$f'(x)=\lim_{h\to0}\frac{f(x+h)-f(x)}h,$$
find the derivative of $f(x)=x^2$. Compare the result with the power rule and indicate where the limit is used in the calculation.

> **Why this problem:** it shows the origin of the power rule and the direct connection between the derivative and a limit.

---

## 2. Theoretical Background and Concepts

1. **Limit Definition of the Derivative**:
   A function $f$ is differentiable at $x$ if the following limit of the **difference quotient** exists and is finite:
   $$f'(x) = \lim_{h \to 0} \frac{f(x + h) - f(x)}{h}$$
   - Geometrically, for $h \neq 0$, the difference quotient $\frac{f(x+h) - f(x)}{h}$ is the **slope of the secant line** passing through the two points $(x, f(x))$ and $(x + h, f(x + h))$ on the graph of $f$.
   - As $h \to 0$ (with $h \neq 0$), the second point $(x + h, f(x + h))$ slides along the curve toward $(x, f(x))$, and the secant slope approaches the **slope of the tangent line**, $f'(x)$.
2. **Resolving the $\left[\frac{0}{0}\right]$ Indeterminate Form**:
   Directly substituting $h = 0$ into $\frac{f(x+h)-f(x)}{h}$ always produces the indeterminate form $\frac{0}{0}$. Because the limit $\lim_{h \to 0}$ only examines values of $h$ **approaching** $0$ with $h \neq 0$, we can algebraically expand and cancel the common factor $h$ in the numerator and denominator before evaluating the limit by continuity.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Set up the difference quotient for $f(x) = x^2$

For $f(x) = x^2$, we first evaluate the function at the shifted input $x + h$:
$$f(x + h) = (x + h)^2$$

Substituting $f(x + h) = (x + h)^2$ and $f(x) = x^2$ into the limit definition of the derivative gives:
$$f'(x) = \lim_{h \to 0} \frac{(x + h)^2 - x^2}{h}$$

---

### Step 2: Expand and simplify the difference quotient for $h \neq 0$

1. **Expand the square $(x + h)^2$** using the binomial identity $(a + b)^2 = a^2 + 2ab + b^2$:
   $$f'(x) = \lim_{h \to 0} \frac{\left(x^2 + 2xh + h^2\right) - x^2}{h}$$

2. **Cancel $x^2 - x^2$ in the numerator**:
   $$f'(x) = \lim_{h \to 0} \frac{2xh + h^2}{h}$$

3. **Factor out $h$ in the numerator and divide by $h$ (valid because $h \neq 0$ inside the limit $h \to 0$)**:
   $$f'(x) = \lim_{h \to 0} \frac{h(2x + h)}{h} = \lim_{h \to 0} (2x + h)$$

---

### Step 3: Evaluate the limit and indicate the exact step where the limit is used

Now that the indeterminate division by $h$ has been removed, the simplified expression $2x + h$ is a linear (continuous) function of $h$ (treating $x$ as fixed while $h$ varies). We now **evaluate the limit as $h \to 0$** by direct substitution of $h = 0$:
$$f'(x) = \lim_{h \to 0} (2x + h) = 2x + 0 = 2x$$

**Where the limit is used in the calculation**:
1. **Implicitly during cancellation**: In Step 2, canceling $\frac{h}{h} = 1$ in $\frac{h(2x+h)}{h} = 2x + h$ is justified **precisely because** the definition of $\lim_{h \to 0}$ restricts $h$ to punctured neighborhoods of $0$ ($h \neq 0$).
2. **Explicitly at the final transition**: The limit operation is explicitly executed in Step 3 when we pass from $\lim_{h \to 0}(2x + h)$ to $2x$, where the perturbation term $+h$ (representing the difference between the secant slope $2x + h$ and the tangent slope $2x$) vanishes as $h \to 0$.

---

### Step 4: Compare the result with the power rule

According to the **power rule** $\frac{d}{dx}(x^n) = nx^{n-1}$ with $n = 2$:
$$\frac{d}{dx}\left(x^2\right) = 2x^{2-1} = 2x^1 = 2x$$

**Comparison**:
- Both the limit definition and the power rule yield the exact same derivative: $f'(x) = 2x$.
- More importantly, our limit calculation reveals **why** the power rule works for $n = 2$: in the binomial expansion $(x + h)^2 = x^2 + 2xh + h^2$,
  - the $0$-th order term $x^2$ cancels with $-f(x) = -x^2$,
  - the $1$-st order term in $h$, namely $2xh$, has coefficient $2x$, which survives after dividing by $h$,
  - and the higher-order term $h^2$ becomes $h$ after dividing by $h$, which goes to $0$ when the limit $\lim_{h \to 0}$ is taken.

---

## 4. Verification and Consistency Checks

1. **Generalization to $x^n$ (Connection to Binomial Theorem)**:
   For any positive integer $n$, $(x + h)^n = x^n + nx^{n-1}h + \binom{n}{2}x^{n-2}h^2 + \dots + h^n$. Subtracting $x^n$, dividing by $h \neq 0$, and taking $\lim_{h \to 0}$ leaves only the coefficient of $h^1$, which is $nx^{n-1}$. Our derivation for $n = 2$ is the foundational base case of this general proof.
2. **Geometric Area Interpretation**:
   If a square of side length $x$ (area $x^2$) has its side increased by a tiny width $h$, the added area $\Delta(x^2) = (x+h)^2 - x^2$ consists of two thin rectangles of area $x \cdot h$ each (total $2xh$) plus one tiny corner square of area $h^2$. Dividing by the width $h$ gives $2x + h$, and as the strip width $h \to 0$, the tiny corner square's contribution $h$ vanishes, leaving the instantaneous rate of area growth $2x$.
