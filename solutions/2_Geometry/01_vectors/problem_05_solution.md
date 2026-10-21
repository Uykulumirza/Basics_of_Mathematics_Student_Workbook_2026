# Solution: Exercise 5 — Angle Between Vectors

## 1. Problem Statement
Given $u=(1,1,0)$ and $v=(1,0,1)$:

1. Use the sign of $u\cdot v$ to predict the type of angle.
2. Compute the angle.
3. Compare the result with the prediction.

---

## 2. Theoretical Background and Concepts
For any two non-zero vectors $u, v \in \mathbb{R}^3$, the angle $\theta \in [0, \pi]$ between them satisfies the dot product identity:
$$u \cdot v = \|u\|\,\|v\|\cos\theta \implies \cos\theta = \frac{u \cdot v}{\|u\|\,\|v\|}.$$
Because the norms $\|u\|$ and $\|v\|$ are strictly positive, the algebraic sign of $u \cdot v$ is identical to the sign of $\cos\theta$:
- If $u \cdot v > 0$, then $\cos\theta > 0$, so $\theta \in \left[0, \frac{\pi}{2}\right)$ (an **acute** angle, or $0$ if collinear).
- If $u \cdot v = 0$, then $\cos\theta = 0$, so $\theta = \frac{\pi}{2} = 90^\circ$ (a **right** angle).
- If $u \cdot v < 0$, then $\cos\theta < 0$, so $\theta \in \left(\frac{\pi}{2}, \pi\right]$ (an **obtuse** angle, or $\pi$ if opposite).

This allows us to determine the qualitative nature of the angle using only simple multiplication and addition before computing any square roots or inverse trigonometric functions.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $u \cdot v$ and predict the type of angle
For $u = (1, 1, 0)$ and $v = (1, 0, 1)$, the dot product is:
$$u \cdot v = (1)(1) + (1)(0) + (0)(1) = 1 + 0 + 0 = 1.$$
Since $u \cdot v = 1 > 0$ (and $u$ is not a scalar multiple of $v$), $\cos\theta > 0$, which predicts that the angle $\theta$ between $u$ and $v$ is **strictly acute** ($\theta \in (0, \pi/2)$ or $0^\circ < \theta < 90^\circ$).

### Step 2: Compute the exact angle $\theta$
First, we compute the Euclidean norms of $u$ and $v$:
$$\|u\| = \sqrt{1^2 + 1^2 + 0^2} = \sqrt{1 + 1 + 0} = \sqrt{2},$$
$$\|v\| = \sqrt{1^2 + 0^2 + 1^2} = \sqrt{1 + 0 + 1} = \sqrt{2}.$$
Next, we substitute $u \cdot v = 1$, $\|u\| = \sqrt{2}$, and $\|v\| = \sqrt{2}$ into the cosine formula:
$$\cos\theta = \frac{u \cdot v}{\|u\|\,\|v\|} = \frac{1}{\sqrt{2}\cdot\sqrt{2}} = \frac{1}{2}.$$
Since $\theta \in [0, \pi]$, taking the inverse cosine gives:
$$\theta = \arccos\left(\frac{1}{2}\right) = \frac{\pi}{3}\text{ radians} = 60^\circ.$$

### Step 3: Compare the result with the prediction
Our exact calculation yielded $\theta = 60^\circ = \frac{\pi}{3}$. Since $0^\circ < 60^\circ < 90^\circ$ (i.e., $0 < \frac{\pi}{3} < \frac{\pi}{2}$), the angle is indeed **acute**, which is completely consistent with the qualitative prediction made in Step 1 from $u \cdot v > 0$.

---

## 4. Verification and Consistency Checks

### Geometric Verification via an Equilateral Triangle
Consider the triangle formed by the origin $O = (0,0,0)$ and the tips of the two vectors $A = (1,1,0)$ and $B = (1,0,1)$. The side lengths are:
- $\|u\| = d(O, A) = \sqrt{2}$
- $\|v\| = d(O, B) = \sqrt{2}$
- $\|u - v\| = \|(0, 1, -1)\| = \sqrt{0^2 + 1^2 + (-1)^2} = \sqrt{2}$

Because all three sides have equal length $\sqrt{2}$, triangle $OAB$ is an **equilateral triangle**, so every interior angle—including the angle $\theta$ at the origin between $u$ and $v$—must be exactly $60^\circ = \frac{\pi}{3}$.
