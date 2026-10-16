# Solution to Exercise 14: Involutory Matrices (Self-Inverse Matrices)

## 1. Problem Statement

1. Assume that a square matrix $A$ satisfies the algebraic condition:
   $$A^2 = I$$
   Prove rigorously from the definition of the inverse that:
   $$A^{-1} = A$$
2. Construct an explicit example of a $2 \times 2$ real matrix $A$ such that $A \ne I$ and $A \ne -I$ that satisfies $A^2 = I$.
3. Verify the example by direct matrix multiplication.

---

## 2. Theoretical Background and Concepts

### Involutory Matrices
A square matrix $A$ satisfying $A^2 = I$ is called an **involutory matrix**.
- An involution is any mathematical operator that is its own inverse: applying the operator twice restores the original object.
- In geometry, reflections (across a line or plane) and coordinate permutations are quintessential examples of involutions: reflecting a geometric figure across an axis and then reflecting it again across the same axis returns the figure to its initial state.

### Formal Definition of the Inverse Matrix
Recall that by definition, a matrix $B$ is the inverse of $A$ if and only if:
$$AB = I \qquad \text{and} \qquad BA = I$$
Furthermore, if an inverse exists, it is strictly unique.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Proof That $A^2 = I \implies A^{-1} = A$

We are given the identity:
$$A^2 = I$$

By definition of integer powers of a matrix:
$$A^2 = A \cdot A = I$$

Now, evaluate the definition of the inverse matrix:
1. Setting candidate matrix $B = A$:
   $$A B = A \cdot A = I$$
   $$B A = A \cdot A = I$$
2. Since multiplying $A$ by $A$ on both the right and the left yields the identity matrix $I$, matrix $A$ satisfies the defining condition of the inverse of $A$.
3. By the uniqueness of matrix inverses:
   $$A^{-1} = A$$

This completes the proof.

---

### Step 2: Construction of a $2 \times 2$ Example (Different from $\pm I$)

Let $A = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$. Compute $A^2$:
$$A^2 = \begin{pmatrix} a & b \\ c & d \end{pmatrix} \begin{pmatrix} a & b \\ c & d \end{pmatrix} = \begin{pmatrix} a^2 + bc & b(a + d) \\ c(a + d) & bc + d^2 \end{pmatrix}$$

For $A^2 = I_2 = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$, we require:
$$\begin{cases} a^2 + bc = 1 \\ b(a + d) = 0 \\ c(a + d) = 0 \\ d^2 + bc = 1 \end{cases}$$

To obtain a solution with $A \ne \pm I_2$, set $a + d = 0 \implies d = -a$ (the matrix must be traceless, $\operatorname{tr}(A) = 0$).
Then the system reduces to:
$$bc = 1 - a^2$$

#### Candidate 1 (Geometric Reflection Across the Line $y = x$):
Choose $a = 0, d = 0 \implies bc = 1$. Setting $b = 1, c = 1$:
$$A = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$$
Notice:
- $A \ne I_2$
- $A \ne -I_2$

#### Candidate 2 (Full Non-Zero Entry Example):
Choose $a = 2, d = -2 \implies bc = 1 - 2^2 = -3$. Setting $b = 3, c = -1$:
$$A = \begin{pmatrix} 2 & 3 \\ -1 & -2 \end{pmatrix}$$

Let us proceed with the elegant permutation/reflection matrix $A = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$ (and also check the non-zero entry candidate).

---

### Step 3: Verification by Direct Multiplication

Multiply $A = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$ by itself:
$$A^2 = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$$

Calculate each entry:
- Position $(1, 1)$: $0(0) + 1(1) = 1$
- Position $(1, 2)$: $0(1) + 1(0) = 0$
- Position $(2, 1)$: $1(0) + 0(1) = 0$
- Position $(2, 2)$: $1(1) + 0(0) = 1$

Thus:
$$A^2 = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I_2 \quad \checkmark$$

Because $A^2 = I_2$, its inverse is:
$$A^{-1} = A = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$$

---

## 4. Verification and Consistency Checks

1. **Independent Verification of Candidate 2 ($A = \begin{pmatrix} 2 & 3 \\ -1 & -2 \end{pmatrix}$):**
   $$A^2 = \begin{pmatrix} 2 & 3 \\ -1 & -2 \end{pmatrix} \begin{pmatrix} 2 & 3 \\ -1 & -2 \end{pmatrix} = \begin{pmatrix} 2(2) + 3(-1) & 2(3) + 3(-2) \\ -1(2) + (-2)(-1) & -1(3) + (-2)(-2) \end{pmatrix} = \begin{pmatrix} 4 - 3 & 6 - 6 \\ -2 + 2 & -3 + 4 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I_2 \quad \checkmark$$
   Using the $2 \times 2$ formula:
   $$\det A = (2)(-2) - (3)(-1) = -4 + 3 = -1$$
   $$A^{-1} = \frac{1}{-1} \begin{pmatrix} -2 & -3 \\ 1 & 2 \end{pmatrix} = \begin{pmatrix} 2 & 3 \\ -1 & -2 \end{pmatrix} = A \quad \checkmark$$

2. **Geometric Consistency (Reflection Across $y = x$):**
   Applying $A = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}$ to an arbitrary vector $(x, y)^T$:
   $$A \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} y \\ x \end{pmatrix}$$
   This swaps the $x$ and $y$ coordinates, which geometrically reflects the point across the line $y = x$.
   Applying it a second time:
   $$A \left( A \begin{pmatrix} x \\ y \end{pmatrix} \right) = A \begin{pmatrix} y \\ x \end{pmatrix} = \begin{pmatrix} x \\ y \end{pmatrix}$$
   Swapping coordinates twice returns the vector to its original coordinates, confirming $A^2 = I$.
