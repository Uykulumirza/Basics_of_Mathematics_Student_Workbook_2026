# Exercise 12: Exponential Function Limit

## 1. Problem Statement

Compute
$$\lim_{x\to0}(1+3x)^{1/x}.$$
Connect the result with the limit from Exercise 5 and show the appropriate transformation.

> **Why this exercise:** teaches how to recognize the classical pattern after a transformation.

---

## 2. Theoretical Background and Concepts

### Continuous Generalization of the Fundamental Limit for $e$
In Exercise 5, we studied the discrete sequence limit
$$\lim_{n\to\infty} \left(1 + \frac{1}{n}\right)^n = e.$$
This classical limit extends from positive integers $n \in \mathbb{N}^+$ to a continuous real variable $t \in \mathbb{R}$ approaching both $+\infty$ and $-\infty$:
$$\lim_{t\to +\infty} \left(1 + \frac{1}{t}\right)^t = e \quad \text{and} \quad \lim_{t\to -\infty} \left(1 + \frac{1}{t}\right)^t = e.$$
By setting $u = \frac{1}{t}$, so that $u \to 0$ (from both sides, $u \to 0^+$ as $t \to +\infty$ and $u \to 0^-$ as $t \to -\infty$), we obtain the equivalent **reciprocal form of the fundamental limit for $e$**:
$$\lim_{u\to 0} (1 + u)^{1/u} = e.$$

### Substitution and Continuity of Power/Exponential Functions
- **Change of Variable (Substitution) in Limits:** If $u = g(x)$ satisfies $\lim_{x\to x_0} g(x) = u_0$ and $g(x) \neq u_0$ for $x \neq x_0$ near $x_0$, then $\lim_{x\to x_0} F(g(x)) = \lim_{u\to u_0} F(u)$.
- **Continuity of the Cube Function $z \mapsto z^3$:** Because the function $h(z) = z^3$ is continuous on $\mathbb{R}$, for any function $\varphi(x)$ with $\lim_{x\to 0} \varphi(x) = L$, we can pass the limit inside the power:
  $$\lim_{x\to 0} \left[\varphi(x)\right]^3 = \left(\lim_{x\to 0} \varphi(x)\right)^3 = L^3.$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify the Indeterminate Form and Domain
Consider $f(x) = (1 + 3x)^{1/x}$. For the base $1 + 3x$ to be strictly positive ($1 + 3x > 0$), we require $x > -\frac{1}{3}$, and for the exponent $\frac{1}{x}$ to be defined, we require $x \neq 0$. Thus $f(x)$ is well-defined on the punctured neighborhood $\left(-\frac{1}{3}, 0\right) \cup (0, \infty)$ of $x = 0$.

As $x \to 0$:
- The base $1 + 3x \to 1 + 0 = 1$.
- The exponent $\frac{1}{x} \to \pm\infty$ ($+\infty$ as $x \to 0^+$ and $-\infty$ as $x \to 0^-$).

Thus, the limit has the indeterminate form $[1^\infty]$, the exact same indeterminate form as Exercise 5!

### Step 2: Algebraic Transformation Matching the Pattern $(1 + u)^{1/u}$
To match the classical pattern $(1 + \text{something})^{1/(\text{something})}$, notice that the small increment added to $1$ inside the base is $3x$. Therefore, we want the exponent immediately outside the parentheses to be its reciprocal $\frac{1}{3x}$ rather than $\frac{1}{x}$.

Using the laws of exponents for a positive base $1 + 3x > 0$, we write $\frac{1}{x} = \frac{3}{3x} = \frac{1}{3x} \cdot 3$:
$$(1 + 3x)^{1/x} = (1 + 3x)^{\frac{3}{3x}} = \left[(1 + 3x)^{\frac{1}{3x}}\right]^3.$$

### Step 3: Change of Variable (Connecting Directly to Exercise 5)
We can perform this substitution in either of two equivalent ways:

#### Approach A: Infinitesimal Substitution $u = 3x \to 0$
Let $u = 3x$. As $x \to 0$ (with $x \neq 0$), we have $u \to 0$ (with $u \neq 0$). Substituting $3x = u$ into the inner expression gives:
$$\lim_{x\to 0} (1 + 3x)^{\frac{1}{3x}} = \lim_{u\to 0} (1 + u)^{1/u} = e.$$

#### Approach B: Infinite Substitution $t = \frac{1}{3x} \to \pm\infty$ (Direct Form of Exercise 5)
Alternatively, let $t = \frac{1}{3x}$, so that $3x = \frac{1}{t}$.
- As $x \to 0^+$, $t = \frac{1}{3x} \to +\infty$.
- As $x \to 0^-$, $t = \frac{1}{3x} \to -\infty$.

In terms of $t$, the expression becomes:
$$(1 + 3x)^{1/x} = \left(1 + \frac{1}{t}\right)^{3t} = \left[\left(1 + \frac{1}{t}\right)^t\right]^3.$$
By the continuous extension of the fundamental limit from Exercise 5, $\lim_{t\to \pm\infty} \left(1 + \frac{1}{t}\right)^t = e$.

### Step 4: Apply Continuity of $z \mapsto z^3$ to Conclude
Since the inner expression $(1 + 3x)^{\frac{1}{3x}}$ converges to $e$ as $x \to 0$, and the cubing function $z \mapsto z^3$ is continuous at $z = e$, we pass the limit inside the exponent $3$:
$$\lim_{x\to 0} (1 + 3x)^{1/x} = \lim_{x\to 0} \left[(1 + 3x)^{\frac{1}{3x}}\right]^3 = \left(\lim_{x\to 0} (1 + 3x)^{\frac{1}{3x}}\right)^3 = e^3.$$

---

## 4. Verification and Consistency Checks

### Numerical Check Near $x = 0$ (Left-Hand and Right-Hand Values)
Let us compare $f(x) = (1 + 3x)^{1/x}$ for small negative and positive values of $x$ against $e^3 \approx (2.718281828)^3 \approx 20.08553692$:

| $x$ | Base $1 + 3x$ | Exponent $1/x$ | $f(x) = (1+3x)^{1/x}$ | Target $e^3$ | Error $|f(x) - e^3|$ |
| :--- | :--- | :--- | :--- | :--- | :--- |
| $-0.01$ | $0.9700$ | $-100$ | $21.029385$ | $20.085537$ | $0.943848$ |
| $-0.001$ | $0.9970$ | $-1{,}000$ | $20.176308$ | $20.085537$ | $0.090771$ |
| $-0.0001$ | $0.9997$ | $-10{,}000$ | $20.094579$ | $20.085537$ | $0.009042$ |
| $+0.0001$ | $1.0003$ | $+10{,}000$ | $20.076502$ | $20.085537$ | $0.009035$ |
| $+0.001$ | $1.0030$ | $+1{,}000$ | $19.995535$ | $20.085537$ | $0.090002$ |
| $+0.01$ | $1.0300$ | $+100$ | $19.218632$ | $20.085537$ | $0.866905$ |

As $x \to 0^-$ and $x \to 0^+$, the values of $(1+3x)^{1/x}$ sandwich $e^3 \approx 20.085537$ from above and below, respectively.

### Independent Check via Logarithms and the Derivative of $\ln(1+3x)$
Using the identity $(1+3x)^{1/x} = \exp\left(\frac{\ln(1+3x)}{x}\right)$ and the continuity of $\exp(z) = e^z$:
$$\lim_{x\to 0} \frac{\ln(1+3x)}{x} = \lim_{x\to 0} \frac{\ln(1+3x) - \ln(1)}{x - 0} = \left.\frac{d}{dx}\ln(1+3x)\right|_{x=0} = \left.\frac{3}{1+3x}\right|_{x=0} = 3.$$
Therefore, $\lim_{x\to 0} (1+3x)^{1/x} = \exp(3) = e^3$, independently confirming the result.

### Final Conclusion
$$\boxed{\lim_{x\to0}(1+3x)^{1/x} = e^3}$$
