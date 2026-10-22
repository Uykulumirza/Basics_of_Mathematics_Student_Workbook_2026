# Solution to Problem 15: Find the Error in the Monotonicity Analysis

## 1. Problem Statement
For the function
$$f(x)=x^3-3x$$
the derivative was correctly computed as
$$f'(x)=3(x-1)(x+1).$$

However, a student wrote the following conclusion:

> The derivative is positive between its zeros and negative outside them. Therefore, the function is decreasing on $(-\infty,-1)\cup(1,\infty)$, increasing on $(-1,1)$, has a local minimum at $x=-1$, and a local maximum at $x=1$.

1. Without differentiating again, explain why merely identifying the zeros of the derivative does not justify the stated sign chart, and find the error in the student's reasoning.
2. Construct the correct sign chart for $f'(x)$.
3. Give the correct intervals of monotonicity and the character of the extrema.
4. In each of the three intervals, choose one simple test point and show that the sign of the derivative confirms your classification.

> **Why this problem:** it teaches how to diagnose an error in a completed argument and shows that a correct derivative formula is not enough if its sign is interpreted incorrectly.

---

## 2. Theoretical Background and Concepts
1. **Sign of a Factored Quadratic $P(x) = a(x - x_1)(x - x_2)$ with $x_1 < x_2$:**
   Knowing the roots $x_1, x_2$ tells us only where $P(x) = 0$. The signs on the three intervals $(-\infty, x_1)$, $(x_1, x_2)$, and $(x_2, \infty)$ depend critically on the **sign of the leading coefficient $a \neq 0$**:
   - If **$a > 0$** (parabola opens **upward**, $\cup$): $P(x) > 0$ outside the roots $(-\infty, x_1) \cup (x_2, \infty)$, and $P(x) < 0$ between the roots $(x_1, x_2)$.
   - If **$a < 0$** (parabola opens **downward**, $\cap$): $P(x) < 0$ outside the roots $(-\infty, x_1) \cup (x_2, \infty)$, and $P(x) > 0$ between the roots $(x_1, x_2)$.
2. **Interval Statement of Monotonicity:** Even when a function has the same derivative sign on two disjoint intervals $(-\infty, -1)$ and $(1, \infty)$, monotonicity should be stated on each interval separately rather than on their set union.

---

## 3. Detailed Step-by-Step Solution

### Part 1: Diagnosing the Error in the Student's Reasoning
1. **Why zeros alone do not determine the sign chart:**
   The zeros $x = -1$ and $x = 1$ only partition the real line into three intervals $(-\infty, -1)$, $(-1, 1)$, and $(1, \infty)$ on each of which the continuous function $f'(x)$ has a constant sign. However, both $f'(x) = +3(x - 1)(x + 1)$ and $-f'(x) = -3(x - 1)(x + 1)$ have the **exact same zeros** $x = \pm 1$, yet they have **completely opposite signs** on every interval! To know which sign pattern holds, one must inspect the **leading coefficient** (or the signs of the individual factors / test points).
2. **The Specific Error Made by the Student:**
   In $f'(x) = 3(x - 1)(x + 1) = 3x^2 - 3$, the leading coefficient is **$a = +3 > 0$**, so the graph of the derivative $y = f'(x)$ is an **upward-opening parabola** ($\cup$). An upward-opening parabola lies **below** the $x$-axis (is **negative**) between its roots $(-1, 1)$ and lies **above** the $x$-axis (is **positive**) outside its roots $(-\infty, -1) \cup (1, \infty)$.
   - The student **reversed the sign of $f'(x)$ on every interval**, mistakenly treating $f'(x)$ as if its parabola opened downward ($a < 0$). Because every sign in the student's chart was flipped, every monotonicity conclusion and every extremum classification (swapping maximum and minimum) was inverted.
   - *(Secondary precision note)*: Additionally, writing that a function is decreasing/increasing on the union $(-\infty, -1) \cup (1, \infty)$ is imprecise; monotonicity should be stated separately on $(-\infty, -1]$ and on $[1, \infty)$.

---

### Part 2: Correct Sign Chart for $f'(x) = 3(x - 1)(x + 1)$
We track the sign of each factor across the critical points $x = -1$ and $x = 1$:

| Interval / Point | $(-\infty, -1)$ | $x = -1$ | $(-1, 1)$ | $x = 1$ | $(1, \infty)$ |
| :---: | :---: | :---: | :---: | :---: | :---: |
| Sign of constant $3$ | $+$ | $+$ | $+$ | $+$ | $+$ |
| Sign of $(x + 1)$ | $-$ | $0$ | $+$ | $+$ | $+$ |
| Sign of $(x - 1)$ | $-$ | $-$ | $-$ | $0$ | $+$ |
| **Sign of $f'(x) = 3(x-1)(x+1)$** | **$+$** | **$0$** | **$-$** | **$0$** | **$+$** |
| **Behavior of $f(x)$** | $\nearrow$ (strictly increasing) | **Local Maximum** ($2$) | $\searrow$ (strictly decreasing) | **Local Minimum** ($-2$) | $\nearrow$ (strictly increasing) |

Hence:
- $f'(x) > 0$ on $(-\infty, -1) \cup (1, \infty)$,
- $f'(x) = 0$ at $x = -1$ and $x = 1$,
- $f'(x) < 0$ on $(-1, 1)$.

---

### Part 3: Correct Intervals of Monotonicity and Character of the Extrema
1. **Intervals of Monotonicity:**
   - $f$ is **strictly increasing** on $(-\infty, -1]$ and on $[1, \infty)$.
   - $f$ is **strictly decreasing** on $[-1, 1]$.
2. **Character and Values of the Local Extrema:**
   - At **$x = -1$**: As $x$ passes through $-1$ from left to right, $f'(x)$ changes sign from **positive ($+$) to negative ($-$)**. Therefore, $f$ attains a **strict local maximum** at $x = -1$, with value:
     $$f_{\max} = f(-1) = (-1)^3 - 3(-1) = -1 + 3 = 2 \quad \longrightarrow \quad (-1, 2).$$
   - At **$x = 1$**: As $x$ passes through $1$ from left to right, $f'(x)$ changes sign from **negative ($-$) to positive ($+$)**. Therefore, $f$ attains a **strict local minimum** at $x = 1$, with value:
     $$f_{\min} = f(1) = (1)^3 - 3(1) = 1 - 3 = -2 \quad \longrightarrow \quad (1, -2).$$

---

### Part 4: Verification Using Simple Test Points in Each Interval
We select one convenient integer test point inside each of the three open intervals and evaluate $f'(x) = 3(x - 1)(x + 1)$ directly:

1. **Left Interval $(-\infty, -1)$ — Test point $x = -2$:**
   $$f'(-2) = 3(-2 - 1)(-2 + 1) = 3(-3)(-1) = +9 > 0.$$
   Since $f'(-2) > 0$, $f'(x)$ is **positive** on $(-\infty, -1)$, confirming that $f$ is **strictly increasing** on $(-\infty, -1]$.

2. **Middle Interval $(-1, 1)$ — Test point $x = 0$:**
   $$f'(0) = 3(0 - 1)(0 + 1) = 3(-1)(+1) = -3 < 0.$$
   Since $f'(0) < 0$, $f'(x)$ is **negative** on $(-1, 1)$, confirming that $f$ is **strictly decreasing** on $[-1, 1]$.

3. **Right Interval $(1, \infty)$ — Test point $x = 2$:**
   $$f'(2) = 3(2 - 1)(2 + 1) = 3(+1)(+3) = +9 > 0.$$
   Since $f'(2) > 0$, $f'(x)$ is **positive** on $(1, \infty)$, confirming that $f$ is **strictly increasing** on $[1, \infty)$.

---

## 4. Verification and Consistency Checks
1. **Direct Function Value Comparison:**
   Evaluating $f(x) = x^3 - 3x$ at $x = -2, -1, 0, 1, 2$:
   $$f(-2) = -2 \xrightarrow{\nearrow} f(-1) = 2 \xrightarrow{\searrow} f(0) = 0 \xrightarrow{\searrow} f(1) = -2 \xrightarrow{\nearrow} f(2) = 2.$$
   Notice that $f(-1) = 2 > f(1) = -2$: on $[-1, 1]$, the function drops from $2$ down to $-2$, which directly contradicts the student's claim that $f$ is increasing on $(-1, 1)$!
2. **End Behavior Consistency:** Since $\lim_{x \to -\infty} (x^3 - 3x) = -\infty$ and $\lim_{x \to +\infty} (x^3 - 3x) = +\infty$, the cubic must start by increasing from $-\infty$ to its first extremum (making $x = -1$ a local maximum) and finish by increasing from its second extremum (making $x = 1$ a local minimum) toward $+\infty$.
