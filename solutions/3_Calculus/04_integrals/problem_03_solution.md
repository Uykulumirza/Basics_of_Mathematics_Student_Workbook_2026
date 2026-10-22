# Solution to Problem 3: Recognizing Basic Antiderivatives

## 1. Problem Statement

Compute
$$\int\left(2e^x+3\cos x-4\sin x\right)\,dx.$$
Match each term with a known derivative and verify the entire result with one differentiation.

> **Why this problem:** it builds a catalogue of basic antiderivatives from known derivatives.

---

## 2. Theoretical Background and Concepts

### Fundamental Table of Derivatives and Corresponding Antiderivatives
Every basic integration formula is the direct inverse of an elementary differentiation formula on $\mathbb{R}$:

| Elementary Function $G(x)$ | Derivative $G'(x) = g(x)$ | Indefinite Integral $\int g(x)\,dx$ |
| :--- | :--- | :--- |
| $e^x$ | $\frac{d}{dx}(e^x) = e^x$ | $\int e^x\,dx = e^x + C$ |
| $\sin x$ | $\frac{d}{dx}(\sin x) = \cos x$ | $\int \cos x\,dx = \sin x + C$ |
| $\cos x$ | $\frac{d}{dx}(\cos x) = -\sin x$ | $\int \sin x\,dx = -\cos x + C$ |

### Linearity of the Indefinite Integral
For any integrable functions $f_1, f_2, f_3$ and real constants $c_1, c_2, c_3 \in \mathbb{R}$:
$$\int \big(c_1 f_1(x) + c_2 f_2(x) + c_3 f_3(x)\big)\,dx = c_1\int f_1(x)\,dx + c_2\int f_2(x)\,dx + c_3\int f_3(x)\,dx.$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Recognizing the Method and Matching Each Term with a Known Derivative
The integrand $f(x) = 2e^x + 3\cos x - 4\sin x$ is a linear combination of three fundamental transcendental functions defined for all $x \in \mathbb{R}$. No substitution or integration by parts is needed; we use **direct integration** by matching each term with its known derivative:

1. **Exponential term ($2e^x$):**
   We know that the natural exponential function is its own derivative:
   $$\frac{d}{dx}(e^x) = e^x \implies \frac{d}{dx}(2e^x) = 2e^x.$$
   Therefore, the antiderivative of $2e^x$ is $2e^x$.

2. **Cosine term ($3\cos x$):**
   We know that the derivative of $\sin x$ is $+\cos x$:
   $$\frac{d}{dx}(\sin x) = \cos x \implies \frac{d}{dx}(3\sin x) = 3\cos x.$$
   Therefore, the antiderivative of $3\cos x$ is $3\sin x$.

3. **Sine term ($-4\sin x$):**
   We know that the derivative of $\cos x$ is $-\sin x$:
   $$\frac{d}{dx}(\cos x) = -\sin x \implies \frac{d}{dx}(4\cos x) = 4(-\sin x) = -4\sin x.$$
   Notice how the negative sign in the integrand $-4\sin x$ is absorbed directly by the minus sign coming from $(\cos x)' = -\sin x$, resulting in $+4\cos x$ in the antiderivative.

### Step 2: Computing the Indefinite Integral
By linearity of the indefinite integral, we combine the three matched antiderivatives into a single expression with one arbitrary constant $C \in \mathbb{R}$:
$$\begin{aligned}
\int\left(2e^x + 3\cos x - 4\sin x\right)\,dx &= 2\int e^x\,dx + 3\int \cos x\,dx - 4\int \sin x\,dx \\
&= 2e^x + 3\sin x - 4(-\cos x) + C \\
&= 2e^x + 3\sin x + 4\cos x + C, \quad C \in \mathbb{R}.
\end{aligned}$$

### Step 3: Verification of the Entire Result with One Differentiation
Let $F(x) = 2e^x + 3\sin x + 4\cos x + C$. Differentiating the entire expression $F(x)$ at once with respect to $x$:
$$\begin{aligned}
F'(x) &= \frac{d}{dx}\left(2e^x + 3\sin x + 4\cos x + C\right) \\
&= 2\frac{d}{dx}(e^x) + 3\frac{d}{dx}(\sin x) + 4\frac{d}{dx}(\cos x) + \frac{d}{dx}(C) \\
&= 2e^x + 3\cos x + 4(-\sin x) + 0 \\
&= 2e^x + 3\cos x - 4\sin x.
\end{aligned}$$
The derivative $F'(x)$ matches the original integrand identically for all $x \in \mathbb{R}$.

---

## 4. Verification and Consistency Checks

1. **Trigonometric Sign Check:** Students frequently confuse the signs when integrating $\sin x$ and $\cos x$. Checking $(\sin x)' = +\cos x$ confirms that $+3\cos x$ integrates to $+3\sin x$, while $(\cos x)' = -\sin x$ confirms that $-4\sin x = 4(-\sin x)$ integrates to $+4\cos x$.
2. **Evaluation at $x = 0$:** For $F(x) = 2e^x + 3\sin x + 4\cos x + C$, the slope at $x = 0$ is $F'(0) = 2e^0 + 3\cos(0) - 4\sin(0) = 2(1) + 3(1) - 0 = 5$, which equals the integrand value $f(0) = 5$.
