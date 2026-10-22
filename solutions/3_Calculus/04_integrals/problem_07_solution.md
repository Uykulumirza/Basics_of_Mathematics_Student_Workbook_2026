# Solution to Problem 7: Integration by Parts as Reversing the Product Rule

## 1. Problem Statement

Compute
$$\int xe^x\,dx.$$
First write the product differentiation rule and, on that basis, explain the meaning of the integration-by-parts formula. Verify the result by differentiation.

> **Why this problem:** it connects a new technique with the familiar product rule.

---

## 2. Theoretical Background and Concepts

### Derivation of Integration by Parts from the Product Rule
Let $u = u(x)$ and $v = v(x)$ be continuously differentiable functions on an interval $I$. By the **Product Rule** of differentiation:
$$\frac{d}{dx}\big[u(x)v(x)\big] = u'(x)v(x) + u(x)v'(x), \quad \text{or in prime notation: } (uv)' = u'v + uv'.$$
Integrating both sides with respect to $x$ gives:
$$\int \big[u(x)v(x)\big]'\,dx = \int u'(x)v(x)\,dx + \int u(x)v'(x)\,dx.$$
Since $\int [u(x)v(x)]'\,dx = u(x)v(x)$ (absorbing the constant of integration into the remaining indefinite integrals), we can rearrange this equation to solve for $\int u(x)v'(x)\,dx$:
$$\int u(x)v'(x)\,dx = u(x)v(x) - \int v(x)u'(x)\,dx.$$
Using differential notation $du = u'(x)\,dx$ and $dv = v'(x)\,dx$, this takes the classic compact form:
$$\int u\,dv = uv - \int v\,du.$$

### Meaning of the Integration-by-Parts Formula
Integration by parts does not immediately evaluate an integral in one step; rather, it **trades one integral $\int u\,dv$ for another integral $\int v\,du$**. The technique succeeds when the new integral $\int v\,du$ is simpler to evaluate than the original integral $\int u\,dv$—typically because differentiating $u$ simplifies $u$ (for instance, reducing a polynomial's degree or turning $\ln x$ into $\frac{1}{x}$) while integrating $dv$ does not make $v$ more complicated.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Recognizing the Method
In the integral $\int xe^x\,dx$, the integrand is a product of two unrelated types of functions: an algebraic polynomial $x$ and an exponential function $e^x$.
- Direct integration does not apply.
- Substitution does not simplify the integral because the exponent is simply $x$ (whose derivative is $1$, not $x$).
- Therefore, we recognize **Integration by Parts** ($\int u\,dv = uv - \int v\,du$), where differentiating the polynomial factor $u = x$ reduces it to the constant $1$, leaving only $\int e^x\,dx$.

### Step 2: Choosing $u$ and $dv$ and Applying the Formula
We split the integrand $xe^x\,dx$ into $u$ and $dv$:
$$\begin{aligned}
u &= x &\implies \quad du &= 1\,dx = dx, \\
dv &= e^x\,dx &\implies \quad v &= \int e^x\,dx = e^x.
\end{aligned}$$
*(Note: When finding $v$ from $dv$, we may choose the simplest antiderivative with constant $0$; the general constant $C$ is added at the end of the integration.)*

Substituting $u, dv, du, v$ into the integration-by-parts formula $\int u\,dv = uv - \int v\,du$:
$$\begin{aligned}
\int xe^x\,dx &= x e^x - \int e^x\,dx \\
&= x e^x - e^x + C \\
&= (x - 1)e^x + C, \quad C \in \mathbb{R}.
\end{aligned}$$

### Step 3: Verification by Differentiation (Using the Product Rule)
Let $F(x) = (x - 1)e^x + C = xe^x - e^x + C$. We differentiate $F(x)$ with respect to $x$ using the **Product Rule** on $(x-1)e^x$:
$$\begin{aligned}
F'(x) &= \frac{d}{dx}\big[(x - 1)e^x + C\big] \\
&= \frac{d}{dx}(x - 1) \cdot e^x + (x - 1) \cdot \frac{d}{dx}(e^x) + 0 \\
&= 1 \cdot e^x + (x - 1)e^x \\
&= e^x + xe^x - e^x \\
&= xe^x.
\end{aligned}$$
Notice how the $+e^x$ term produced by differentiating the factor $(x-1)$ cancels the $-e^x$ term, leaving exactly $xe^x$. This directly illustrates why integration by parts is the inverse of the product rule.

---

## 4. Verification and Consistency Checks

1. **Cancellation Mechanism Check:** If a student mistakenly wrote $\int xe^x\,dx = xe^x + C$, differentiating by the product rule would give $(xe^x)' = 1\cdot e^x + xe^x = (x+1)e^x \neq xe^x$. The subtracted integral $-\int v\,du = -\int e^x\,dx = -e^x$ exists specifically to cancel the unwanted $+e^x$ term from the product rule!
2. **Sign and Critical Point Check:** The integrand $f(x) = xe^x$ is negative for $x < 0$, zero at $x = 0$, and positive for $x > 0$. Consequently, any antiderivative $F(x) = (x-1)e^x + C$ must have a global minimum at $x = 0$, which matches $F(0) = -1 + C < F(x)$ for all $x \neq 0$.
