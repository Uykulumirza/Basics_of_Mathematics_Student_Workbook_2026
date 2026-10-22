# Exercise 13: Fundamental Trigonometric Limit

## 1. Problem Statement

Using
$$\lim_{x\to0}\frac{\sin x}{x}=1,$$
compute
$$\lim_{x\to0}\frac{\sin5x}{x},\qquad \lim_{x\to0}\frac{\sin2x}{\sin3x}.$$
In each case, show how you reduce the expression to the fundamental limit.

> **Why this exercise:** teaches how to reduce new limits to one known pattern.

---

## 2. Theoretical Background and Concepts

### The Fundamental Trigonometric Limit and Its Scaled Pattern
The foundational limit of trigonometry (with $x$ measured in radians) is:
$$\lim_{u\to 0} \frac{\sin u}{u} = 1.$$
Geometrically, this states that for very small angles $u$ (in radians), $\sin u \approx u$.

When the argument of the sine function is a non-zero constant multiple of $x$, say $u = kx$ with $k \neq 0$, then as $x \to 0$ (with $x \neq 0$), we also have $u = kx \to 0$ (with $u \neq 0$). By the **Change of Variable (Substitution) Theorem for Limits**,
$$\lim_{x\to 0} \frac{\sin(kx)}{kx} = \lim_{u\to 0} \frac{\sin u}{u} = 1.$$

### Crucial Structural Observation
In the pattern $\frac{\sin(\text{argument})}{\text{argument}}$, the denominator must match the **exact argument** inside the sine function! If we encounter $\sin(kx)$ in a limit as $x \to 0$, we multiply and divide by $kx$ to create the unit ratio $\frac{\sin(kx)}{kx} \to 1$.

---

## 3. Detailed Step-by-Step Solution

### Part A: First Limit $\lim_{x\to 0}\frac{\sin 5x}{x}$

#### Step 1: Identify the Indeterminate Form and Target Pattern
As $x \to 0$, both $\sin 5x \to \sin 0 = 0$ and $x \to 0$, so $\frac{\sin 5x}{x}$ is an indeterminate form of type $\left[\frac{0}{0}\right]$.
Inside the numerator we have $\sin(5x)$, whose argument is $5x$. To apply the fundamental limit $\lim_{u\to 0}\frac{\sin u}{u} = 1$, we need $5x$ in the denominator as well.

#### Step 2: Multiply and Divide by $5$ to Match the Argument
For all $x \neq 0$, we multiply the numerator and denominator by $5$:
$$\frac{\sin 5x}{x} = \frac{5 \cdot \sin 5x}{5x} = 5 \cdot \frac{\sin 5x}{5x}.$$

#### Step 3: Substitute $u = 5x$ and Apply Limit Laws
Let $u = 5x$. As $x \to 0$ (with $x \neq 0$), we have $u = 5x \to 0$ (with $u \neq 0$). Therefore:
$$\lim_{x\to 0} \frac{\sin 5x}{5x} = \lim_{u\to 0} \frac{\sin u}{u} = 1.$$
By the Constant Multiple Rule for limits:
$$\lim_{x\to 0} \frac{\sin 5x}{x} = \lim_{x\to 0} \left(5 \cdot \frac{\sin 5x}{5x}\right) = 5 \cdot \left(\lim_{x\to 0} \frac{\sin 5x}{5x}\right) = 5 \cdot 1 = 5.$$

---

### Part B: Second Limit $\lim_{x\to 0}\frac{\sin 2x}{\sin 3x}$

#### Step 1: Identify the Indeterminate Form and Domain Near $x = 0$
For $0 < |x| < \frac{\pi}{3}$, we have $0 < |3x| < \pi$, so $\sin 3x \neq 0$ and $x \neq 0$. As $x \to 0$, both $\sin 2x \to 0$ and $\sin 3x \to 0$, giving the indeterminate form $\left[\frac{0}{0}\right]$.

Here we have **two** sine expressions: $\sin(2x)$ in the numerator (which needs $2x$ to form $\frac{\sin 2x}{2x}$) and $\sin(3x)$ in the denominator (which needs $3x$ to form $\frac{\sin 3x}{3x}$).

#### Step 2: Introduce $2x$ and $3x$ to Reduce Both Sine Terms to the Fundamental Pattern
For $0 < |x| < \frac{\pi}{3}$, we can divide both numerator and denominator by $x$, and then adjust the constants $2$ and $3$:
$$\begin{aligned}
\frac{\sin 2x}{\sin 3x} &= \frac{\frac{\sin 2x}{x}}{\frac{\sin 3x}{x}} \\[6pt]
&= \frac{2 \cdot \frac{\sin 2x}{2x}}{3 \cdot \frac{\sin 3x}{3x}} \\[6pt]
&= \frac{2}{3} \cdot \frac{\frac{\sin 2x}{2x}}{\frac{\sin 3x}{3x}}.
\end{aligned}$$
*(Equivalently, written as a product: $\frac{\sin 2x}{\sin 3x} = \frac{2x}{3x} \cdot \frac{\sin 2x / (2x)}{\sin 3x / (3x)} = \frac{2}{3} \cdot \frac{\sin 2x / (2x)}{\sin 3x / (3x)}$.)*

#### Step 3: Apply Substitutions and the Quotient Rule for Limits
- Let $u = 2x$. As $x \to 0$, $u \to 0$, so:
  $$\lim_{x\to 0} \frac{\sin 2x}{2x} = \lim_{u\to 0} \frac{\sin u}{u} = 1.$$
- Let $v = 3x$. As $x \to 0$, $v \to 0$, so:
  $$\lim_{x\to 0} \frac{\sin 3x}{3x} = \lim_{v\to 0} \frac{\sin v}{v} = 1 \neq 0.$$

Since both the numerator and denominator of the complex fraction converge to $1 \neq 0$, we apply the Constant Multiple and Quotient Rules for limits:
$$\lim_{x\to 0}\frac{\sin 2x}{\sin 3x} = \frac{2}{3} \cdot \frac{\lim_{x\to 0}\frac{\sin 2x}{2x}}{\lim_{x\to 0}\frac{\sin 3x}{3x}} = \frac{2}{3} \cdot \frac{1}{1} = \frac{2}{3}.$$

---

## 4. Verification and Consistency Checks

### Numerical Check for Small $x$ (in Radians)
Let $f(x) = \frac{\sin 5x}{x}$ and $g(x) = \frac{\sin 2x}{\sin 3x}$. Because $f(-x) = \frac{\sin(-5x)}{-x} = \frac{-\sin 5x}{-x} = f(x)$ and $g(-x) = \frac{\sin(-2x)}{\sin(-3x)} = \frac{-\sin 2x}{-\sin 3x} = g(x)$, both functions are **even**, so their values at $-x$ and $+x$ are identical:

| $x$ (radians) | $\sin 5x$ | $f(x) = \frac{\sin 5x}{x}$ | Target $5$ | $\sin 2x$ | $\sin 3x$ | $g(x) = \frac{\sin 2x}{\sin 3x}$ | Target $\frac{2}{3} \approx 0.666667$ |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| $\pm 0.1$ | $\pm 0.4794255$ | $4.7942554$ | $5.0000000$ | $\pm 0.1986693$ | $\pm 0.2955202$ | $0.6722699$ | $0.6666667$ |
| $\pm 0.01$ | $\pm 0.0499792$ | $4.9979169$ | $5.0000000$ | $\pm 0.0199987$ | $\pm 0.0299955$ | $0.6667222$ | $0.6666667$ |
| $\pm 0.001$ | $\pm 0.00499998$ | $4.9999792$ | $5.0000000$ | $\pm 0.001999999$ | $\pm 0.002999996$ | $0.6666672$ | $0.6666667$ |

### Independent Check via Small-Angle / Taylor Approximation
For small $u$ in radians, $\sin u = u - \frac{u^3}{6} + O(u^5)$:
- $\frac{\sin 5x}{x} = \frac{5x - \frac{125}{6}x^3 + O(x^5)}{x} = 5 - \frac{125}{6}x^2 + O(x^4) \xrightarrow{x\to 0} 5$.
- $\frac{\sin 2x}{\sin 3x} = \frac{2x - \frac{8}{6}x^3 + O(x^5)}{3x - \frac{27}{6}x^3 + O(x^5)} = \frac{2 - \frac{4}{3}x^2 + O(x^4)}{3 - \frac{9}{2}x^2 + O(x^4)} \xrightarrow{x\to 0} \frac{2}{3}$.

### Final Conclusion
$$\boxed{\lim_{x\to0}\frac{\sin 5x}{x} = 5, \qquad \lim_{x\to0}\frac{\sin 2x}{\sin 3x} = \frac{2}{3}}$$
