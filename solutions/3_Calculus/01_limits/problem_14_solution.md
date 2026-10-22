# Exercise 14: A $0/0$ Limit with Trigonometry

## 1. Problem Statement

Compute
$$\lim_{x\to0}\frac{1-\cos x}{x^2}.$$
Justify the result without using l'Hôpital's rule, using a trigonometric identity and the fundamental limit.

> **Why this exercise:** requires combining two known tools in one argument.

---

## 2. Theoretical Background and Concepts

### Why $\frac{1-\cos x}{x^2}$ Has $x^2$ in the Denominator
As $x \to 0$, $\cos x \to \cos 0 = 1$, so the numerator $1 - \cos x \to 0$, while the denominator $x^2 \to 0$. Thus $\lim_{x\to 0} \frac{1-\cos x}{x^2}$ has the indeterminate form $\left[\frac{0}{0}\right]$.

To evaluate this limit **without L'Hôpital's rule**, we convert $1 - \cos x$ into an expression involving $\sin^2(\cdot)$ so that the two factors of $\sin(\cdot)$ in the numerator pair up with the two factors of $x$ in $x^2$, allowing us to apply the fundamental trigonometric limit:
$$\lim_{u\to 0} \frac{\sin u}{u} = 1.$$

Two classic trigonometric identities achieve this conversion:
1. **Half-Angle (Power-Reduction) Identity:**
   $$1 - \cos x = 2\sin^2\left(\frac{x}{2}\right).$$
2. **Pythagorean Identity via Trigonometric Conjugation:**
   Multiplying $1 - \cos x$ by its conjugate $1 + \cos x$ gives:
   $$(1 - \cos x)(1 + \cos x) = 1 - \cos^2 x = \sin^2 x.$$

We present both methods in full detail below.

---

## 3. Detailed Step-by-Step Solution

### Method 1: Using the Half-Angle Identity $1 - \cos x = 2\sin^2\left(\frac{x}{2}\right)$

#### Step 1: Apply the Half-Angle Identity to the Numerator
Recall the double-angle cosine identity $\cos(2\theta) = 1 - 2\sin^2\theta$. Setting $\theta = \frac{x}{2}$ gives $1 - \cos x = 2\sin^2\left(\frac{x}{2}\right)$. Substituting this into the quotient for $x \neq 0$:
$$\frac{1 - \cos x}{x^2} = \frac{2\sin^2\left(\frac{x}{2}\right)}{x^2}.$$

#### Step 2: Reshape the Quotient to Match $\left(\frac{\sin(x/2)}{x/2}\right)^2$
Inside the sine function, the argument is $u = \frac{x}{2}$. Since $\sin^2\left(\frac{x}{2}\right) = \left(\sin\frac{x}{2}\right)^2$, we want $\left(\frac{x}{2}\right)^2 = \frac{x^2}{4}$ in the denominator. Writing $x^2 = 4 \cdot \left(\frac{x}{2}\right)^2$ yields:
$$\begin{aligned}
\frac{2\sin^2\left(\frac{x}{2}\right)}{x^2} &= \frac{2\sin^2\left(\frac{x}{2}\right)}{4\left(\frac{x}{2}\right)^2} \\[6pt]
&= \frac{1}{2} \cdot \left(\frac{\sin\left(\frac{x}{2}\right)}{\frac{x}{2}}\right)^2.
\end{aligned}$$

#### Step 3: Apply the Fundamental Trigonometric Limit and Limit Laws
Let $u = \frac{x}{2}$. As $x \to 0$ (with $x \neq 0$), we have $u \to 0$ (with $u \neq 0$). By the fundamental trigonometric limit:
$$\lim_{x\to 0} \frac{\sin\left(\frac{x}{2}\right)}{\frac{x}{2}} = \lim_{u\to 0} \frac{\sin u}{u} = 1.$$
By the Product/Power Rule and Constant Multiple Rule for limits:
$$\lim_{x\to 0} \frac{1 - \cos x}{x^2} = \frac{1}{2} \cdot \left(\lim_{x\to 0} \frac{\sin\left(\frac{x}{2}\right)}{\frac{x}{2}}\right)^2 = \frac{1}{2} \cdot 1^2 = \frac{1}{2}.$$

---

### Method 2: Multiplying by the Conjugate $(1 + \cos x)$ and Using $1 - \cos^2 x = \sin^2 x$

#### Step 1: Multiply Numerator and Denominator by $1 + \cos x$
For all $x$ in the punctured neighborhood $(-\pi, 0) \cup (0, \pi)$, we have $\cos x > -1$, so $1 + \cos x > 0$. Multiplying numerator and denominator by $1 + \cos x$ and applying the Pythagorean identity $1 - \cos^2 x = \sin^2 x$ gives:
$$\begin{aligned}
\frac{1 - \cos x}{x^2} &= \frac{(1 - \cos x)(1 + \cos x)}{x^2(1 + \cos x)} \\[6pt]
&= \frac{1 - \cos^2 x}{x^2(1 + \cos x)} \\[6pt]
&= \frac{\sin^2 x}{x^2(1 + \cos x)}.
\end{aligned}$$

#### Step 2: Separate into Known Factors
Grouping $\frac{\sin^2 x}{x^2} = \left(\frac{\sin x}{x}\right)^2$ and $\frac{1}{1 + \cos x}$:
$$\frac{1 - \cos x}{x^2} = \left(\frac{\sin x}{x}\right)^2 \cdot \frac{1}{1 + \cos x}.$$

#### Step 3: Evaluate the Limit of Each Factor
1. By the fundamental trigonometric limit and the Product Rule:
   $$\lim_{x\to 0} \left(\frac{\sin x}{x}\right)^2 = \left(\lim_{x\to 0} \frac{\sin x}{x}\right)^2 = 1^2 = 1.$$
2. By the continuity of $\cos x$ at $x = 0$, $\lim_{x\to 0} \cos x = \cos 0 = 1$, so the denominator $1 + \cos x$ approaches $1 + 1 = 2 \neq 0$:
   $$\lim_{x\to 0} \frac{1}{1 + \cos x} = \frac{1}{1 + \cos 0} = \frac{1}{1 + 1} = \frac{1}{2}.$$
3. Applying the Product Rule for limits:
   $$\lim_{x\to 0} \frac{1 - \cos x}{x^2} = \left(\lim_{x\to 0}\frac{\sin x}{x}\right)^2 \cdot \left(\lim_{x\to 0}\frac{1}{1 + \cos x}\right) = 1^2 \cdot \frac{1}{2} = \frac{1}{2}.$$

Both methods yield the exact same result $\frac{1}{2}$.

---

## 4. Verification and Consistency Checks

### Numerical Check for Small $x$ (in Radians)
Since $f(x) = \frac{1-\cos x}{x^2}$ is an even function ($f(-x) = f(x)$ because $\cos(-x) = \cos x$ and $(-x)^2 = x^2$), we evaluate $f(x)$ as $x \to 0$:

| $x$ (radians) | $\cos x$ | Numerator $1 - \cos x$ | Denominator $x^2$ | $f(x) = \frac{1-\cos x}{x^2}$ | Target $\frac{1}{2}$ | Error $\left|\frac{1}{2} - f(x)\right|$ |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| $\pm 0.5$ | $0.87758256$ | $0.12241744$ | $0.25$ | $0.48966975$ | $0.50000000$ | $0.01033025$ |
| $\pm 0.1$ | $0.99500417$ | $0.00499583$ | $0.01$ | $0.49958347$ | $0.50000000$ | $0.00041653$ |
| $\pm 0.01$ | $0.9999500004$ | $0.0000499996$ | $0.0001$ | $0.49999583$ | $0.50000000$ | $0.00000417$ |
| $\pm 0.001$ | $0.9999995000$ | $0.0000005000$ | $0.000001$ | $0.49999996$ | $0.50000000$ | $0.00000004$ |

### Taylor Series Consistency Check
The Maclaurin expansion of $\cos x$ is $\cos x = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \dots = 1 - \frac{x^2}{2} + \frac{x^4}{24} - \dots$. Therefore:
$$\frac{1 - \cos x}{x^2} = \frac{\frac{x^2}{2} - \frac{x^4}{24} + O(x^6)}{x^2} = \frac{1}{2} - \frac{x^2}{24} + O(x^4) \xrightarrow{x\to 0} \frac{1}{2}.$$
Notice that the error $\frac{1}{2} - f(x) \approx \frac{x^2}{24}$ at $x = 0.1$ gives $\frac{0.01}{24} \approx 0.0004167$, in exact agreement with the table above!

### Final Conclusion
$$\boxed{\lim_{x\to0}\frac{1-\cos x}{x^2} = \frac{1}{2}}$$
