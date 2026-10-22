# Solution: Exercise 15 — Comparing Directions Using the Cosine of the Angle

## 1. Problem Statement
Given
$$a=(1,2,1),\qquad b=(2,4,2),\qquad c=(2,0,3).$$
For each pair, compute
$$\frac{u\cdot v}{\|u\|\,\|v\|}.$$
Order the pairs by increasing angle between the vectors. Explain why for $a$ and $b$ the value is $1$ even though the vectors have different lengths.

---

## 2. Theoretical Background and Concepts
For any pair of non-zero vectors $u, v \in \mathbb{R}^3$, the quantity
$$\cos\theta_{uv} = \frac{u \cdot v}{\|u\|\,\|v\|} = \left(\frac{u}{\|u\|}\right) \cdot \left(\frac{v}{\|v\|}\right)$$
is the cosine of the angle $\theta_{uv} \in [0, \pi]$ between $u$ and $v$.
- **Monotonicity of $\cos\theta$ on $[0, \pi]$:** Because the function $\theta \mapsto \cos\theta$ is **strictly decreasing** on the interval $[0, \pi]$ (decreasing from $\cos 0 = 1$ down to $\cos\pi = -1$), a **larger** cosine corresponds to a **smaller** angle:
  $$\cos\theta_1 > \cos\theta_2 \iff \theta_1 < \theta_2 \quad \text{for } \theta_1, \theta_2 \in [0, \pi].$$
- **Scale Invariance:** Replacing $v$ with $\lambda v$ for any positive scalar $\lambda > 0$ leaves $\cos\theta_{uv}$ completely invariant because the factor $\lambda$ cancels between the numerator and denominator.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the Euclidean norms of $a, b, c$
First, we compute the length of each vector:
- $\|a\| = \sqrt{1^2 + 2^2 + 1^2} = \sqrt{1 + 4 + 1} = \sqrt{6},$
- $\|b\| = \sqrt{2^2 + 4^2 + 2^2} = \sqrt{4 + 16 + 4} = \sqrt{24} = 2\sqrt{6},$
- $\|c\| = \sqrt{2^2 + 0^2 + 3^2} = \sqrt{4 + 0 + 9} = \sqrt{13}.$

### Step 2: Compute $\frac{u \cdot v}{\|u\|\,\|v\|}$ for each of the three pairs
1. **Pair $(a, b)$:**
   $$a \cdot b = (1)(2) + (2)(4) + (1)(2) = 2 + 8 + 2 = 12,$$
   $$\|a\|\,\|b\| = \sqrt{6} \cdot (2\sqrt{6}) = 2 \cdot 6 = 12,$$
   $$\cos\theta_{ab} = \frac{a \cdot b}{\|a\|\,\|b\|} = \frac{12}{12} = 1.$$
   Since $\cos\theta_{ab} = 1$, the angle between $a$ and $b$ is $\theta_{ab} = \arccos(1) = 0$.

2. **Pair $(a, c)$:**
   $$a \cdot c = (1)(2) + (2)(0) + (1)(3) = 2 + 0 + 3 = 5,$$
   $$\|a\|\,\|c\| = \sqrt{6}\cdot\sqrt{13} = \sqrt{78},$$
   $$\cos\theta_{ac} = \frac{a \cdot c}{\|a\|\,\|c\|} = \frac{5}{\sqrt{78}} = \frac{5\sqrt{78}}{78} \approx 0.5661.$$
   Thus, $\theta_{ac} = \arccos\left(\frac{5}{\sqrt{78}}\right) \approx 55.52^\circ$.

3. **Pair $(b, c)$:**
   $$b \cdot c = (2)(2) + (4)(0) + (2)(3) = 4 + 0 + 6 = 10,$$
   $$\|b\|\,\|c\| = (2\sqrt{6})\cdot\sqrt{13} = 2\sqrt{78},$$
   $$\cos\theta_{bc} = \frac{b \cdot c}{\|b\|\,\|c\|} = \frac{10}{2\sqrt{78}} = \frac{5}{\sqrt{78}} = \frac{5\sqrt{78}}{78} \approx 0.5661.$$
   Thus, $\theta_{bc} = \arccos\left(\frac{5}{\sqrt{78}}\right) \approx 55.52^\circ$.

### Step 3: Order the pairs by increasing angle between the vectors
Comparing the cosines on $[0, \pi]$, where $\cos\theta$ is strictly decreasing:
$$\cos\theta_{ab} = 1 > \cos\theta_{ac} = \cos\theta_{bc} = \frac{5}{\sqrt{78}} \approx 0.5661.$$
Therefore, ordering the pairs by **increasing angle** gives:
$$\theta_{ab} = 0 < \theta_{ac} = \theta_{bc} = \arccos\left(\frac{5}{\sqrt{78}}\right) \approx 55.52^\circ.$$
That is, the pair $(a, b)$ has the smallest angle ($0^\circ$), followed by the pairs $(a, c)$ and $(b, c)$, which are **tied** with the exact same angle $\arccos(5/\sqrt{78})$.

### Step 4: Explain why $\frac{a \cdot b}{\|a\|\,\|b\|} = 1$ even though $\|a\| \neq \|b\|$
Notice that $b = (2, 4, 2) = 2(1, 2, 1) = 2a$, so $b$ has twice the length of $a$ ($\|b\| = 2\|a\|$), but points in the **exact same direction and orientation** as $a$ ($\theta_{ab} = 0$). 

The formula $\frac{a \cdot b}{\|a\|\,\|b\|}$ can be grouped as the dot product of the **normalized unit vectors** $\hat{a} = \frac{a}{\|a\|}$ and $\hat{b} = \frac{b}{\|b\|}$:
$$\frac{a \cdot b}{\|a\|\,\|b\|} = \left(\frac{a}{\|a\|}\right) \cdot \left(\frac{b}{\|b\|}\right).$$
Dividing $a$ by $\|a\|$ and $b$ by $\|b\|$ strips away both vectors' lengths—normalizing both to unit length $1$—so that $\hat{b} = \frac{2a}{\|2a\|} = \frac{2a}{2\|a\|} = \frac{a}{\|a\|} = \hat{a}$, and their dot product is $\hat{a} \cdot \hat{a} = \|\hat{a}\|^2 = 1$. Algebraically, the scaling factor $2$ increases the dot product $a \cdot b = 2(a \cdot a) = 2\|a\|^2$ in the numerator by a factor of $2$, and simultaneously increases the norm $\|b\| = 2\|a\|$ in the denominator by the exact same factor of $2$, which cancels out completely:
$$\frac{a \cdot (2a)}{\|a\|\,\|2a\|} = \frac{2\|a\|^2}{2\|a\|^2} = 1.$$
For the exact same reason, $a$ and $b$ make the exact same angle with $c$ ($\cos\theta_{ac} = \cos\theta_{bc} = \frac{5}{\sqrt{78}}$), because angle is purely a property of direction, independent of vector length.

---

## 4. Verification and Consistency Checks

### Cauchy-Schwarz Inequality Check
For every pair of non-zero vectors $(u, v)$, the Cauchy–Schwarz inequality states that
$$\left|\frac{u \cdot v}{\|u\|\,\|v\|}\right| \le 1, \qquad \text{or equivalently} \qquad -1 \le \frac{u \cdot v}{\|u\|\,\|v\|} \le 1.$$
- **Equality with the absolute value:** $\left|\frac{u \cdot v}{\|u\|\,\|v\|}\right| = 1$ holds if and only if $u$ and $v$ are collinear (one is a **non-zero scalar multiple** of the other, $v = \lambda u$ with $\lambda \neq 0$, including both positive and negative multiples).
- **Signed equality without the absolute value:**
  - $\frac{u \cdot v}{\|u\|\,\|v\|} = +1$ holds if and only if $v = \lambda u$ for a **positive** scalar multiple $\lambda > 0$ (same direction, $\theta = 0$),
  - $\frac{u \cdot v}{\|u\|\,\|v\|} = -1$ holds if and only if $v = \lambda u$ for a **negative** scalar multiple $\lambda < 0$ (opposite direction, $\theta = \pi$).
- **Application to our pairs:**
  - For $(a, b)$: Since $b = 2a$ with positive scalar $\lambda = 2 > 0$, we obtain $\cos\theta_{ab} = \frac{a \cdot b}{\|a\|\,\|b\|} = +1$ (and $|\cos\theta_{ab}| = 1$).
  - For $(a, c)$ and $(b, c)$: $\frac{5}{\sqrt{78}} = \sqrt{\frac{25}{78}} < 1$, confirming a strictly positive acute angle between the non-collinear directions of $a$ (or $b$) and $c$.
