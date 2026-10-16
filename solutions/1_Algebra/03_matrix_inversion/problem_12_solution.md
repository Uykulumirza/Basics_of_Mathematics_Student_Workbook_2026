# Solution to Exercise 12: Finding Inverses Using Algebraic Properties

## 1. Problem Statement

Given the inverse of an unknown square matrix $A$:
$$A^{-1} = \begin{pmatrix} 2 & -1 \\ -3 & 2 \end{pmatrix}$$

Without computing the original matrix $A$, determine each of the following inverse matrices and justify each step using the foundational algebraic properties of matrix inversion:
1. $(3A)^{-1}$
2. $(A^T)^{-1}$
3. $(A^2)^{-1}$

---

## 2. Theoretical Background and Concepts

### Key Algebraic Properties of Matrix Inverses
Let $A, B \in M_n(\mathbb{R})$ be invertible matrices, and let $c \in \mathbb{R} \setminus \{0\}$ be a non-zero scalar:

1. **Scalar Scaling Property:**
   $$(cA)^{-1} = \frac{1}{c} A^{-1}$$
   *Proof:* $(cA)\left(\frac{1}{c} A^{-1}\right) = \left(c \cdot \frac{1}{c}\right)(A A^{-1}) = 1 \cdot I = I$.

2. **Transpose-Inverse Commutativity:**
   $$(A^T)^{-1} = (A^{-1})^T$$
   *Proof:* Transposing the identity $A A^{-1} = I$ using the reverse-order transpose law $(MN)^T = N^T M^T$:
   $$(A A^{-1})^T = I^T \implies (A^{-1})^T A^T = I$$
   Similarly, transposing $A^{-1}A = I$ gives $A^T (A^{-1})^T = I$.
   By definition of the inverse, $(A^{-1})^T$ is the unique inverse of $A^T$.

3. **Power Property (Product of Inverses):**
   $$(A^k)^{-1} = (A^{-1})^k \quad \text{for all integers } k \ge 1$$
   *Proof:* For $k = 2$, applying the product formula $(MN)^{-1} = N^{-1} M^{-1}$ with $M = N = A$:
   $$(A^2)^{-1} = (AA)^{-1} = A^{-1} A^{-1} = (A^{-1})^2$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $(3A)^{-1}$
Apply the scalar scaling property with $c = 3$:
$$(3A)^{-1} = \frac{1}{3} A^{-1}$$

Substitute the given matrix $A^{-1}$:
$$(3A)^{-1} = \frac{1}{3} \begin{pmatrix} 2 & -1 \\ -3 & 2 \end{pmatrix} = \begin{pmatrix} \frac{2}{3} & -\frac{1}{3} \\ \frac{-3}{3} & \frac{2}{3} \end{pmatrix} = \begin{pmatrix} \frac{2}{3} & -\frac{1}{3} \\ -1 & \frac{2}{3} \end{pmatrix}$$

---

### Step 2: Compute $(A^T)^{-1}$
Apply the transpose-inverse commutativity property:
$$(A^T)^{-1} = (A^{-1})^T$$

Compute the transpose of $A^{-1}$ by swapping entries across the main diagonal:
$$(A^{-1})^T = \begin{pmatrix} 2 & -1 \\ -3 & 2 \end{pmatrix}^T = \begin{pmatrix} 2 & -3 \\ -1 & 2 \end{pmatrix}$$

Thus:
$$(A^T)^{-1} = \begin{pmatrix} 2 & -3 \\ -1 & 2 \end{pmatrix}$$

---

### Step 3: Compute $(A^2)^{-1}$
Apply the power property for $k = 2$:
$$(A^2)^{-1} = (A^{-1})^2 = A^{-1} A^{-1}$$

Multiply $A^{-1}$ by itself:
$$(A^{-1})^2 = \begin{pmatrix} 2 & -1 \\ -3 & 2 \end{pmatrix} \begin{pmatrix} 2 & -1 \\ -3 & 2 \end{pmatrix}$$

Evaluate each matrix element:
- Position $(1, 1)$: $2(2) + (-1)(-3) = 4 + 3 = 7$
- Position $(1, 2)$: $2(-1) + (-1)(2) = -2 - 2 = -4$
- Position $(2, 1)$: $-3(2) + 2(-3) = -6 - 6 = -12$
- Position $(2, 2)$: $-3(-1) + 2(2) = 3 + 4 = 7$

Thus:
$$(A^2)^{-1} = \begin{pmatrix} 7 & -4 \\ -12 & 7 \end{pmatrix}$$

---

## 4. Verification and Consistency Checks

1. **Independent Verification via Finding Matrix $A$:**
   Since $(A^{-1})^{-1} = A$, compute $A$ directly:
   $$\det(A^{-1}) = (2)(2) - (-1)(-3) = 4 - 3 = 1$$
   $$A = (A^{-1})^{-1} = \frac{1}{1} \begin{pmatrix} 2 & 1 \\ 3 & 2 \end{pmatrix} = \begin{pmatrix} 2 & 1 \\ 3 & 2 \end{pmatrix}$$

   Now independently verify each computed inverse using $A$:
   - **Check $(3A)^{-1}$:**
     $$3A = \begin{pmatrix} 6 & 3 \\ 9 & 6 \end{pmatrix}$$
     $$(3A) \begin{pmatrix} 2/3 & -1/3 \\ -1 & 2/3 \end{pmatrix} = \begin{pmatrix} 6(2/3) + 3(-1) & 6(-1/3) + 3(2/3) \\ 9(2/3) + 6(-1) & 9(-1/3) + 6(2/3) \end{pmatrix} = \begin{pmatrix} 4 - 3 & -2 + 2 \\ 6 - 6 & -3 + 4 \end{pmatrix} = I_2 \quad \checkmark$$

   - **Check $(A^T)^{-1}$:**
     $$A^T = \begin{pmatrix} 2 & 3 \\ 1 & 2 \end{pmatrix}$$
     $$A^T (A^T)^{-1} = \begin{pmatrix} 2 & 3 \\ 1 & 2 \end{pmatrix} \begin{pmatrix} 2 & -3 \\ -1 & 2 \end{pmatrix} = \begin{pmatrix} 4 - 3 & -6 + 6 \\ 2 - 2 & -3 + 4 \end{pmatrix} = I_2 \quad \checkmark$$

   - **Check $(A^2)^{-1}$:**
     $$A^2 = \begin{pmatrix} 2 & 1 \\ 3 & 2 \end{pmatrix} \begin{pmatrix} 2 & 1 \\ 3 & 2 \end{pmatrix} = \begin{pmatrix} 4 + 3 & 2 + 2 \\ 6 + 6 & 3 + 4 \end{pmatrix} = \begin{pmatrix} 7 & 4 \\ 12 & 7 \end{pmatrix}$$
     $$A^2 (A^2)^{-1} = \begin{pmatrix} 7 & 4 \\ 12 & 7 \end{pmatrix} \begin{pmatrix} 7 & -4 \\ -12 & 7 \end{pmatrix} = \begin{pmatrix} 49 - 48 & -28 + 28 \\ 84 - 84 & -48 + 49 \end{pmatrix} = I_2 \quad \checkmark$$

All results are thoroughly corroborated.
