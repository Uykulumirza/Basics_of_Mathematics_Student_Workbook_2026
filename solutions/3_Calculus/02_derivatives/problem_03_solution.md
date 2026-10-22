# Solution to Problem 3: The Product Rule — Why Is It Needed?

## 1. Problem Statement

For
$$f(x)=(x^2+1)e^x$$
compute the derivative. Then compare the correct result with the incorrect idea
$$f'(x)\stackrel{?}{=}(2x)e^x$$
and explain which term is missing.

> **Why this problem:** it teaches the product rule by analyzing a common mistake.

---

## 2. Theoretical Background and Concepts

1. **The Product Rule**: If $u(x)$ and $v(x)$ are differentiable functions, then the product $f(x) = u(x)v(x)$ is differentiable and its derivative is:
   $$\frac{d}{dx}\left[u(x)v(x)\right] = u'(x)v(x) + u(x)v'(x)$$
   In words: the derivative of a product of two functions is the derivative of the first times the second, **plus** the first times the derivative of the second.
2. **Why $(uv)' \neq u'v'$ and $(uv)' \neq u'v$**:
   When $x$ changes by a small increment $\Delta x$, both factors $u(x)$ and $v(x)$ change simultaneously:
   $$\Delta(uv) = (u + \Delta u)(v + \Delta v) - uv = (\Delta u)v + u(\Delta v) + (\Delta u)(\Delta v)$$
   Dividing by $\Delta x$ and taking the limit as $\Delta x \to 0$:
   - $\frac{\Delta u}{\Delta x} v \to u'(x)v(x)$ (rate of change caused by $u$ varying while $v$ is held fixed),
   - $u \frac{\Delta v}{\Delta x} \to u(x)v'(x)$ (rate of change caused by $v$ varying while $u$ is held fixed),
   - $\frac{\Delta u}{\Delta x}\Delta v \to u'(x)\cdot 0 = 0$.
   Ignoring either of the first two terms treats one of the variable factors as if it were a constant.
3. **Derivative of the Natural Exponential Function**:
   $$\frac{d}{dx}\left(e^x\right) = e^x$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify the product structure and compute the derivative

The function
$$f(x) = (x^2 + 1)e^x$$
is the product of two differentiable functions of $x$:
- First factor: $u(x) = x^2 + 1$
- Second factor: $v(x) = e^x$

We compute the derivative of each factor individually:
- By the power and constant rules:
  $$u'(x) = \frac{d}{dx}\left(x^2 + 1\right) = 2x + 0 = 2x$$
- By the exponential derivative rule:
  $$v'(x) = \frac{d}{dx}\left(e^x\right) = e^x$$

Now we apply the **product rule** $f'(x) = u'(x)v(x) + u(x)v'(x)$:
$$f'(x) = (2x)e^x + (x^2 + 1)e^x$$

We can simplify this expression by factoring out the common factor $e^x$:
$$f'(x) = (x^2 + 2x + 1)e^x$$
Recognizing the quadratic factor $x^2 + 2x + 1$ as the perfect square $(x + 1)^2$, we obtain the fully factored form:
$$f'(x) = (x + 1)^2 e^x$$

---

### Step 2: Compare with the incorrect formula and explain the missing term

Let us compare our true derivative with the proposed incorrect formula:
- **Correct derivative**:
  $$f'(x) = \underbrace{2x e^x}_{u'(x)v(x)} + \underbrace{(x^2 + 1)e^x}_{u(x)v'(x)}$$
- **Incorrect formula**:
  $$f'_{\text{wrong}}(x) = (2x)e^x$$

**Which term is missing and why?**
1. **The missing term is $(x^2 + 1)e^x = u(x)v'(x)$.**
2. **Conceptual explanation**:
   - The incorrect formula $(2x)e^x$ comes from one of two common misconceptions:
     - **Misconception A**: Treating $e^x$ as a constant multiplier, differentiating only $(x^2+1)$ to get $2x$, and leaving $e^x$ untouched. However, $e^x$ is **not a constant**—it depends on $x$ and grows exponentially as $x$ increases.
     - **Misconception B**: Falsely assuming $(uv)' = u'v'$, since $\frac{d}{dx}(x^2+1) = 2x$ and $\frac{d}{dx}(e^x) = e^x$ happen to have $(2x)e^x$ as the product of their individual derivatives $u'(x)v'(x)$.
   - In reality, as $x$ varies, $f(x) = (x^2+1)e^x$ changes for **two independent reasons**:
     1. The polynomial factor $(x^2+1)$ changes at rate $u'(x) = 2x$, scaled by the current value of $e^x$, giving $2xe^x$.
     2. The exponential factor $e^x$ changes at rate $v'(x) = e^x$, scaled by the current value of $(x^2+1)$, giving $(x^2+1)e^x$.
   - Omitting $(x^2+1)e^x$ ignores the growth of the exponential factor $e^x$.

---

## 4. Verification and Consistency Checks

1. **Concrete Counterexample at $x = 0$**:
   Let us inspect the behavior of $f(x) = (x^2 + 1)e^x$ at $x = 0$:
   - The incorrect formula predicts a slope of $f'_{\text{wrong}}(0) = 2(0)e^0 = 0$ (a horizontal tangent).
   - However, near $x = 0$, $x^2 + 1 \approx 1$, so $f(x) \approx 1 \cdot e^x = e^x$, which is strictly increasing with slope $1$ at $x = 0$!
   - Indeed, our correct formula gives:
     $$f'(0) = (0 + 1)^2 e^0 = 1 \cdot 1 = 1$$
   - Checking with the difference quotient for $h = 0.001$ at $x = 0$:
     $$\frac{f(0.001) - f(0)}{0.001} = \frac{(1.000001)e^{0.001} - 1}{0.001} \approx \frac{1.0010015 - 1}{0.001} \approx 1.0015 \approx 1$$
     This decisively refutes the incorrect formula $(2x)e^x$ and confirms the necessity of the missing term $(x^2+1)e^x$.
2. **Sign Analysis**:
   Since $(x+1)^2 \ge 0$ and $e^x > 0$ for all $x \in \mathbb{R}$, the true derivative $f'(x) = (x+1)^2 e^x \ge 0$ everywhere (vanishing only at the inflection point $x = -1$), meaning $f(x)$ is strictly increasing on $\mathbb{R}$.
