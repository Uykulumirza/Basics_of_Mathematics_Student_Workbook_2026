# Solution: Exercise 6 — Projection and Perpendicular Component

## 1. Problem Statement
Find the projection of $u=(4,2)$ onto the direction $v=(1,1)$. Then compute
$$r=u-\operatorname{proj}_v u$$
and verify that $r\cdot v=0$. Explain this result geometrically.

---

## 2. Theoretical Background and Concepts
Given a vector $u$ and a non-zero direction vector $v \neq \mathbf{0}$, the **orthogonal projection** of $u$ onto $v$, denoted $\operatorname{proj}_v u$, is the vector lying on the line spanned by $v$ obtained by dropping a perpendicular from the tip of $u$ to the line of $v$:
$$\operatorname{proj}_v u = \left(\frac{u \cdot v}{v \cdot v}\right)v = \left(\frac{u \cdot v}{\|v\|^2}\right)v.$$
Subtracting this parallel component from $u$ leaves the **residual (perpendicular) component**:
$$r = u - \operatorname{proj}_v u.$$
By construction, $r$ satisfies $(u - \operatorname{proj}_v u) \cdot v = u \cdot v - \frac{u \cdot v}{v \cdot v}(v \cdot v) = 0$, meaning $r$ is orthogonal to $v$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the orthogonal projection $\operatorname{proj}_v u$
For $u = (4, 2)$ and $v = (1, 1)$, we first compute the dot product $u \cdot v$ and the squared norm $\|v\|^2 = v \cdot v$:
$$u \cdot v = (4)(1) + (2)(1) = 4 + 2 = 6,$$
$$\|v\|^2 = v \cdot v = 1^2 + 1^2 = 2.$$
Substituting these values into the projection formula gives:
$$\operatorname{proj}_v u = \frac{u \cdot v}{\|v\|^2}v = \frac{6}{2}(1, 1) = 3(1, 1) = (3, 3).$$

### Step 2: Compute the residual vector $r = u - \operatorname{proj}_v u$
Subtracting $\operatorname{proj}_v u = (3, 3)$ from $u = (4, 2)$ component-wise:
$$r = u - \operatorname{proj}_v u = (4, 2) - (3, 3) = (4 - 3,\; 2 - 3) = (1, -1).$$

### Step 3: Verify that $r \cdot v = 0$
Computing the dot product of $r = (1, -1)$ and $v = (1, 1)$:
$$r \cdot v = (1)(1) + (-1)(1) = 1 - 1 = 0.$$
This confirms that $r$ is strictly perpendicular to $v$.

### Step 4: Geometric explanation
Geometrically, $u$ is decomposed into two mutually perpendicular vectors that form the legs of a right triangle with hypotenuse $u$:
- $\operatorname{proj}_v u = (3, 3)$ is the **shadow** (parallel component) of $u$ cast orthogonally onto the line $y = x$ directed by $v = (1, 1)$.
- $r = u - \operatorname{proj}_v u = (1, -1)$ is the **altitude** (or perpendicular error vector) pointing from the tip of the shadow $(3, 3)$ on the line of $v$ directly to the tip of $u = (4, 2)$. Because an altitude dropped to a line meets that line at a right angle ($90^\circ$), $r$ is perpendicular to $v$, which algebraically means $r \cdot v = 0$.

---

## 4. Verification and Consistency Checks

### Reconstruction Check
Adding the parallel projection and the perpendicular residual recovers $u$:
$$\operatorname{proj}_v u + r = (3, 3) + (1, -1) = (4, 2) = u.$$

### Pythagorean Theorem Check
Since $\operatorname{proj}_v u \perp r$, their squared lengths must sum to $\|u\|^2$:
- $\|\operatorname{proj}_v u\|^2 = 3^2 + 3^2 = 9 + 9 = 18$
- $\|r\|^2 = 1^2 + (-1)^2 = 1 + 1 = 2$
- $\|u\|^2 = 4^2 + 2^2 = 16 + 4 = 20$

Indeed, $\|\operatorname{proj}_v u\|^2 + \|r\|^2 = 18 + 2 = 20 = \|u\|^2$.
