# Solution to Problem 8: Choosing the Factors in Integration by Parts

## 1. Problem Statement

Compute
$$\int x\cos x\,dx.$$
Before calculating, justify why it is convenient to differentiate $x$ and integrate $\cos x$, rather than the other way around.

> **Why this problem:** it teaches that integration by parts requires a deliberate choice of factors.

---

## 2. Theoretical Background and Concepts

### Strategic Choice of $u$ and $dv$ in Integration by Parts
In the integration-by-parts formula
$$\int u\,dv = uv - \int v\,du,$$
we must partition the integrand $f(x)\,dx$ into two factors: a function $u$ to be **differentiated** ($du = u'(x)\,dx$) and a differential $dv$ to be **integrated** ($v = \int dv$).

Two guiding principles govern this choice:
1. **$dv$ must be readily integrable** in closed form.
2. **$\int v\,du$ must be simpler than $\int u\,dv$.** Specifically, differentiating $u$ should simplify the factor (e.g., reducing the degree of a polynomial $x^n \to nx^{n-1}$), while integrating $dv$ should not increase complexity (e.g., $\cos x$, $\sin x$, and $e^x$ remain within the same class of elementary functions upon integration).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Justifying the Choice of Factors Before Calculating
In $\int x\cos x\,dx$, we have two possible ways to assign $u$ and $dv$ to the factors $x$ and $\cos x$:

1. **Correct Choice — Differentiate $u = x$ and integrate $dv = \cos x\,dx$:**
   - Differentiating $u = x$ yields $du = 1\,dx$, which **reduces the polynomial degree from $1$ to $0$**, eliminating the variable $x$ completely!
   - Integrating $dv = \cos x\,dx$ yields $v = \sin x$, which is just as simple as $\cos x$.
   - The resulting new integral is $\int v\,du = \int \sin x\,dx$, an immediate basic table integral.

2. **What Happens with the Opposite Choice — Differentiate $u = \cos x$ and integrate $dv = x\,dx$:**
   - Differentiating $u = \cos x$ gives $du = -\sin x\,dx$ (still a trigonometric function of the same complexity).
   - Integrating $dv = x\,dx$ gives $v = \frac{1}{2}x^2$, which **raises the polynomial degree from $1$ to $2$**.
   - Applying the formula would yield:
     $$\int x\cos x\,dx = \frac{1}{2}x^2\cos x - \int \frac{1}{2}x^2(-\sin x)\,dx = \frac{1}{2}x^2\cos x + \frac{1}{2}\int x^2\sin x\,dx.$$
   - Instead of simplifying the problem, the new integral $\int x^2\sin x\,dx$ has a **higher power of $x$** and is strictly harder to evaluate than the original integral $\int x\cos x\,dx$.

Therefore, we must choose $u = x$ and $dv = \cos x\,dx$.

### Step 2: Carrying Out the Integration by Parts
We set:
$$\begin{aligned}
u &= x &\implies \quad du &= dx, \\
dv &= \cos x\,dx &\implies \quad v &= \int \cos x\,dx = \sin x.
\end{aligned}$$
Applying the integration-by-parts formula $\int u\,dv = uv - \int v\,du$:
$$\begin{aligned}
\int x\cos x\,dx &= x\sin x - \int \sin x\,dx.
\end{aligned}$$
Since $\frac{d}{dx}(\cos x) = -\sin x$, we have $\int \sin x\,dx = -\cos x + C$. Substituting this in:
$$\begin{aligned}
\int x\cos x\,dx &= x\sin x - (-\cos x) + C \\
&= x\sin x + \cos x + C, \quad C \in \mathbb{R}.
\end{aligned}$$

### Step 3: Verification by Differentiation
Let $F(x) = x\sin x + \cos x + C$. Differentiating $F(x)$ with respect to $x$ using the Product Rule on the first term $x\sin x$:
$$\begin{aligned}
F'(x) &= \frac{d}{dx}\big(x\sin x + \cos x + C\big) \\
&= \left[\frac{d}{dx}(x)\cdot\sin x + x\cdot\frac{d}{dx}(\sin x)\right] + \frac{d}{dx}(\cos x) + 0 \\
&= \big[1\cdot\sin x + x\cos x\big] - \sin x \\
&= \sin x + x\cos x - \sin x \\
&= x\cos x.
\end{aligned}$$
The derivative matches the original integrand identically for all $x \in \mathbb{R}$.

---

## 4. Verification and Consistency Checks

1. **Parity Check:** The integrand $f(x) = x\cos x$ is the product of an odd function ($x$) and an even function ($\cos x$), so $f(x)$ is an **odd function**: $f(-x) = (-x)\cos(-x) = -x\cos x = -f(x)$. Its antiderivative $F_0(x) = x\sin x + \cos x$ satisfies $F_0(-x) = (-x)\sin(-x) + \cos(-x) = x\sin x + \cos x = F_0(x)$, which is an **even function**, as required.
2. **Sign Check on $+\cos x$:** Notice that in $F'(x)$, differentiating $x\sin x$ produces $+\sin x + x\cos x$. To cancel $+\sin x$, the second term of $F(x)$ must differentiate to $-\sin x$, which confirms that the second term must be $+\cos x$ (not $-\cos x$).
