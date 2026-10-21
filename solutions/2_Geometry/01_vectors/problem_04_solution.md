# Solution: Exercise 4 — Dot Product and Perpendicularity

## 1. Problem Statement
For $u=(1,2,-1)$ and $v=(2,-1,3)$ compute $u\cdot v$ and determine whether the vectors are perpendicular. Then find $a$ so that $w=(2,-1,a)$ is perpendicular to $u$, and check the result.

---

## 2. Theoretical Background and Concepts
- **Algebraic Definition of the Dot Product:** For two vectors $u = (u_1, u_2, u_3)$ and $v = (v_1, v_2, v_3)$ in $\mathbb{R}^3$, their dot (scalar) product is the sum of the products of their corresponding components:
  $$u \cdot v = u_1 v_1 + u_2 v_2 + u_3 v_3.$$
- **Geometric Interpretation and Orthogonality Criterion:** Geometrically, the dot product is related to the angle $\theta \in [0, \pi]$ between two non-zero vectors by:
  $$u \cdot v = \|u\|\,\|v\|\cos\theta.$$
  Since $\|u\| > 0$ and $\|v\| > 0$ for non-zero vectors, $\cos\theta = 0$ (which means $\theta = \frac{\pi}{2} = 90^\circ$) holds if and only if the dot product vanishes:
  $$u \perp v \iff u \cdot v = 0.$$
  This turns the dot product into both an immediate test for perpendicularity and a linear equation generator for constructing perpendicular vectors.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $u \cdot v$ and test for perpendicularity
Given $u = (1, 2, -1)$ and $v = (2, -1, 3)$, we multiply corresponding coordinates and sum the results:
$$u \cdot v = (1)(2) + (2)(-1) + (-1)(3) = 2 - 2 - 3 = -3.$$
Since $u \cdot v = -3 \neq 0$, the vectors $u$ and $v$ are **not perpendicular** (in fact, because $u \cdot v < 0$, the angle between them is obtuse).

### Step 2: Find $a$ so that $w = (2, -1, a)$ is perpendicular to $u$
For $w = (2, -1, a)$ to be perpendicular to $u = (1, 2, -1)$, their dot product must equal zero:
$$u \cdot w = 0.$$
Writing out the dot product in terms of $a$:
$$(1)(2) + (2)(-1) + (-1)(a) = 0$$
$$2 - 2 - a = 0$$
$$-a = 0 \implies a = 0.$$
Thus, the required parameter is $a = 0$, giving the vector $w = (2, -1, 0)$.

---

## 4. Verification and Consistency Checks

### Explicit Orthogonality Check
Substituting $a = 0$ into $w = (2, -1, 0)$ and computing the dot product with $u = (1, 2, -1)$:
$$u \cdot w = (1, 2, -1) \cdot (2, -1, 0) = (1)(2) + (2)(-1) + (-1)(0) = 2 - 2 + 0 = 0.$$
Since $u \cdot w = 0$ and both vectors are non-zero, $w = (2, -1, 0)$ is indeed perpendicular to $u$.

### Pythagorean Check of Perpendicularity
Two vectors $u$ and $w$ are perpendicular if and only if they satisfy the Pythagorean relation $\|u - w\|^2 = \|u\|^2 + \|w\|^2$:
- $\|u\|^2 = 1^2 + 2^2 + (-1)^2 = 1 + 4 + 1 = 6$
- $\|w\|^2 = 2^2 + (-1)^2 + 0^2 = 4 + 1 + 0 = 5$
- $u - w = (1 - 2, 2 - (-1), -1 - 0) = (-1, 3, -1)$, so $\|u - w\|^2 = (-1)^2 + 3^2 + (-1)^2 = 1 + 9 + 1 = 11$

Indeed, $\|u\|^2 + \|w\|^2 = 6 + 5 = 11 = \|u - w\|^2$, confirming right-triangle geometry between $u$ and $w$.
