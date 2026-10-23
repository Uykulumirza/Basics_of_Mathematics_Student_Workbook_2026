# Solution to Problem 10: Definite Integral and Checking the Result

## 1. Problem Statement

Before carrying out the exact calculation, estimate the possible range of values of the integral
$$\int_0^2(x^2+1)\,dx,$$
using
$$1\le x^2+1\le5$$
on $[0,2]$. Only then compute the integral exactly, compare the result with the earlier estimate, and explain what type of computational error such a check can detect.

> **Why this problem:** it teaches how to predict the possible range of a result and check the calculation.

---

## 2. Theoretical Background and Concepts

### Comparison and Boundedness Property of the Definite Integral
Let $f: [a, b] \to \mathbb{R}$ be an integrable function on $[a, b]$ with $a < b$. If there exist real constants $m$ and $M$ such that
$$m \le f(x) \le M \quad \text{for all } x \in [a, b],$$
then by the monotonicity of the definite integral:
$$\int_a^b m\,dx \le \int_a^b f(x)\,dx \le \int_a^b M\,dx,$$
which simplifies to the **Lower and Upper Bound Inequality**:
$$m(b - a) \le \int_a^b f(x)\,dx \le M(b - a).$$
Geometrically, when $0 \le m \le f(x) \le M$, the area under $y = f(x)$ over $[a, b]$ contains a rectangle of width $(b - a)$ and height $m$, and is contained inside a rectangle of width $(b - a)$ and height $M$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Estimating the Range of Values Before Calculating
The integrand $f(x) = x^2 + 1$ is strictly increasing on the interval $[a, b] = [0, 2]$ because $x \ge 0$. Therefore:
- Its minimum value on $[0, 2]$ occurs at the left endpoint $x = 0$:
  $$m = f(0) = 0^2 + 1 = 1.$$
- Its maximum value on $[0, 2]$ occurs at the right endpoint $x = 2$:
  $$M = f(2) = 2^2 + 1 = 5.$$
Thus, for all $x \in [0, 2]$:
$$1 \le x^2 + 1 \le 5.$$
Multiplying these bounds by the length of the interval, $b - a = 2 - 0 = 2$ (equivalently, integrating the inequality over $[0, 2]$):
$$1 \cdot (2 - 0) \le \int_0^2 (x^2 + 1)\,dx \le 5 \cdot (2 - 0),$$
$$2 \le \int_0^2 (x^2 + 1)\,dx \le 10.$$
Hence, before doing any antiderivative calculation, we know with certainty that the exact value of the integral must lie inside the closed interval $[2, 10]$ (and strictly inside $(2, 10)$ because $x^2+1$ is continuous and non-constant).

### Step 2: Computing the Definite Integral Exactly
To find the exact value of $\int_0^2 (x^2 + 1)\,dx$, we first determine an antiderivative of $f(x) = x^2 + 1$ using the power rule term by term:
$$F(x) = \int (x^2 + 1)\,dx = \frac{x^3}{3} + x.$$
*(Verification of antiderivative by differentiation: $F'(x) = \frac{d}{dx}\left(\frac{x^3}{3} + x\right) = \frac{3x^2}{3} + 1 = x^2 + 1 = f(x)$.)*

Applying the Fundamental Theorem of Calculus on $[0, 2]$:
$$\begin{aligned}
\int_0^2 (x^2 + 1)\,dx &= \left[\frac{x^3}{3} + x\right]_0^2 \\
&= \left(\frac{2^3}{3} + 2\right) - \left(\frac{0^3}{3} + 0\right) \\
&= \frac{8}{3} + \frac{6}{3} - 0 \\
&= \frac{14}{3} = 4\frac{2}{3} \approx 4.67.
\end{aligned}$$

### Step 3: Comparing the Exact Result with the Earlier Estimate
We check whether $I = \frac{14}{3}$ falls within the predicted interval $[2, 10]$:
$$2 = \frac{6}{3} \le \frac{14}{3} \le \frac{30}{3} = 10.$$
Indeed, $4.67 \in [2, 10]$ (and is slightly below the midpoint $\frac{2+10}{2} = 6$ because $y = x^2 + 1$ is convex/concave upward on $[0, 2]$). The exact result is fully consistent with our a priori bound.

### Step 4: Explaining What Types of Computational Errors Such a Check Detects (and Its Limitations)
Performing a quick $m(b-a) \le \int_a^b f(x)\,dx \le M(b-a)$ bound check provides a **necessary consistency condition**, though it is **not sufficient** by itself to prove that a calculation is error-free:

1. **Errors that ARE detected (values falling outside $[2, 10]$):**
   - **Sign errors or reversed limits of integration:** Computing $F(0) - F(2) = -\frac{14}{3} \approx -4.67 < 2$ is immediately flagged as impossible because the integrand is strictly positive ($f(x) \ge 1$) and the lower bound is $+2$.
   - **Major exponent, coefficient, or arithmetic errors:** For example, mistakenly writing $\int x^2\,dx = 3x^3$ instead of $\frac{x^3}{3}$ yields $[3x^3 + x]_0^2 = 26 > 10$, violating the upper bound; similarly, evaluating only at the lower endpoint ($0 < 2$) or making a large arithmetic slip that pushes the result outside $[2, 10]$ is immediately caught.

2. **Errors that are NOT detected by the bound $[2, 10]$ alone (requiring independent checks):**
   - Because the interval $[2, 10]$ is relatively wide, certain flawed calculations still land inside $[2, 10]$. For instance:
     - **Omitting the constant term $+1$** (or treating $\int 1\,dx$ as $0$) gives $\int_0^2 x^2\,dx = \left[\frac{x^3}{3}\right]_0^2 = \frac{8}{3} \approx 2.67$, which still satisfies $2 \le \frac{8}{3} \le 10$.
     - **Differentiating instead of integrating** gives $[2x]_0^2 = 4$, which also lies inside $[2, 10]$.
   - Detecting these subtler errors requires **verifying the antiderivative by differentiation** ($F'(x) = \frac{d}{dx}\left(\frac{x^3}{3} + x\right) = x^2 + 1 = f(x)$) or using a tighter numerical check such as the midpoint/trapezoidal rule.

---

## 4. Verification and Consistency Checks

1. **Trapezoidal Approximation Check (Convexity Refinement):** Because $f''(x) = 2 > 0$, the graph of $f(x) = x^2 + 1$ is strictly convex on $[0, 2]$, so it lies below the secant line connecting $(0, 1)$ and $(2, 5)$. The area of that trapezoid is $\frac{f(0)+f(2)}{2}\cdot(2-0) = \frac{1+5}{2}\cdot 2 = 6$. Our exact answer $\frac{14}{3} \approx 4.67$ satisfies $2 < 4.67 < 6 < 10$.
