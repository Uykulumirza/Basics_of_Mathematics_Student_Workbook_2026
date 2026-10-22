# Solution to Problem 15: Recovering a Function from Its Derivative and a Condition

## 1. Problem Statement

The function $F$ satisfies
$$F'(x)=2xe^{x^2}$$
and
$$F(0)=3.$$

1. Recognize the method needed to find the function $F$.
2. Determine the entire family of functions with the given derivative.
3. Use the condition $F(0)=3$ to determine the correct constant.
4. Verify the final result by differentiation and substitution of $x=0$.

> **Why this problem:** it combines recognition of substitution, the meaning of the constant of integration, and an initial condition in one problem, using only mechanisms introduced earlier.

---

## 2. Theoretical Background and Concepts

### Initial Value Problems (IVPs) of First Order
Finding a differentiable function $F: \mathbb{R} \to \mathbb{R}$ that simultaneously satisfies a differential equation of the form
$$F'(x) = f(x)$$
and a point condition (called an **initial condition**)
$$F(x_0) = y_0$$
is the simplest type of **Initial Value Problem (IVP)**.

Solving it proceeds in two stages:
1. **General Solution (Indefinite Integration):** Integrate $f(x)$ to obtain the one-parameter family of all antiderivatives:
   $$F(x) = \int f(x)\,dx = F_0(x) + C, \quad C \in \mathbb{R}.$$
   Geometrically, this represents a family of parallel curves shifted vertically by $C$.
2. **Particular Solution (Applying the Initial Condition):** Substitute $x = x_0$ and $F(x_0) = y_0$ into the general solution to solve uniquely for $C$:
   $$F_0(x_0) + C = y_0 \implies C = y_0 - F_0(x_0).$$
   Geometrically, this selects the single curve in the family that passes through the prescribed point $(x_0, y_0)$.

---

## 3. Detailed Step-by-Step Solution

### Part 1: Recognizing the Method Needed to Find $F$
To recover $F(x)$ from its derivative $F'(x) = 2xe^{x^2}$, we must compute the indefinite integral:
$$F(x) = \int 2xe^{x^2}\,dx.$$
**How we recognize the integration method:**
- Inspecting the integrand $2xe^{x^2}$, we observe a composite exponential function $e^{x^2}$ whose inner exponent is $u = g(x) = x^2$.
- Differentiating the inner function $u = x^2$ gives $u'(x) = 2x$, which appears **verbatim** as the factor multiplying $e^{x^2}$!
- Thus, the integrand has the exact Chain-Rule derivative form $g'(x)e^{g(x)} = 2xe^{x^2}$, so the appropriate method is **Integration by Substitution** ($u = x^2$, reversing the chain rule).

---

### Part 2: Determining the Entire Family of Functions with the Given Derivative
We apply the substitution:
$$u = x^2 \implies du = \frac{d}{dx}(x^2)\,dx = 2x\,dx.$$
Substituting $u = x^2$ and $du = 2x\,dx$ into the indefinite integral:
$$\begin{aligned}
F(x) &= \int 2xe^{x^2}\,dx \\
&= \int e^{x^2} \cdot (2x\,dx) \\
&= \int e^u\,du.
\end{aligned}$$
Since the antiderivative of $e^u$ is $e^u + C$, we obtain:
$$F(x) = e^u + C.$$
Back-substituting $u = x^2$ gives the entire family of functions whose derivative is $2xe^{x^2}$:
$$F(x) = e^{x^2} + C, \quad C \in \mathbb{R}.$$

---

### Part 3: Using the Condition $F(0) = 3$ to Determine the Constant $C$
We now require that the function $F(x) = e^{x^2} + C$ satisfy the given initial condition $F(0) = 3$. Substituting $x = 0$ into our general formula for $F(x)$:
$$F(0) = e^{0^2} + C = 3.$$
Since $0^2 = 0$ and $e^0 = 1$, this simplifies to:
$$1 + C = 3 \implies C = 3 - 1 = 2.$$
*(Caution: A common student pitfall is to assume automatically that $C$ equals the right-hand side $3$ of $F(0) = 3$, forgetting that $e^0 = 1 \neq 0$! Because the particular antiderivative $F_0(x) = e^{x^2}$ already equals $1$ at $x = 0$, the constant $C$ must be $2$ so that $1 + 2 = 3$.)*

Substituting $C = 2$ back into the family gives the unique function $F$:
$$F(x) = e^{x^2} + 2.$$

---

### Part 4: Verification of the Final Result
To verify that $F(x) = e^{x^2} + 2$ is the exact and unique solution to the problem, we check both requirements explicitly:

1. **Verification of the Derivative $F'(x) = 2xe^{x^2}$:**
   Differentiating $F(x) = e^{x^2} + 2$ with respect to $x$ using the Chain Rule and the fact that the derivative of the constant $2$ is $0$:
   $$\begin{aligned}
   F'(x) &= \frac{d}{dx}\left(e^{x^2} + 2\right) \\
   &= \frac{d}{dx}\left(e^{x^2}\right) + \frac{d}{dx}(2) \\
   &= e^{x^2} \cdot \frac{d}{dx}(x^2) + 0 \\
   &= e^{x^2} \cdot (2x) \\
   &= 2xe^{x^2}. \quad \checkmark
   \end{aligned}$$

2. **Verification of the Initial Condition $F(0) = 3$:**
   Evaluating $F(x) = e^{x^2} + 2$ at $x = 0$:
   $$F(0) = e^{0^2} + 2 = e^0 + 2 = 1 + 2 = 3. \quad \checkmark$$

Both conditions are satisfied identically.

---

## 4. Verification and Consistency Checks

1. **Alternative Formulation via the Definite Integral (FTC):** By the Fundamental Theorem of Calculus, the unique solution to $F'(x) = f(x)$ with $F(0) = 3$ can also be written directly as:
   $$F(x) = F(0) + \int_0^x 2te^{t^2}\,dt = 3 + \left[e^{t^2}\right]_0^x = 3 + \big(e^{x^2} - e^0\big) = 3 + e^{x^2} - 1 = e^{x^2} + 2.$$
   This independent method confirms $C = 2$ and explains why $e^0 = 1$ is subtracted from $3$.
2. **Comparison with Problem 5:** In Problem 5, we found $\int xe^{x^2}\,dx = \frac{1}{2}e^{x^2} + C$. Multiplying the integrand by $2$ gives $\int 2xe^{x^2}\,dx = 2\left(\frac{1}{2}e^{x^2}\right) + C = e^{x^2} + C$, which is completely consistent.
