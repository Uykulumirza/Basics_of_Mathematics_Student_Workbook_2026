# Solution to Problem 6: When Does a Logarithm Appear from an Integral?

## 1. Problem Statement

Compute
$$\int\frac{2x}{x^2+5}\,dx.$$
Identify the denominator as a candidate for substitution, compare the numerator with its derivative, and explain the source of the logarithm in the result.

> **Why this problem:** it teaches how to recognize the structure “derivative of the denominator over the denominator.”

---

## 2. Theoretical Background and Concepts

### The Exceptional Exponent $n = -1$ and the Natural Logarithm
The standard power rule for integration,
$$\int u^n\,du = \frac{u^{n+1}}{n+1} + C,$$
holds for all real exponents $n \neq -1$. At the exceptional value $n = -1$, the formula $\frac{u^0}{0}$ is undefined because division by zero is impossible, and the derivative of a constant $u^0 = 1$ is $0$, not $u^{-1}$.

Instead, the antiderivative of $\frac{1}{u} = u^{-1}$ comes from the differentiation formula for the natural logarithm:
$$\frac{d}{du}\big(\ln|u|\big) = \frac{1}{u} \quad (u \neq 0) \implies \int \frac{1}{u}\,du = \ln|u| + C.$$

### Logarithmic Derivative Structure
By combining $\frac{d}{du}(\ln|u|) = \frac{1}{u}$ with the Chain Rule for $u = g(x) \neq 0$, we obtain:
$$\frac{d}{dx}\big(\ln|g(x)|\big) = \frac{1}{g(x)} \cdot g'(x) = \frac{g'(x)}{g(x)}.$$
Reversing this differentiation rule yields the fundamental logarithmic integration pattern ("derivative of the denominator over the denominator"):
$$\int \frac{g'(x)}{g(x)}\,dx = \ln|g(x)| + C.$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identifying the Denominator as the Substitution Variable and Comparing with the Numerator
Consider the rational integrand
$$f(x) = \frac{2x}{x^2+5}.$$
1. **Candidate for substitution:** In a rational fraction where the degree of the numerator ($1$) is one less than the degree of the denominator ($2$), the entire denominator is the natural candidate for the substitution variable:
   $$u = g(x) = x^2 + 5.$$
2. **Comparing the numerator with the derivative of the denominator:** Differentiating the denominator $u = x^2 + 5$ with respect to $x$ gives:
   $$u'(x) = \frac{d}{dx}(x^2 + 5) = 2x \implies du = 2x\,dx.$$
   Comparing this with the integrand, we observe that the numerator $2x$ is **identically equal** to the derivative $u'(x)$ of the denominator. Thus, the integrand has the exact form $\frac{u'(x)}{u(x)}$.

### Step 2: Explaining the Source of the Logarithm in the Result
When we apply the substitution $u = x^2 + 5$ and $du = 2x\,dx$, the integral becomes:
$$\int \frac{2x}{x^2+5}\,dx = \int \frac{1}{u}\,du = \int u^{-1}\,du.$$
Why does a logarithm appear here rather than a power function?
- The power rule $\int u^n\,du = \frac{u^{n+1}}{n+1} + C$ fails at $n = -1$ because $n + 1 = 0$ would produce division by zero.
- From differential calculus, the unique elementary function (up to an additive constant) whose derivative is $\frac{1}{u}$ is the natural logarithm: $(\ln|u|)' = \frac{1}{u}$, or more generally by the chain rule, $\big(\ln|u(x)|\big)' = \frac{u'(x)}{u(x)}$.
- Therefore, reversing differentiation on $\int \frac{du}{u}$ necessarily introduces $\ln|u|$.

### Step 3: Computing the Integral and Simplifying the Absolute Value
Carrying out the substitution $u = x^2 + 5$, $du = 2x\,dx$:
$$\begin{aligned}
\int \frac{2x}{x^2+5}\,dx &= \int \frac{du}{u} \\
&= \ln|u| + C \\
&= \ln|x^2 + 5| + C, \quad C \in \mathbb{R}.
\end{aligned}$$
**Why the absolute value bars can be dropped:**
For every real number $x \in \mathbb{R}$, we have $x^2 \ge 0$, which implies:
$$x^2 + 5 \ge 5 > 0 \quad \text{for all } x \in \mathbb{R}.$$
Because $x^2 + 5$ is strictly positive everywhere on $\mathbb{R}$, $|x^2 + 5| = x^2 + 5$, so we can replace the absolute value bars with standard parentheses:
$$F(x) = \ln(x^2 + 5) + C, \quad C \in \mathbb{R}.$$

### Step 4: Verification by Differentiation
We differentiate $F(x) = \ln(x^2 + 5) + C$ with respect to $x$ using the Chain Rule for the natural logarithm, $\frac{d}{dx}[\ln(g(x))] = \frac{g'(x)}{g(x)}$:
$$\begin{aligned}
F'(x) &= \frac{d}{dx}\big[\ln(x^2 + 5) + C\big] \\
&= \frac{1}{x^2 + 5} \cdot \frac{d}{dx}(x^2 + 5) + 0 \\
&= \frac{1}{x^2 + 5} \cdot (2x) \\
&= \frac{2x}{x^2 + 5}.
\end{aligned}$$
This recovers the original integrand for all $x \in \mathbb{R}$.

---

## 4. Verification and Consistency Checks

1. **Domain Check:** Since $x^2 + 5 \ge 5 > 0$, neither the integrand $\frac{2x}{x^2+5}$ nor the antiderivative $\ln(x^2+5) + C$ has any singularities on $\mathbb{R}$; both are smooth ($C^\infty$) on $(-\infty, \infty)$.
2. **Sign and Monotonicity Check:** For $x > 0$, the integrand $\frac{2x}{x^2+5} > 0$, and $F(x) = \ln(x^2+5) + C$ is strictly increasing; for $x < 0$, the integrand $\frac{2x}{x^2+5} < 0$, and $F(x)$ is strictly decreasing, with a horizontal tangent ($F'(0) = 0$) at $x = 0$.
