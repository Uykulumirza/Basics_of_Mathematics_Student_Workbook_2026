# Solution to Exercise 3: When Does the Inverse Not Exist?

## 1. Problem Statement

Given the matrix:
$$A = \begin{pmatrix} 2 & 4 \\ 1 & 2 \end{pmatrix}$$

Explain in two distinct ways why the inverse matrix $A^{-1}$ does not exist:
1. Using the determinant of $A$.
2. Using the linear dependence between the rows of $A$.

---

## 2. Theoretical Background and Concepts

### Criteria for Matrix Invertibility
For any square matrix $A \in M_n(\mathbb{R})$, the following statements are logically equivalent:
1. $A$ is invertible ($A^{-1}$ exists).
2. $\det A \ne 0$ (the matrix is non-singular).
3. The rows (and columns) of $A$ are linearly independent.
4. $\operatorname{rank}(A) = n$ (full rank).
5. The kernel (null space) is trivial: $\ker(A) = \{0\}$.
6. The linear mapping $f_A(x) = Ax$ is bijective (one-to-one and onto $\mathbb{R}^n$).

### Failure Modes of Invertibility
- **Determinant Vanishing:** The determinant measures the oriented volume scaling factor of the linear mapping. If $\det A = 0$, the transformation collapses an $n$-dimensional volume to a lower-dimensional subspace (area collapsing to a line or point in $\mathbb{R}^2$). Since division by zero is undefined, the inverse formula $A^{-1} = \frac{1}{\det A} \operatorname{adj}(A)$ cannot be computed.
- **Row Linear Dependence:** If one row is a scalar multiple of another, the rows do not span $\mathbb{R}^n$. The rank drops strictly below $n$, creating a non-trivial null space. Vectors in the null space map to zero, destroying injectivity (different inputs produce the same output), making inversion impossible.

---

## 3. Detailed Step-by-Step Solution

### Method 1: Explanation via the Determinant

Compute the determinant of matrix $A$:
$$\det A = \det \begin{pmatrix} 2 & 4 \\ 1 & 2 \end{pmatrix} = (2)(2) - (4)(1) = 4 - 4 = 0$$

**Mathematical Consequence:**
- If $A^{-1}$ existed, then by the multiplicativity of determinants:
  $$\det(A A^{-1}) = \det(I_2) \implies \det(A) \cdot \det(A^{-1}) = 1$$
- Substituting $\det A = 0$ yields:
  $$0 \cdot \det(A^{-1}) = 1 \implies 0 = 1$$
  which is a blatant mathematical contradiction.
- Additionally, the adjugate formula would require dividing by zero:
  $$A^{-1} = \frac{1}{\det A} \begin{pmatrix} 2 & -4 \\ -1 & 2 \end{pmatrix} = \frac{1}{0} \begin{pmatrix} 2 & -4 \\ -1 & 2 \end{pmatrix} \quad (\text{undefined})$$
Therefore, because $\det A = 0$, $A$ is singular and no inverse exists.

---

### Method 2: Explanation via Linear Dependence Between Rows

Examine the two row vectors of matrix $A$:
$$R_1 = (2, 4), \qquad R_2 = (1, 2)$$

**Linear Dependence Relation:**
Observe that row 1 is exactly twice row 2:
$$R_1 = 2 R_2 \iff 1 R_1 - 2 R_2 = (0, 0)$$

Because there exist scalars $(c_1, c_2) = (1, -2) \ne (0, 0)$ such that $c_1 R_1 + c_2 R_2 = 0$, the rows are **linearly dependent**.

**Geometric and Structural Consequence:**
1. **Rank Deficiency:** The row space $\operatorname{row}(A) = \operatorname{span}\{(2, 4), (1, 2)\} = \operatorname{span}\{(1, 2)\}$ is a $1$-dimensional line in $\mathbb{R}^2$, so:
   $$\operatorname{rank}(A) = 1 < 2$$
2. **Failure of Bijectivity (Loss of Injectivity):**
   Consider the homogeneous equation $Ax = 0$:
   $$\begin{pmatrix} 2 & 4 \\ 1 & 2 \end{pmatrix} \begin{pmatrix} x_1 \\ x_2 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \end{pmatrix} \iff x_1 + 2x_2 = 0$$
   Choosing $x_2 = 1$ gives $x_1 = -2$, yielding the non-zero vector:
   $$v = \begin{pmatrix} -2 \\ 1 \end{pmatrix} \ne \begin{pmatrix} 0 \\ 0 \end{pmatrix}$$
   Notice:
   $$A v = \begin{pmatrix} 2 & 4 \\ 1 & 2 \end{pmatrix} \begin{pmatrix} -2 \\ 1 \end{pmatrix} = \begin{pmatrix} -4 + 4 \\ -2 + 2 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \end{pmatrix} = A \begin{pmatrix} 0 \\ 0 \end{pmatrix}$$
   Because two different vectors map to the same image ($A v = A 0 = 0$), the transformation is not one-to-one (not injective).
3. **Impossibility of Inversion:**
   If an inverse $A^{-1}$ existed, multiplying $A v = 0$ by $A^{-1}$ would force:
   $$A^{-1}(Av) = A^{-1}(0) \implies (A^{-1}A)v = 0 \implies I_2 v = 0 \implies v = 0$$
   This contradicts $v = \begin{pmatrix} -2 \\ 1 \end{pmatrix} \ne 0$.

Therefore, linear dependence between the rows fundamentally prevents the existence of an inverse.

---

## 4. Verification and Consistency Checks

1. **Gaussian Elimination Check:**
   Form the echelon form by performing $R_2 \leftarrow R_2 - \frac{1}{2}R_1$:
   $$\begin{pmatrix} 2 & 4 \\ 1 & 2 \end{pmatrix} \xrightarrow{R_2 \leftarrow R_2 - \frac{1}{2}R_1} \begin{pmatrix} 2 & 4 \\ 0 & 0 \end{pmatrix}$$
   The appearance of an entire row of zeros proves that the row rank is $1$, confirming singular status.

2. **Column Dependence Consistency:**
   Note that the columns $C_1 = \begin{pmatrix} 2 \\ 1 \end{pmatrix}$ and $C_2 = \begin{pmatrix} 4 \\ 2 \end{pmatrix}$ satisfy $C_2 = 2C_1$.
   The image of the transformation is the line $y = \frac{1}{2}x$. Any vector outside this line (e.g., $b = \begin{pmatrix} 1 \\ 0 \end{pmatrix}$) has no solution to $Ax = b$, proving the mapping is also not surjective.
