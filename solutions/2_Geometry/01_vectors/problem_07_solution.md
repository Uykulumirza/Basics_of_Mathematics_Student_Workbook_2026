# Solution: Exercise 7 — Linear Dependence Without Heavy Computation

## 1. Problem Statement
Given
$$u=(1,2,3),\qquad v=(2,4,6),\qquad w=(0,1,1).$$
Identify a specific relation between $u$ and $v$, decide whether the three vectors can be linearly independent, and explain why no long calculation is needed.

---

## 2. Theoretical Background and Concepts
- **Linear Dependence and Independence:** A set of vectors $\{v_1, v_2, \dots, v_k\}$ is **linearly independent** if the vector equation
  $$c_1 v_1 + c_2 v_2 + \dots + c_k v_k = \mathbf{0}$$
  has only the trivial solution $c_1 = c_2 = \dots = c_k = 0$. Conversely, the set is **linearly dependent** if there exist scalars $c_1, \dots, c_k$, **not all zero**, such that $c_1 v_1 + \dots + c_k v_k = \mathbf{0}$.
- **Subset Property of Linear Dependence:** If any subset of vectors (for example, a pair of vectors) is linearly dependent, then the entire larger set is automatically linearly dependent—because we can simply assign coefficient $0$ to all remaining vectors in the set.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify the specific relation between $u$ and $v$
Comparing the coordinates of $u = (1, 2, 3)$ and $v = (2, 4, 6)$ directly, we see that every component of $v$ is exactly twice the corresponding component of $u$:
$$v = (2, 4, 6) = 2(1, 2, 3) = 2u.$$
Geometrically, $u$ and $v$ are **collinear** (parallel vectors lying along the exact same line through the origin).

### Step 2: Decide whether the three vectors can be linearly independent
Rearranging the relation $v = 2u$ as $2u - v = \mathbf{0}$, we can immediately write a non-trivial linear combination of $\{u, v, w\}$ that equals the zero vector by choosing $c_1 = 2$, $c_2 = -1$, and $c_3 = 0$:
$$2u - 1v + 0w = 2(1, 2, 3) - 1(2, 4, 6) + 0(0, 1, 1) = (2 - 2,\; 4 - 4,\; 6 - 6) = (0, 0, 0) = \mathbf{0}.$$
Since $(c_1, c_2, c_3) = (2, -1, 0) \neq (0, 0, 0)$, the three vectors $u, v, w$ are **linearly dependent**; they **cannot** be linearly independent.

### Step 3: Explain why no long calculation is needed
No determinant evaluation, row reduction (Gaussian elimination), or $3 \times 3$ system solving is needed because **proportionality of two vectors in a set is sufficient to make the entire set linearly dependent**:
1. **Algebraic reason:** Once $v = 2u$ is observed by inspection, setting the coefficient of $w$ to $0$ immediately provides a non-zero solution $(2, -1, 0)$ to $c_1 u + c_2 v + c_3 w = \mathbf{0}$, regardless of what $w$ is.
2. **Geometric reason:** Three vectors in $\mathbb{R}^3$ are linearly independent if and only if they span a 3-dimensional volume (are non-coplanar). Because $u$ and $v$ lie on the same 1-dimensional line, adding a third vector $w$ can at most expand the span to a 2-dimensional plane—never to all of $\mathbb{R}^3$.

---

## 4. Verification and Consistency Checks

### Determinant / Cross Product Check
To confirm our structural conclusion computationally, note that in a $3 \times 3$ matrix whose rows are $u, v, w$:
$$\det\begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \\ 0 & 1 & 1 \end{pmatrix} = 0$$
because the second row is $2$ times the first row (a determinant with two proportional rows is identically zero). Equivalently, $u \times v = u \times (2u) = \mathbf{0}$, so the scalar triple product $(u \times v) \cdot w = \mathbf{0} \cdot w = 0$.
