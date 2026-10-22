# Exercise 9: One-Sided Limits and an Asymptote

## 1. Problem Statement

Analyze the left-hand and right-hand limits of
$$f(x)=\frac1{x-2}$$
as $x\to2$. Does the two-sided limit exist? Interpret the result on a sketch of the graph and identify the vertical asymptote.

> **Why this exercise:** teaches how to distinguish one-sided limits and connect them with the geometry of an asymptote.

---

## 2. Theoretical Background and Concepts

### One-Sided Limits
1. **Left-Hand Limit ($x \to x_0^-$):** We write $\lim_{x\to x_0^-} f(x) = L$ (or $\pm\infty$) when $x$ approaches $x_0$ exclusively from the left, i.e., through values $x < x_0$ ($x - x_0 < 0$).
2. **Right-Hand Limit ($x \to x_0^+$):** We write $\lim_{x\to x_0^+} f(x) = L$ (or $\pm\infty$) when $x$ approaches $x_0$ exclusively from the right, i.e., through values $x > x_0$ ($x - x_0 > 0$).

### Criterion for the Existence of a Two-Sided Limit
The two-sided limit $\lim_{x\to x_0} f(x)$ exists (in $\mathbb{R}$ or as an improper limit $+\infty$ or $-\infty$) **if and only if** both one-sided limits exist and are equal:
$$\lim_{x\to x_0} f(x) = L \iff \lim_{x\to x_0^-} f(x) = \lim_{x\to x_0^+} f(x) = L.$$
If $\lim_{x\to x_0^-} f(x) \neq \lim_{x\to x_0^+} f(x)$ (for instance, one is $-\infty$ and the other is $+\infty$), then the two-sided limit $\lim_{x\to x_0} f(x)$ **does not exist**.

### Reciprocal Limit Rule $\left[\frac{c}{0^\pm}\right]$ and Vertical Asymptotes
- If $\lim_{x\to x_0^\pm} g(x) = c \neq 0$ and $\lim_{x\to x_0^\pm} h(x) = 0$ while $h(x)$ maintains a constant sign near $x_0^\pm$, then $\left|\frac{g(x)}{h(x)}\right| \to +\infty$, and the sign of the infinite limit is determined by the sign of $\frac{c}{h(x)}$:
  $$\left[\frac{1}{0^-}\right] = -\infty, \qquad \left[\frac{1}{0^+}\right] = +\infty.$$
- **Vertical Asymptote:** The vertical line $x = x_0$ is called a **vertical asymptote** of the graph of $y = f(x)$ if at least one of the one-sided limits $\lim_{x\to x_0^-} f(x)$ or $\lim_{x\to x_0^+} f(x)$ equals $+\infty$ or $-\infty$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Domain and Behavior of Numerator and Denominator Near $x = 2$
The function $f(x) = \frac{1}{x-2}$ has domain $D_f = \mathbb{R} \setminus \{2\} = (-\infty, 2) \cup (2, \infty)$.
As $x \to 2$:
- The numerator is the positive constant $1 > 0$.
- The denominator $x - 2$ approaches $2 - 2 = 0$, so its absolute value $|x - 2|$ becomes arbitrarily small, causing $\left|\frac{1}{x-2}\right| = \frac{1}{|x-2|} \to +\infty$.
However, the **sign** of $x - 2$ changes depending on which side of $2$ the variable $x$ lies on. Therefore, we must analyze the left-hand and right-hand limits separately.

### Step 2: Left-Hand Limit as $x \to 2^-$
When $x \to 2^-$, we have $x < 2$, which implies:
$$x - 2 < 0.$$
Thus, as $x$ approaches $2$ from the left, the denominator $x - 2$ approaches $0$ through **strictly negative** values (denoted $0^-$). Since the numerator is $+1 > 0$ and the denominator is negative and arbitrarily small in magnitude, the quotient $\frac{1}{x-2}$ is negative and grows arbitrarily large in absolute value:
$$\lim_{x\to 2^-} \frac{1}{x-2} = \left[\frac{1}{0^-}\right] = -\infty.$$

*(Rigorous $M$-$\delta$ justification: For any $M > 0$, choose $\delta = \frac{1}{M} > 0$. Whenever $2 - \delta < x < 2$, we have $-\frac{1}{M} < x - 2 < 0$, so $\frac{1}{x-2} < -M$.)*

### Step 3: Right-Hand Limit as $x \to 2^+$
When $x \to 2^+$, we have $x > 2$, which implies:
$$x - 2 > 0.$$
Thus, as $x$ approaches $2$ from the right, the denominator $x - 2$ approaches $0$ through **strictly positive** values (denoted $0^+$). Since the numerator is $+1 > 0$ and the denominator is positive and arbitrarily small, the quotient $\frac{1}{x-2}$ is positive and grows without bound:
$$\lim_{x\to 2^+} \frac{1}{x-2} = \left[\frac{1}{0^+}\right] = +\infty.$$

*(Rigorous $M$-$\delta$ justification: For any $M > 0$, choose $\delta = \frac{1}{M} > 0$. Whenever $2 < x < 2 + \delta$, we have $0 < x - 2 < \frac{1}{M}$, so $\frac{1}{x-2} > M$.)*

### Step 4: Existence of the Two-Sided Limit
Comparing the two one-sided limits:
$$\lim_{x\to 2^-} \frac{1}{x-2} = -\infty \quad \neq \quad \lim_{x\to 2^+} \frac{1}{x-2} = +\infty.$$
Because the left-hand limit and the right-hand limit disagree in sign ($-\infty \neq +\infty$), **the two-sided limit $\lim_{x\to 2} \frac{1}{x-2}$ does not exist** (not even as an improper limit $+\infty$ or $-\infty$).

### Step 5: Vertical Asymptote and Sketch of the Graph
Because $\lim_{x\to 2^-} f(x) = -\infty$ and $\lim_{x\to 2^+} f(x) = +\infty$, the vertical line
$$x = 2$$
is a **vertical asymptote** of the graph of $f(x) = \frac{1}{x-2}$. (Additionally, since $\lim_{x\to \pm\infty} \frac{1}{x-2} = 0$, the horizontal line $y = 0$, i.e., the $x$-axis, is a horizontal asymptote.)

Below is an aligned ASCII sketch of the hyperbola $f(x) = \frac{1}{x-2}$ showing the coordinate axes, the dashed vertical asymptote $x = 2$, the left branch plunging to $-\infty$ as $x \to 2^-$, and the right branch rising to $+\infty$ as $x \to 2^+$:

```text
                       y
                       ^
                     4 +           |  *
                       |           |  *
                     2 +           |   *       y = 1 / (x - 2)
                       |           |    *
                     1 +           |      *
                       |           |          *       *
   --------------------+-----------+-----+-----+---------*----> x
   -2     -1      0    |     1     |     3     4     5
        *       *      |           |
              *     -1 +           |
                 *     |           |
                   * -2 +          |
                    *  |           |
                    * -4 +         |
                       |           |
                                 x = 2
                          (vertical asymptote)
```

**Geometric Interpretation:**
- On the **left side of $x = 2$** ($x < 2$), the curve lies below the $x$-axis ($f(x) < 0$). As $x$ moves closer to $2$ from the left ($x \to 2^-$), the curve drops steeply downward along the left side of the vertical line $x = 2$ toward $-\infty$.
- On the **right side of $x = 2$** ($x > 2$), the curve lies above the $x$-axis ($f(x) > 0$). As $x$ moves closer to $2$ from the right ($x \to 2^+$), the curve shoots steeply upward along the right side of the vertical line $x = 2$ toward $+\infty$.

---

## 4. Verification and Consistency Checks

### Numerical Table Approaching $x = 2$ from Left and Right
Let us compute $f(x) = \frac{1}{x-2}$ for values of $x$ approaching $2$ from the left ($x < 2$) and from the right ($x > 2$):

| Left Approach ($x \to 2^-$) | $x - 2$ | $f(x) = \frac{1}{x-2}$ | Right Approach ($x \to 2^+$) | $x - 2$ | $f(x) = \frac{1}{x-2}$ |
| :--- | :--- | :--- | :--- | :--- | :--- |
| $1.9$ | $-0.1$ | $-10$ | $2.1$ | $+0.1$ | $+10$ |
| $1.99$ | $-0.01$ | $-100$ | $2.01$ | $+0.01$ | $+100$ |
| $1.999$ | $-0.001$ | $-1{,}000$ | $2.001$ | $+0.001$ | $+1{,}000$ |
| $1.9999$ | $-0.0001$ | $-10{,}000$ | $2.0001$ | $+0.0001$ | $+10{,}000$ |
| **Limit $x \to 2^-$** | **$0^-$** | **$-\infty$** | **Limit $x \to 2^+$** | **$0^+$** | **$+\infty$** |

### Symmetry Consistency Check
Notice that $f(2 + h) = \frac{1}{(2+h)-2} = \frac{1}{h}$ and $f(2 - h) = \frac{1}{(2-h)-2} = -\frac{1}{h} = -f(2 + h)$. Thus the graph of $f(x) = \frac{1}{x-2}$ is simply the standard hyperbola $y = \frac{1}{h}$ shifted $2$ units to the right, and is centrally symmetric about the point $(2, 0)$. This confirms why the right-hand limit $+\infty$ and the left-hand limit $-\infty$ have opposite signs.

### Final Conclusion
$$\boxed{\lim_{x\to 2^-}\frac{1}{x-2} = -\infty, \quad \lim_{x\to 2^+}\frac{1}{x-2} = +\infty, \quad \lim_{x\to 2}\frac{1}{x-2} \text{ DNE; vertical asymptote: } x = 2}$$
