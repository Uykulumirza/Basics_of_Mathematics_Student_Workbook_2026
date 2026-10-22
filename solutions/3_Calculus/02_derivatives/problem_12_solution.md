# Solution to Problem 12: Several Rules at Once

## 1. Problem Statement

For
$$f(x)=(x^2+1)^3e^x$$
compute the derivative. Before calculating, write down a plan: which rule applies to the whole expression and which rule applies to one of its factors. Finally, organize the result by factoring out common factors.

> **Why this problem:** it practices the order of decisions when combining familiar differentiation rules.

---

## 2. Theoretical Background and Concepts

1. **Top-Down Structural Analysis of Expressions**:
   When differentiating an expression that combines multiple operations (products, quotients, powers, compositions), we always determine the **top-level rule** from the **last operation performed** when evaluating the expression:
   - In $f(x) = (x^2 + 1)^3 e^x$, the final operation connects $(x^2 + 1)^3$ and $e^x$ by **multiplication**. Therefore, the **Product Rule** governs the whole expression.
   - Inside the first factor $u(x) = (x^2 + 1)^3$, the outer operation is raising the inner polynomial $x^2 + 1$ to the $3$-rd power. Therefore, the **Chain Rule** governs the differentiation of that factor.
2. **Product Rule and Chain Rule Combined**:
   If $f(x) = u(x)v(x)$ with $u(x) = [w(x)]^n$, then:
   $$f'(x) = u'(x)v(x) + u(x)v'(x) = \left[n\left(w(x)\right)^{n-1} w'(x)\right]v(x) + \left(w(x)\right)^n v'(x)$$
3. **Factoring Derivative Expressions**:
   Factoring out the highest common powers of shared factors converts a sum of bulky products into a compact product, making it trivial to identify roots (critical points) and signs of $f'(x)$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Write the differentiation plan before calculating

Before performing any algebraic calculations, we establish a two-stage plan:
1. **Rule for the whole expression (Top-Level Rule — Product Rule)**:
   The function $f(x) = (x^2 + 1)^3 e^x$ is a **product** of two factors:
   $$u(x) = (x^2 + 1)^3 \qquad \text{and} \qquad v(x) = e^x$$
   Therefore, we apply the **Product Rule** to the whole expression:
   $$f'(x) = u'(x)v(x) + u(x)v'(x)$$
2. **Rule for the first factor (Sub-Level Rule — Chain Rule)**:
   While $v(x) = e^x$ differentiates directly to $v'(x) = e^x$, the first factor $u(x) = (x^2 + 1)^3$ is a **composition** of an outer cubic power $g(w) = w^3$ and an inner quadratic polynomial $w(x) = x^2 + 1$. Therefore, we apply the **Chain Rule** (and Power Rule) to compute $u'(x)$.
3. **Final Organization (Algebraic Factoring)**:
   Once $f'(x) = u'(x)v(x) + u(x)v'(x)$ is assembled, both terms will share the common factors $(x^2 + 1)^2$ and $e^x$. We will factor out $(x^2 + 1)^2 e^x$ and simplify the remaining polynomial factor.

---

### Step 2: Execute the plan to compute $u'(x)$, $v'(x)$, and $f'(x)$

1. **Differentiate the first factor $u(x) = (x^2 + 1)^3$ using the Chain Rule**:
   - Outer function: $w^3 \implies$ derivative with respect to $w$ is $3w^2 = 3(x^2 + 1)^2$.
   - Inner function: $w(x) = x^2 + 1 \implies$ derivative with respect to $x$ is $w'(x) = 2x$.
   Multiplying the outer and inner derivatives gives:
   $$u'(x) = 3(x^2 + 1)^2 \cdot \frac{d}{dx}(x^2 + 1) = 3(x^2 + 1)^2 (2x) = 6x(x^2 + 1)^2$$

2. **Differentiate the second factor $v(x) = e^x$**:
   $$v'(x) = \frac{d}{dx}\left(e^x\right) = e^x$$

3. **Assemble $f'(x)$ using the Product Rule**:
   Substituting $u(x)$, $u'(x)$, $v(x)$, and $v'(x)$ into $f'(x) = u'(x)v(x) + u(x)v'(x)$:
   $$f'(x) = 6x(x^2 + 1)^2 e^x + (x^2 + 1)^3 e^x$$

---

### Step 3: Organize the result by factoring out common factors

Inspect the two terms in the sum:
$$f'(x) = \underbrace{6x \cdot (x^2 + 1)^2 \cdot e^x}_{\text{Term 1}} + \underbrace{(x^2 + 1) \cdot (x^2 + 1)^2 \cdot e^x}_{\text{Term 2}}$$

Both terms contain the common factor $(x^2 + 1)^2 e^x$. Factoring $(x^2 + 1)^2 e^x$ out to the front:
$$f'(x) = (x^2 + 1)^2 e^x \left[6x + (x^2 + 1)\right]$$

Arranging the quadratic polynomial inside the brackets in standard descending order of powers of $x$, we obtain the final factored derivative:
$$f'(x) = (x^2 + 1)^2 (x^2 + 6x + 1) e^x$$

---

## 4. Verification and Consistency Checks

1. **Evaluation Check at $x = 0$**:
   - Near $x = 0$, $x^2 + 1 = 1 + O(x^2)$, so $(x^2 + 1)^3 = 1 + 3x^2 + O(x^4)$ has zero linear term at $x = 0$. Thus at $x = 0$, $f(x) = (1 + 3x^2 + \dots)(1 + x + \dots) = 1 + x + O(x^2)$, which means $f'(0)$ must equal $1$.
   - Substituting $x = 0$ into our factored derivative:
     $$f'(0) = (0^2 + 1)^2 (0^2 + 6(0) + 1) e^0 = (1)^2 (1) (1) = 1$$
2. **Verification by Expanding First (Alternative Method)**:
   If we expand $(x^2 + 1)^3 = x^6 + 3x^4 + 3x^2 + 1$, then $f(x) = (x^6 + 3x^4 + 3x^2 + 1)e^x$. Using the formula $\frac{d}{dx}[P(x)e^x] = [P(x) + P'(x)]e^x$:
   $$P(x) + P'(x) = (x^6 + 3x^4 + 3x^2 + 1) + (6x^5 + 12x^3 + 6x) = x^6 + 6x^5 + 3x^4 + 12x^3 + 3x^2 + 6x + 1$$
   Expanding our factored result $(x^2 + 1)^2(x^2 + 6x + 1) = (x^4 + 2x^2 + 1)(x^2 + 6x + 1)$:
   $$(x^4 + 2x^2 + 1)(x^2 + 1) + 6x(x^4 + 2x^2 + 1) = (x^6 + 3x^4 + 3x^2 + 1) + (6x^5 + 12x^3 + 6x)$$
   The two polynomials match term for term, confirming both our differentiation and our factoring.
