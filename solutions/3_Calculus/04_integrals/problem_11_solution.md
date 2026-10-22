# Solution to Problem 11: Choose the Method First

## 1. Problem Statement

For each integral, first write which method you choose and how you recognize it, and then compute:
1. $\int\sin(3x)\,dx$,
2. $\int x\ln x\,dx$,
3. $\int\frac{x}{\sqrt{x^2+1}}\,dx$.

> **Why this problem:** it tests the choice of method based on the structure of the problem.

---

## 2. Theoretical Background and Concepts

### Decision Framework for Selecting an Integration Technique
When confronted with an indefinite integral $\int h(x)\,dx$, we analyze its algebraic and functional structure:
1. **Linear Substitution ($u = ax + b$):** If the integrand is a composite function $f(ax + b)$ whose inner argument is linear, its derivative is a non-zero constant $a$. Substituting $u = ax + b \implies dx = \frac{1}{a}\,du$ reduces the integral to $\frac{1}{a}\int f(u)\,du$.
2. **Non-Linear Substitution ($u = g(x)$):** If the integrand has the product/quotient structure $f(g(x)) \cdot k g'(x)$, where a factor outside the inner function $g(x)$ is proportional to the derivative $g'(x)$, substituting $u = g(x)$ reverses the Chain Rule.
3. **Integration by Parts ($\int u\,dv = uv - \int v\,du$):** If the integrand is a product of two functionally independent classes (such as a polynomial $x^n$ and a logarithm $\ln x$, exponential $e^x$, or trigonometric function) where neither factor is the derivative of an inner function of the other, we reverse the Product Rule. In particular, when $\ln x$ multiplies a power of $x$, we always set $u = \ln x$ (following the **LIATE** hierarchy: **L**ogarithmic, **I**nverse trig, **A**lgebraic, **T**rigonometric, **E**xponential) because differentiating $\ln x$ eliminates the transcendental logarithm into the rational algebraic function $\frac{1}{x}$.

---

## 3. Detailed Step-by-Step Solution

### Part 1: $\int \sin(3x)\,dx$

#### A. Method Selection and Recognition
- **Chosen Method:** **Linear Substitution** ($u = 3x$).
- **How We Recognize It:** The integrand $\sin(3x)$ is a composite function $f(g(x))$ with outer function $f(u) = \sin u$ and inner linear function $u = g(x) = 3x$. Because the derivative of the inner function is a constant ($g'(x) = 3$), $dx = \frac{1}{3}\,du$ introduces only a constant factor $\frac{1}{3}$, immediately reducing the integral to the basic table integral $\int \sin u\,du$.

#### B. Step-by-Step Computation
Let
$$u = 3x \implies du = 3\,dx \implies dx = \frac{1}{3}\,du.$$
Substituting into the integral:
$$\begin{aligned}
\int \sin(3x)\,dx &= \int \sin(u) \cdot \frac{1}{3}\,du \\
&= \frac{1}{3}\int \sin u\,du \\
&= \frac{1}{3}(-\cos u) + C \\
&= -\frac{1}{3}\cos(3x) + C, \quad C \in \mathbb{R}.
\end{aligned}$$

#### C. Verification by Differentiation
Differentiating $F_1(x) = -\frac{1}{3}\cos(3x) + C$ via the Chain Rule:
$$F_1'(x) = \frac{d}{dx}\left[-\frac{1}{3}\cos(3x) + C\right] = -\frac{1}{3}\big(-\sin(3x)\big)\cdot \frac{d}{dx}(3x) + 0 = \frac{1}{3}\sin(3x)\cdot 3 = \sin(3x).$$

---

### Part 2: $\int x\ln x\,dx$ (Domain: $x \in (0, \infty)$)

#### A. Method Selection and Recognition
- **Chosen Method:** **Integration by Parts** ($\int u\,dv = uv - \int v\,du$) with $u = \ln x$ and $dv = x\,dx$.
- **How We Recognize It:** The integrand is a product of an algebraic power function ($x$) and a logarithmic function ($\ln x$) on $(0, \infty)$. Neither factor is the derivative of an inner function of the other, ruling out direct substitution. Under integration by parts, choosing $u = \ln x$ and $dv = x\,dx$ is decisive because:
  1. Differentiating $u = \ln x$ gives $du = \frac{1}{x}\,dx$, which **eliminates the logarithm completely** and converts it into a simple algebraic power of $x$.
  2. Integrating $dv = x\,dx$ gives $v = \frac{1}{2}x^2$, so the product $v\,du = \frac{1}{2}x^2 \cdot \frac{1}{x}\,dx = \frac{1}{2}x\,dx$ becomes a trivial polynomial to integrate.
  *(By contrast, choosing $dv = \ln x\,dx$ would require already knowing the integral of $\ln x$.)*

#### B. Step-by-Step Computation
On the domain $x > 0$, we set:
$$\begin{aligned}
u &= \ln x &\implies \quad du &= \frac{1}{x}\,dx, \\
dv &= x\,dx &\implies \quad v &= \int x\,dx = \frac{x^2}{2}.
\end{aligned}$$
Applying $\int u\,dv = uv - \int v\,du$:
$$\begin{aligned}
\int x\ln x\,dx &= \frac{x^2}{2}\ln x - \int \frac{x^2}{2} \cdot \frac{1}{x}\,dx \\
&= \frac{x^2}{2}\ln x - \frac{1}{2}\int x\,dx \\
&= \frac{x^2}{2}\ln x - \frac{1}{2}\left(\frac{x^2}{2}\right) + C \\
&= \frac{x^2}{2}\ln x - \frac{x^2}{4} + C = \frac{x^2}{4}(2\ln x - 1) + C, \quad C \in \mathbb{R}, \; x > 0.
\end{aligned}$$

#### C. Verification by Differentiation
Differentiating $F_2(x) = \frac{x^2}{2}\ln x - \frac{x^2}{4} + C$ on $(0, \infty)$ using the Product Rule on the first term:
$$\begin{aligned}
F_2'(x) &= \frac{d}{dx}\left(\frac{x^2}{2}\ln x - \frac{x^2}{4} + C\right) \\
&= \left[\frac{d}{dx}\left(\frac{x^2}{2}\right)\cdot\ln x + \frac{x^2}{2}\cdot\frac{d}{dx}(\ln x)\right] - \frac{2x}{4} + 0 \\
&= \left[x\ln x + \frac{x^2}{2}\cdot\frac{1}{x}\right] - \frac{x}{2} \\
&= x\ln x + \frac{x}{2} - \frac{x}{2} \\
&= x\ln x.
\end{aligned}$$

---

### Part 3: $\int \frac{x}{\sqrt{x^2+1}}\,dx$

#### A. Method Selection and Recognition
- **Chosen Method:** **Integration by Substitution** ($u = x^2 + 1$).
- **How We Recognize It:** Inside the square root in the denominator sits the quadratic expression $g(x) = x^2 + 1$ (defined and strictly positive for all $x \in \mathbb{R}$). Its derivative is $g'(x) = 2x$, and the numerator of the integrand is $x = \frac{1}{2}(2x)$, which is a constant multiple of the inner derivative! Thus, the integrand has the exact composite chain-rule structure $\frac{1}{2} u^{-1/2} u'(x)$.

#### B. Step-by-Step Computation
Let
$$u = x^2 + 1 \implies du = 2x\,dx \implies x\,dx = \frac{1}{2}\,du.$$
Rewriting the radical as a fractional power and substituting $u = x^2 + 1$:
$$\begin{aligned}
\int \frac{x}{\sqrt{x^2+1}}\,dx &= \int (x^2+1)^{-1/2} \cdot (x\,dx) \\
&= \int u^{-1/2} \cdot \left(\frac{1}{2}\,du\right) \\
&= \frac{1}{2}\int u^{-1/2}\,du.
\end{aligned}$$
Applying the power rule $\int u^p\,du = \frac{u^{p+1}}{p+1} + C$ for $p = -\frac{1}{2}$ (so $p + 1 = +\frac{1}{2}$):
$$\begin{aligned}
\frac{1}{2}\int u^{-1/2}\,du &= \frac{1}{2} \cdot \frac{u^{1/2}}{\frac{1}{2}} + C \\
&= u^{1/2} + C \\
&= \sqrt{x^2+1} + C, \quad C \in \mathbb{R}.
\end{aligned}$$

#### C. Verification by Differentiation
Differentiating $F_3(x) = \sqrt{x^2+1} + C = (x^2+1)^{1/2} + C$ via the Chain Rule:
$$\begin{aligned}
F_3'(x) &= \frac{d}{dx}\left[(x^2+1)^{1/2} + C\right] \\
&= \frac{1}{2}(x^2+1)^{-1/2} \cdot \frac{d}{dx}(x^2+1) + 0 \\
&= \frac{1}{2\sqrt{x^2+1}} \cdot (2x) \\
&= \frac{x}{\sqrt{x^2+1}}.
\end{aligned}$$

---

## 4. Verification and Consistency Checks

1. **Summary Table of Results:**
   - $\int \sin(3x)\,dx = -\frac{1}{3}\cos(3x) + C$ ($x \in \mathbb{R}$)
   - $\int x\ln x\,dx = \frac{x^2}{2}\ln x - \frac{x^2}{4} + C$ ($x \in (0, \infty)$)
   - $\int \frac{x}{\sqrt{x^2+1}}\,dx = \sqrt{x^2+1} + C$ ($x \in \mathbb{R}$)
2. **Coefficient Check in Part 3:** Notice how the factor of $\frac{1}{2}$ from $x\,dx = \frac{1}{2}\,du$ and the factor of $2$ from dividing by the new exponent $\frac{1}{2}$ cancel each other out ($\frac{1}{2} \cdot 2 = 1$), leaving $\sqrt{x^2+1} + C$ with coefficient $1$.
