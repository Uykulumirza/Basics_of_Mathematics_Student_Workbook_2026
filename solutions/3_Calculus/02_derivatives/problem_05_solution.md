# Solution to Problem 5: The Chain Rule as Working Through Layers

## 1. Problem Statement

For
$$f(x)=(3x^2-2x+1)^5$$
identify the inner and outer functions, compute their derivatives, and combine the result according to the chain rule. Explain the origin of the additional factor.

> **Why this problem:** it teaches how to recognize the structure of a composition instead of memorizing the rule as a meaningless pattern.

---

## 2. Theoretical Background and Concepts

1. **Composite Functions**: A function $f(x)$ is a composition $f(x) = (g \circ u)(x) = g(u(x))$ when evaluating $f(x)$ requires two sequential steps:
   - First, apply the **inner function** $u = u(x)$ to the input $x$.
   - Second, apply the **outer function** $y = g(u)$ to the intermediate result $u$.
2. **The Chain Rule**: If $u = u(x)$ is differentiable at $x$ and $y = g(u)$ is differentiable at $u = u(x)$, then the composite function $f(x) = g(u(x))$ is differentiable at $x$, and its derivative is:
   $$f'(x) = g'(u(x)) \cdot u'(x) \qquad \text{or in Leibniz notation:} \qquad \frac{dy}{dx} = \frac{dy}{du} \cdot \frac{du}{dx}$$
3. **Generalized Power Rule (Chain Rule Special Case)**: When the outer function is a power $g(u) = u^n$, the chain rule states:
   $$\frac{d}{dx}\left[\left(u(x)\right)^n\right] = n\left(u(x)\right)^{n-1} \cdot u'(x)$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify the inner and outer functions

To evaluate $f(x) = (3x^2 - 2x + 1)^5$ for a given $x$, we first compute the quadratic polynomial inside the parentheses, and then raise that result to the $5$-th power. Thus, the two layers are:
- **Inner function**:
  $$u = u(x) = 3x^2 - 2x + 1$$
- **Outer function**:
  $$y = g(u) = u^5$$

Checking the composition: $g(u(x)) = \left(u(x)\right)^5 = (3x^2 - 2x + 1)^5 = f(x)$.

---

### Step 2: Compute the derivatives of the outer and inner functions

1. **Derivative of the outer function with respect to $u$**:
   Applying the power rule to $g(u) = u^5$ with respect to its argument $u$:
   $$g'(u) = \frac{dy}{du} = \frac{d}{du}\left(u^5\right) = 5u^4$$
   Substituting the inner expression $u = 3x^2 - 2x + 1$ back in gives the outer derivative evaluated at $u(x)$:
   $$g'(u(x)) = 5(3x^2 - 2x + 1)^4$$

2. **Derivative of the inner function with respect to $x$**:
   Applying the power, constant multiple, and sum rules to $u(x) = 3x^2 - 2x + 1$:
   $$u'(x) = \frac{du}{dx} = \frac{d}{dx}\left(3x^2 - 2x + 1\right) = 3(2x) - 2(1) + 0 = 6x - 2$$

---

### Step 3: Combine the results using the chain rule

By the **chain rule**, $f'(x) = g'(u(x)) \cdot u'(x)$:
$$f'(x) = 5(3x^2 - 2x + 1)^4 \cdot (6x - 2)$$

We can factor a $2$ out of the linear factor $(6x - 2) = 2(3x - 1)$ and multiply $5 \cdot 2 = 10$ to write the derivative in clean factored form:
$$f'(x) = 10(3x - 1)(3x^2 - 2x + 1)^4$$

---

### Step 4: Explain the origin of the additional factor $(6x - 2)$

Why can we not simply write $5(3x^2 - 2x + 1)^4$, and why must the additional factor $u'(x) = 6x - 2$ appear?

- **Sensitivity / Rate-of-Change Explanation**:
  The expression $g'(u) = 5u^4 = 5(3x^2 - 2x + 1)^4$ measures how fast the output $y = u^5$ changes **per unit change in the intermediate quantity $u$** ($\frac{dy}{du}$), **not** per unit change in $x$.
  However, $u = 3x^2 - 2x + 1$ does not change at the same speed as $x$: when $x$ changes by a small amount $\Delta x$, the intermediate variable $u$ changes by approximately:
  $$\Delta u \approx u'(x)\,\Delta x = (6x - 2)\,\Delta x$$
  In turn, that change $\Delta u$ produces a change in the final output $y$:
  $$\Delta y \approx g'(u)\,\Delta u \approx 5u^4 \cdot (6x - 2)\,\Delta x$$
  Dividing by $\Delta x$ and taking the limit as $\Delta x \to 0$ shows that the overall rate of change $\frac{dy}{dx}$ is the **product** of the two local magnification rates:
  $$\frac{dy}{dx} = \frac{dy}{du} \cdot \frac{du}{dx} = 5(3x^2 - 2x + 1)^4 (6x - 2)$$
  Thus, the factor $(6x - 2)$ accounts for the local rate at which the inner polynomial stretches, compresses, or reverses changes in $x$ before the $5$-th power acts on it.

---

## 4. Verification and Consistency Checks

1. **Leading Term (Asymptotic) Check**:
   - If we expanded $f(x) = (3x^2 - 2x + 1)^5$ completely, its highest-degree term would be $(3x^2)^5 = 3^5 x^{10} = 243x^{10}$.
   - Differentiating this leading term gives $\frac{d}{dx}(243x^{10}) = 2430x^9$.
   - Now check the leading term of our derivative $f'(x) = 5(3x^2 - 2x + 1)^4(6x - 2)$:
     $$5(3x^2)^4(6x) = 5(81x^8)(6x) = 30 \cdot 81 x^9 = 2430x^9$$
     The leading coefficients and degrees match identically.
2. **Evaluation at $x = 0$ (Linear Term Check)**:
   - Using the binomial expansion near $x = 0$: $(1 + (-2x + 3x^2))^5 = 1 + 5(-2x + 3x^2) + \dots = 1 - 10x + O(x^2)$, so $f'(0)$ must be $-10$.
   - Evaluating our derivative formula at $x = 0$:
     $$f'(0) = 5(0 - 0 + 1)^4(0 - 2) = 5(1)^4(-2) = -10$$
     (Notice that without the inner derivative factor $6x - 2$, one would falsely get $5(1)^4 = +5$, missing even the negative sign!)
3. **Stationary Point Check**:
   Since $3x^2 - 2x + 1 = 3\left(x - \frac{1}{3}\right)^2 + \frac{2}{3} > 0$ for all $x \in \mathbb{R}$, $f'(x) = 0$ if and only if the inner derivative $6x - 2 = 0 \iff x = \frac{1}{3}$, which is the vertex of the inner parabola $3x^2 - 2x + 1$.
