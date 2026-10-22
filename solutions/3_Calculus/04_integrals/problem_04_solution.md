# Solution to Problem 4: Substitution as Reversing the Chain Rule

## 1. Problem Statement

Compute
$$\int 2x(x^2+1)^4\,dx.$$
Before calculating, identify a candidate for the new variable $u$ and show that its derivative appears in the integral. Finally, verify the result by differentiation.

> **Why this problem:** it teaches how to recognize substitution as reversing the chain rule.

---

## 2. Theoretical Background and Concepts

### The Chain Rule and Its Inverse (Integration by Substitution)
Recall the **Chain Rule** for differentiating a composite function $F(g(x))$:
$$\frac{d}{dx}\big[F(g(x))\big] = F'(g(x)) \cdot g'(x).$$
If $F$ is an antiderivative of $f$ (so that $F'(u) = f(u)$), then reading this identity in reverse gives the **Integration by Substitution Rule**:
$$\int f(g(x))\,g'(x)\,dx = \int f(u)\,du = F(u) + C = F(g(x)) + C,$$
where we set $u = g(x)$ and the differential is $du = g'(x)\,dx$.

### How to Recognize a Substitution Integral
Integration by substitution is indicated whenever the integrand is a product of:
1. A composite function $f(g(x))$ containing an "inner" expression $u = g(x)$, and
2. A factor outside the composite function that equals (or is a non-zero constant multiple of) the derivative $g'(x)$ of that inner expression.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identifying the Candidate for $u$ and Its Derivative Before Calculating
We inspect the structure of the integrand:
$$2x(x^2+1)^4.$$
- **Candidate for the inner variable $u$:** Inside the fourth power $(\cdots)^4$, we see the polynomial $g(x) = x^2 + 1$. Thus, the natural candidate for the new variable is:
  $$u = x^2 + 1.$$
- **Checking for its derivative in the integrand:** Differentiating $u = x^2 + 1$ with respect to $x$ gives:
  $$\frac{du}{dx} = \frac{d}{dx}(x^2 + 1) = 2x \implies du = 2x\,dx.$$
  Looking back at the original integral $\int \underbrace{(x^2+1)^4}_{u^4}\,\underbrace{2x\,dx}_{du}$, we see that the factor $2x$ multiplying $(x^2+1)^4\,dx$ is **literally the exact derivative** $u'(x) = 2x$ of the inner function! This confirms that the integrand has the exact chain-rule derivative form $f(g(x))g'(x)$ with $f(u) = u^4$ and $g(x) = x^2+1$.

*(Note: While one could theoretically expand $(x^2+1)^4 = x^8 + 4x^6 + 6x^4 + 4x^2 + 1$ by the binomial theorem, multiply by $2x$, and integrate term by term, substitution avoids this tedious expansion and generalizes to high or fractional powers such as $(x^2+1)^{100}$ or $(x^2+1)^{1/2}$.)*

### Step 2: Carrying Out the Substitution and Integration
Substituting $u = x^2 + 1$ and $du = 2x\,dx$ transforms the integral in $x$ into an elementary power-rule integral in $u$:
$$\begin{aligned}
\int 2x(x^2+1)^4\,dx &= \int (x^2+1)^4 \cdot (2x\,dx) \\
&= \int u^4\,du.
\end{aligned}$$
Applying the power rule $\int u^n\,du = \frac{u^{n+1}}{n+1} + C$ for $n = 4$:
$$\int u^4\,du = \frac{u^{4+1}}{4+1} + C = \frac{u^5}{5} + C, \quad C \in \mathbb{R}.$$
Finally, we back-substitute $u = x^2 + 1$ to express the antiderivative in terms of the original variable $x$:
$$F(x) = \frac{1}{5}(x^2+1)^5 + C, \quad C \in \mathbb{R}.$$

### Step 3: Verification by Differentiation
We differentiate $F(x) = \frac{1}{5}(x^2+1)^5 + C$ with respect to $x$ using the **Chain Rule**:
$$\begin{aligned}
F'(x) &= \frac{d}{dx}\left[\frac{1}{5}(x^2+1)^5 + C\right] \\
&= \frac{1}{5} \cdot \underbrace{5(x^2+1)^{5-1}}_{\text{outer derivative}} \cdot \underbrace{\frac{d}{dx}(x^2+1)}_{\text{inner derivative}} + 0 \\
&= (x^2+1)^4 \cdot (2x) \\
&= 2x(x^2+1)^4.
\end{aligned}$$
The result is identical to the original integrand for all $x \in \mathbb{R}$.

---

## 4. Verification and Consistency Checks

1. **Degree and Leading Term Check:** In the integrand, the highest-degree term is $2x \cdot (x^2)^4 = 2x^9$, whose integral is $\frac{2}{10}x^{10} = \frac{1}{5}x^{10}$. In our solution $F(x) = \frac{1}{5}(x^2+1)^5 + C$, the leading term of the binomial expansion is $\frac{1}{5}(x^2)^5 = \frac{1}{5}x^{10}$, which matches completely.
2. **Slope Check at $x = 1$:** At $x = 1$, the integrand equals $2(1)(1^2+1)^4 = 2 \cdot 2^4 = 32$, and $F'(1) = 2(1)(1+1)^4 = 32$.
