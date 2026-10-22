# Solution to Problem 8: Two Exponential Functions

## 1. Problem Statement

For
$$f(x)=e^{2x-3}+5^x$$
compute the derivative. Explain why the factor $2$ appears in the first term and why $\ln5$ appears in the second.

> **Why this problem:** it organizes two different mechanisms that produce additional factors.

---

## 2. Theoretical Background and Concepts

1. **Derivative of the Natural Exponential Function $e^x$**:
   The natural base $e \approx 2.71828\dots$ is the unique positive base for which the exponential function is its own derivative:
   $$\frac{d}{dx}\left(e^x\right) = e^x \quad (\text{since } \ln e = 1)$$
2. **Chain Rule for $e^{u(x)}$**:
   When the exponent of $e$ is a differentiable function $u(x)$, applying the chain rule to the outer function $g(u) = e^u$ and inner function $u = u(x)$ gives:
   $$\frac{d}{dx}\left(e^{u(x)}\right) = e^{u(x)} \cdot u'(x)$$
3. **Derivative of a General Exponential Function $a^x$ ($a > 0, a \neq 1$)**:
   Using the inverse identity $a = e^{\ln a}$, any exponential function with base $a > 0$ can be rewritten in terms of the natural base $e$:
   $$a^x = \left(e^{\ln a}\right)^x = e^{x \ln a}$$
   Applying the chain rule with inner function $w(x) = (\ln a)x$ (whose derivative with respect to $x$ is the constant $w'(x) = \ln a$) yields:
   $$\frac{d}{dx}\left(a^x\right) = \frac{d}{dx}\left(e^{x \ln a}\right) = e^{x \ln a} \cdot \ln a = a^x \ln a$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the derivative $f'(x)$

The function $f(x) = e^{2x-3} + 5^x$ is the sum of two exponential terms defined for all $x \in \mathbb{R}$. By the **sum rule**, we differentiate each term separately:
$$f'(x) = \frac{d}{dx}\left(e^{2x-3}\right) + \frac{d}{dx}\left(5^x\right)$$

1. **First term $\frac{d}{dx}\left(e^{2x-3}\right)$**:
   This is a composite function with:
   - Outer function: $g(u) = e^u \implies g'(u) = e^u$
   - Inner function: $u(x) = 2x - 3 \implies u'(x) = \frac{d}{dx}(2x - 3) = 2$
   By the **chain rule**:
   $$\frac{d}{dx}\left(e^{2x-3}\right) = e^{2x-3} \cdot \frac{d}{dx}(2x - 3) = e^{2x-3} \cdot 2 = 2e^{2x-3}$$

2. **Second term $\frac{d}{dx}\left(5^x\right)$**:
   This is an exponential function with base $a = 5 > 0$ and simple variable exponent $x$. Using the general exponential derivative rule $\frac{d}{dx}(a^x) = a^x \ln a$:
   $$\frac{d}{dx}\left(5^x\right) = 5^x \ln 5$$

3. **Combine the two derivatives**:
   $$f'(x) = 2e^{2x-3} + 5^x \ln 5$$

---

### Step 2: Explain the two mechanisms producing the factors $2$ and $\ln 5$

Although both terms in $f'(x)$ acquire a constant multiplicative factor upon differentiation, the two factors arise from two distinct aspects of exponential structure—**which actually unify under the chain rule**:

1. **Why the factor $2$ appears in $2e^{2x-3}$ (Non-Unit Coefficient in the Exponent)**:
   - In the first term $e^{2x-3}$, the base is the natural base $e$ (so no logarithm of the base is needed, since $\ln e = 1$), **but the exponent is not simply $x$**; it is the linear function $u(x) = 2x - 3$.
   - Every time $x$ increases by $1$ unit, the exponent $u(x) = 2x - 3$ increases by $2$ units ($\frac{du}{dx} = 2$).
   - By the **chain rule**, the derivative of the outer exponential $e^{2x-3}$ must be multiplied by the rate of change of its inner exponent, $u'(x) = \frac{d}{dx}(2x - 3) = 2$.

2. **Why the factor $\ln 5$ appears in $5^x \ln 5$ (Non-$e$ Base)**:
   - In the second term $5^x$, the exponent is simply $x$ (whose derivative is $1$), **but the base is $5 \neq e$**.
   - While $e^x$ has slope $1$ at $x = 0$, the curve $y = 5^x$ grows faster than $e^x$ because $5 > e$; its slope at $x = 0$ is $\ln 5 \approx 1.6094$.
   - Algebraically, when we express $5^x$ in the natural base $e$ as:
     $$5^x = \left(e^{\ln 5}\right)^x = e^{(\ln 5)x}$$
     we see that having a base of $5$ is equivalent to having a base of $e$ with a **scaled exponent** $w(x) = (\ln 5)x$.
   - Applying the chain rule to $e^{(\ln 5)x}$ multiplies by the derivative of the exponent $\frac{d}{dx}\left[(\ln 5)x\right] = \ln 5$, yielding $e^{(\ln 5)x}\cdot \ln 5 = 5^x \ln 5$.

---

## 4. Verification and Consistency Checks

1. **Alternative Method for $e^{2x-3}$ Using Exponent Laws**:
   We can rewrite the first term using exponent laws before differentiating:
   $$e^{2x-3} = e^{-3} \cdot e^{2x} = e^{-3} \cdot \left(e^2\right)^x$$
   Here $e^{-3}$ is a constant multiple and $a = e^2$ is the base of $\left(e^2\right)^x$. Differentiating using the base-$a$ exponential rule $\frac{d}{dx}(a^x) = a^x \ln a$:
   $$\frac{d}{dx}\left[e^{-3}\left(e^2\right)^x\right] = e^{-3} \left(e^2\right)^x \ln(e^2) = e^{-3} e^{2x} \cdot 2 = 2e^{2x-3}$$
   This confirms that the two mechanisms are completely consistent!
2. **Global Positivity Check**:
   Since $e^{2x-3} > 0$, $5^x > 0$, $2 > 0$, and $\ln 5 > \ln e = 1 > 0$ for all $x \in \mathbb{R}$, every term of $f'(x) = 2e^{2x-3} + 5^x \ln 5$ is strictly positive. This matches the fact that $f(x)$ is the sum of two strictly increasing exponential functions.
