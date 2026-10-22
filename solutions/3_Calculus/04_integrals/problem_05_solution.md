# Solution to Problem 5: The Same Substitution in a Different Context

## 1. Problem Statement

Compute
$$\int xe^{x^2}\,dx.$$
First compare the structure with Problem 4 and explain what is common despite the different appearance of the function.

> **Why this problem:** it shows that the substitution mechanism is recognized by structure, not by the type of function.

---

## 2. Theoretical Background and Concepts

### Structural Pattern of Substitution ($\int g'(x)f(g(x))\,dx$)
The method of integration by substitution does not depend on whether the outer function $f(u)$ is a power function, an exponential, a trigonometric function, or a logarithm. Instead, it depends solely on the **composite-derivative structure**:
$$\int f(g(x))\,g'(x)\,dx = \int f(u)\,du \quad \text{where } u = g(x), \; du = g'(x)\,dx.$$
More generally, if the integrand contains $g'(x)$ up to a non-zero constant factor $k$—that is, if $du = k\cdot h(x)\,dx$ so that $h(x)\,dx = \frac{1}{k}\,du$—linearity allows us to factor out $\frac{1}{k}$:
$$\int f(g(x))\,h(x)\,dx = \frac{1}{k}\int f(g(x))\,\big(k\,h(x)\,dx\big) = \frac{1}{k}\int f(u)\,du.$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Structural Comparison with Problem 4
Let us compare the integrand of Problem 4 with the current integrand side by side:

| Feature | Problem 4: $\int 2x(x^2+1)^4\,dx$ | Problem 5: $\int xe^{x^2}\,dx$ |
| :--- | :--- | :--- |
| **Outer function $f(u)$** | Power function: $f(u) = u^4$ | Exponential function: $f(u) = e^u$ |
| **Inner function $u = g(x)$** | Quadratic polynomial: $u = x^2 + 1$ | Quadratic monomial: $u = x^2$ |
| **Inner derivative $g'(x)$** | $\frac{du}{dx} = 2x$ | $\frac{du}{dx} = 2x$ |
| **Outside factor in integrand** | $2x$ (exact derivative $g'(x)$) | $x = \frac{1}{2}(2x)$ ($\frac{1}{2}$ of $g'(x)$) |

**What is common despite the different appearance:**
- Even though Problem 4 involves an algebraic polynomial raised to the $4$th power and Problem 5 involves a transcendental exponential function, **both integrands are built on the exact same structural pattern** $\text{const} \times g'(x) \cdot f(g(x))$.
- In both problems, the inner function $g(x)$ is a quadratic expression in $x$ ($x^2+1$ or $x^2$) whose derivative $g'(x) = 2x$ is linear in $x$, and in both integrands there is an external factor of $x$ multiplying the composite function.
- The only minor difference is a constant factor of $2$: in Problem 4 the factor $2x$ is already present, whereas in Problem 5 we have $x\,dx = \frac{1}{2}(2x\,dx) = \frac{1}{2}\,du$. Because $\frac{1}{2}$ is a constant, it can be factored outside the integral sign.

### Step 2: Carrying Out the Substitution and Integration
We set the inner exponent as our substitution variable:
$$u = x^2.$$
Computing the differential:
$$du = \frac{d}{dx}(x^2)\,dx = 2x\,dx \implies x\,dx = \frac{1}{2}\,du.$$
Substituting $u = x^2$ and $x\,dx = \frac{1}{2}\,du$ into the integral gives:
$$\begin{aligned}
\int xe^{x^2}\,dx &= \int e^{x^2} \cdot (x\,dx) \\
&= \int e^u \cdot \left(\frac{1}{2}\,du\right) \\
&= \frac{1}{2}\int e^u\,du.
\end{aligned}$$
Since $\int e^u\,du = e^u + C$, we obtain:
$$\frac{1}{2}\int e^u\,du = \frac{1}{2}e^u + C.$$
Back-substituting $u = x^2$ yields the family of antiderivatives in terms of $x$:
$$F(x) = \frac{1}{2}e^{x^2} + C, \quad C \in \mathbb{R}.$$

### Step 3: Verification by Differentiation
We differentiate $F(x) = \frac{1}{2}e^{x^2} + C$ with respect to $x$ using the Chain Rule $\frac{d}{dx}\left(e^{g(x)}\right) = e^{g(x)} \cdot g'(x)$:
$$\begin{aligned}
F'(x) &= \frac{d}{dx}\left(\frac{1}{2}e^{x^2} + C\right) \\
&= \frac{1}{2} \cdot e^{x^2} \cdot \frac{d}{dx}(x^2) + 0 \\
&= \frac{1}{2} e^{x^2} \cdot (2x) \\
&= xe^{x^2}.
\end{aligned}$$
This matches the original integrand identically for all $x \in \mathbb{R}$.

---

## 4. Verification and Consistency Checks

1. **Role of the Outside Factor $x$:** Note that without the factor $x$ in front, the integral $\int e^{x^2}\,dx$ cannot be expressed in terms of elementary functions (it leads to the imaginary error function $\operatorname{erfi}(x)$). It is precisely the presence of $x = \frac{1}{2}(x^2)'$ that allows the chain rule to be reversed.
2. **Parity Check:** The integrand $f(x) = xe^{x^2}$ is an odd function ($f(-x) = -xe^{(-x)^2} = -f(x)$). Its antiderivative $F(x) = \frac{1}{2}e^{x^2} + C$ is an even function ($F(-x) = F(x)$), which is consistent with the general rule that the derivative of an even function is odd.
