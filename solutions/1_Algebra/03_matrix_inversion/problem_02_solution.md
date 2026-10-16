# Solution to Exercise 2: Formula for a 2×2 Matrix

## 1. Problem Statement

Given the matrix:
$$A = \begin{pmatrix} 3 & 2 \\ 5 & 4 \end{pmatrix}$$

1. Find the inverse matrix $A^{-1}$ using the explicit formula for the inverse of a $2 \times 2$ matrix.
2. Check the result by computing the matrix product of $A$ and the calculated inverse.

---

## 2. Theoretical Background and Concepts

### Canonical Formula for the Inverse of a $2 \times 2$ Matrix
For an arbitrary $2 \times 2$ matrix:
$$M = \begin{pmatrix} a & b \\ c & d \end{pmatrix}$$

1. **Invertibility Criterion:** $M$ is invertible if and only if its determinant is non-zero:
   $$\det M = ad - bc \ne 0$$
2. **Adjugate Representation:** The classical adjugate matrix $\operatorname{adj}(M)$ is formed by the transposed matrix of cofactors:
   $$\operatorname{adj}(M) = \begin{pmatrix} d & -b \\ -c & a \end{pmatrix}$$
3. **Explicit Inverse Formula:**
   $$M^{-1} = \frac{1}{\det M} \operatorname{adj}(M) = \frac{1}{ad - bc} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix}$$

The operation involves:
- Swapping the diagonal entries ($a \leftrightarrow d$),
- Negating the off-diagonal entries ($b \to -b$, $c \to -c$),
- Dividing every entry by the scalar determinant $\det M$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute the Determinant of $A$
Identify the matrix entries:
$$a = 3, \quad b = 2, \quad c = 5, \quad d = 4$$

Calculate the determinant:
$$\det A = ad - bc = (3)(4) - (2)(5) = 12 - 10 = 2$$

Since $\det A = 2 \ne 0$, the matrix $A$ is non-singular and its inverse $A^{-1}$ exists.

---

### Step 2: Construct the Adjugate Matrix
Form the matrix by swapping the main diagonal elements and reversing the signs of the off-diagonal elements:
$$\operatorname{adj}(A) = \begin{pmatrix} d & -b \\ -c & a \end{pmatrix} = \begin{pmatrix} 4 & -2 \\ -5 & 3 \end{pmatrix}$$

---

### Step 3: Compute $A^{-1}$
Multiply the adjugate matrix by the reciprocal of the determinant:
$$A^{-1} = \frac{1}{\det A} \operatorname{adj}(A) = \frac{1}{2} \begin{pmatrix} 4 & -2 \\ -5 & 3 \end{pmatrix}$$

Distributing the scalar $\frac{1}{2}$ into the matrix entries gives:
$$A^{-1} = \begin{pmatrix} \frac{4}{2} & \frac{-2}{2} \\ \frac{-5}{2} & \frac{3}{2} \end{pmatrix} = \begin{pmatrix} 2 & -1 \\ -\frac{5}{2} & \frac{3}{2} \end{pmatrix}$$

---

### Step 4: Verification via Multiplication
Compute the product $A A^{-1}$:
$$A A^{-1} = \begin{pmatrix} 3 & 2 \\ 5 & 4 \end{pmatrix} \begin{pmatrix} 2 & -1 \\ -\frac{5}{2} & \frac{3}{2} \end{pmatrix}$$

Evaluate each element:
- Position $(1, 1)$: $3(2) + 2\left(-\frac{5}{2}\right) = 6 - 5 = 1$
- Position $(1, 2)$: $3(-1) + 2\left(\frac{3}{2}\right) = -3 + 3 = 0$
- Position $(2, 1)$: $5(2) + 4\left(-\frac{5}{2}\right) = 10 - 10 = 0$
- Position $(2, 2)$: $5(-1) + 4\left(\frac{3}{2}\right) = -5 + 6 = 1$

Thus:
$$A A^{-1} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I_2$$

---

## 4. Verification and Consistency Checks

1. **Reverse Product Verification ($A^{-1} A = I_2$):**
   $$A^{-1} A = \begin{pmatrix} 2 & -1 \\ -\frac{5}{2} & \frac{3}{2} \end{pmatrix} \begin{pmatrix} 3 & 2 \\ 5 & 4 \end{pmatrix} = \begin{pmatrix} 2(3) + (-1)(5) & 2(2) + (-1)(4) \\ -\frac{5}{2}(3) + \frac{3}{2}(5) & -\frac{5}{2}(2) + \frac{3}{2}(4) \end{pmatrix} = \begin{pmatrix} 6 - 5 & 4 - 4 \\ -\frac{15}{2} + \frac{15}{2} & -5 + 6 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I_2$$
   Both left and right multiplication hold.

2. **Determinant Inverse Property Check:**
   $$\det(A^{-1}) = (2)\left(\frac{3}{2}\right) - (-1)\left(-\frac{5}{2}\right) = 3 - \frac{5}{2} = \frac{1}{2}$$
   Notice that:
   $$\det(A^{-1}) = \frac{1}{\det A} = \frac{1}{2}$$
   This satisfies the theorem $\det(A^{-1}) = (\det A)^{-1}$.
