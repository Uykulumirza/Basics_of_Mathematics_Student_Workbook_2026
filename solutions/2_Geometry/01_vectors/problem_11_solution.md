# Solution: Exercise 11 — Decomposition into Parallel and Perpendicular Components

## 1. Problem Statement
Decompose $u=(3,4)$ into components parallel and perpendicular to $v=(1,2)$. Check
$$u=u_{\parallel}+u_{\perp},\qquad u_{\perp}\cdot v=0.$$
Explain why these are two independent checks of correctness.

---

## 2. Theoretical Background and Concepts
Given a vector $u$ and a non-zero reference direction vector $v \neq \mathbf{0}$, the **orthogonal decomposition theorem** states that $u$ can be written uniquely as the sum of two vectors:
$$u = u_{\parallel} + u_{\perp},$$
where:
1. $u_{\parallel} = \operatorname{proj}_v u = \left(\frac{u \cdot v}{v \cdot v}\right)v$ is **parallel** (collinear) to $v$, i.e., $u_{\parallel} = \lambda v$ for the scalar $\lambda = \frac{u \cdot v}{\|v\|^2}$.
2. $u_{\perp} = u - u_{\parallel}$ is **perpendicular** (orthogonal) to $v$, i.e., $u_{\perp} \cdot v = 0$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the parallel component $u_{\parallel}$
For $u = (3, 4)$ and $v = (1, 2)$, we compute $u \cdot v$ and $v \cdot v = \|v\|^2$:
$$u \cdot v = (3)(1) + (4)(2) = 3 + 8 = 11,$$
$$\|v\|^2 = v \cdot v = 1^2 + 2^2 = 1 + 4 = 5.$$
Therefore, the component of $u$ parallel to $v$ is:
$$u_{\parallel} = \operatorname{proj}_v u = \frac{u \cdot v}{\|v\|^2}v = \frac{11}{5}(1, 2) = \left(\frac{11}{5},\; \frac{22}{5}\right).$$

### Step 2: Compute the perpendicular component $u_{\perp}$
Subtracting $u_{\parallel}$ from $u = (3, 4) = \left(\frac{15}{5}, \frac{20}{5}\right)$ gives:
$$u_{\perp} = u - u_{\parallel} = \left(\frac{15}{5} - \frac{11}{5},\; \frac{20}{5} - \frac{22}{5}\right) = \left(\frac{4}{5},\; -\frac{2}{5}\right).$$

### Step 3: Perform the two required checks
1. **Sum (Completeness) Check ($u = u_{\parallel} + u_{\perp}$):**
   $$u_{\parallel} + u_{\perp} = \left(\frac{11}{5},\; \frac{22}{5}\right) + \left(\frac{4}{5},\; -\frac{2}{5}\right) = \left(\frac{11 + 4}{5},\; \frac{22 - 2}{5}\right) = \left(\frac{15}{5},\; \frac{20}{5}\right) = (3, 4) = u.$$
2. **Orthogonality Check ($u_{\perp} \cdot v = 0$):**
   $$u_{\perp} \cdot v = \left(\frac{4}{5},\; -\frac{2}{5}\right) \cdot (1, 2) = \left(\frac{4}{5}\right)(1) + \left(-\frac{2}{5}\right)(2) = \frac{4}{5} - \frac{4}{5} = 0.$$

### Step 4: Explain why these are two independent checks of correctness
Once $u_{\parallel}$ is chosen as a scalar multiple of $v$ ($u_{\parallel} = \lambda v$), the two conditions $u = u_{\parallel} + u_{\perp}$ and $u_{\perp} \cdot v = 0$ test two logically distinct requirements that can fail independently if an error is made:
1. **Why $u = u_{\parallel} + u_{\perp}$ alone is not enough:** Any choice of scalar $\lambda$—even a completely wrong projection coefficient—will satisfy $u = u_{\parallel} + u_{\perp}$ as long as we define $u_{\perp} = u - \lambda v$ without an arithmetic mistake. For example, if we mistakenly took $u_{\parallel} = (1, 2)$ and $u_{\perp} = (2, 2)$, their sum is still $(3, 4) = u$, so the first check passes, yet $u_{\perp} \cdot v = 2 + 4 = 6 \neq 0$ fails. Thus, the sum check only verifies the **algebraic subtraction** $u_{\perp} = u - u_{\parallel}$ (completeness of the decomposition), not that $u_{\parallel}$ was projected with the right coefficient.
2. **Why $u_{\perp} \cdot v = 0$ alone is not enough:** Conversely, any scalar multiple of $(2, -1)$ is perpendicular to $v = (1, 2)$—for example, $u_{\perp} = (2, -1)$ satisfies $u_{\perp} \cdot v = 0$, or if we made a scaling error in $u_{\perp}$ after computing $u_{\parallel}$, $u_{\perp} \cdot v = 0$ could still hold while $u_{\parallel} + u_{\perp} \neq u$. Thus, the dot-product check verifies **orthogonality** (and the correctness of the projection scalar $\lambda = 11/5$), whereas the sum check verifies that the two pieces actually reconstruct the original vector $u$.

Together with $u_{\parallel} \parallel v$, both checks are necessary and jointly sufficient to guarantee the unique orthogonal decomposition of $u$.

---

## 4. Verification and Consistency Checks

### Pythagorean Norm Check
Since $u_{\parallel} \perp u_{\perp}$, we also have $u_{\parallel} \cdot u_{\perp} = 0$, so $\|u_{\parallel}\|^2 + \|u_{\perp}\|^2$ must equal $\|u\|^2$:
- $\|u_{\parallel}\|^2 = \left(\frac{11}{5}\right)^2 + \left(\frac{22}{5}\right)^2 = \frac{121 + 484}{25} = \frac{605}{25} = \frac{121}{5}$
- $\|u_{\perp}\|^2 = \left(\frac{4}{5}\right)^2 + \left(-\frac{2}{5}\right)^2 = \frac{16 + 4}{25} = \frac{20}{25} = \frac{4}{5}$
- $\|u_{\parallel}\|^2 + \|u_{\perp}\|^2 = \frac{121}{5} + \frac{4}{5} = \frac{125}{5} = 25 = 3^2 + 4^2 = \|u\|^2$.
