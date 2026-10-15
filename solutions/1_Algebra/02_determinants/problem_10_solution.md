# Solution to Exercise 10: Detecting Dependence

## 1. Problem Statement

Without carrying out a full determinant expansion or Sarrus calculation, explain why:
$$\det A = \det\begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \\ 0 & 1 & 5 \end{pmatrix} = 0$$

1. Identify a specific linear dependence relation between the rows of matrix $A$.
2. Connect this linear dependence directly to the non-invertibility of the matrix.

---

## 2. Theoretical Background and Concepts

### Linear Dependence of Rows and Determinants
A set of vectors $\{r_1, r_2, \dots, r_n\}$ is **linearly dependent** if there exist scalars $c_1, c_2, \dots, c_n$, not all zero, such that:
$$c_1 r_1 + c_2 r_2 + \cdots + c_n r_n = 0$$

Fundamental properties connecting linear dependence and determinants:
1. **Multilinearity and Alternating Property:** If one row of a matrix is a scalar multiple of another row (or a linear combination of other rows), the determinant of the matrix is identically zero.
2. **Row of Zeros:** Adding a multiple of one row to another preserves the determinant. If row $i$ is proportional to row $j$ ($R_i = k R_j$), the elementary operation $R_i \leftarrow R_i - k R_j$ transforms row $i$ into a row consisting entirely of zeros. Expanding the determinant along a zero row yields identically zero.
3. **Invertibility Criterion:** A matrix $A \in M_n(\mathbb{R})$ is invertible if and only if its rows form a basis of $\mathbb{R}^n$ (i.e., they are linearly independent, so $\operatorname{rank}(A) = n$). If the rows are linearly dependent, the matrix has deficient rank ($\operatorname{rank}(A) < n$) and is non-invertible (singular).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify the Linear Dependence Between the Rows
Examine the rows of matrix $A$:
- Row 1: $R_1 = (1, 2, 3)$
- Row 2: $R_2 = (2, 4, 6)$
- Row 3: $R_3 = (0, 1, 5)$

Compare row 2 with row 1:
$$R_2 = (2, 4, 6) = 2 \cdot (1, 2, 3) = 2 R_1$$

We can write this as a non-trivial linear combination equaling the zero vector:
$$-2 R_1 + 1 R_2 + 0 R_3 = (0, 0, 0)$$

Since the coefficients $(-2, 1, 0)$ are not all zero, the rows of $A$ are **linearly dependent**.

---

### Step 2: Show Why This Forces $\det A = 0$
Apply the elementary row operation $R_2 \leftarrow R_2 - 2R_1$:
$$A \xrightarrow{R_2 \leftarrow R_2 - 2R_1} \begin{pmatrix} 1 & 2 & 3 \\ 0 & 0 & 0 \\ 0 & 1 & 5 \end{pmatrix} = A'$$

- Because row addition does not change the determinant: $\det A = \det A'$.
- Now expand $\det A'$ along its second row, which consists entirely of zeros:
  $$\det A' = 0 \cdot C_{21} + 0 \cdot C_{22} + 0 \cdot C_{23} = 0$$
- Therefore:
  $$\det A = 0$$

---

### Step 3: Connection to Non-Invertibility
Because the rows are linearly dependent:
1. **Rank Deficiency:** The span of the rows has dimension at most $2$, so:
   $$\operatorname{rank}(A) \le 2 < 3$$
2. **Non-trivial Kernel (Null Space):** By the Rank-Nullity Theorem:
   $$\dim(\ker A) = 3 - \operatorname{rank}(A) \ge 3 - 2 = 1$$
   There exist non-zero vectors $x \ne 0$ such that $Ax = 0$. For instance, notice that the columns also exhibit linear dependence ($C_2 = 2C_1$), meaning:
   $$\begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \\ 0 & 1 & 5 \end{pmatrix} \begin{pmatrix} -2 \\ 1 \\ 0 \end{pmatrix} = \begin{pmatrix} -2 + 2 + 0 \\ -4 + 4 + 0 \\ 0 + 1 + 0 \end{pmatrix} \ne 0$$
   Wait, to find an explicit null vector, we solve $Ax = 0$:
   From row 1 and row 3: $x_1 + 2x_2 + 3x_3 = 0$ and $x_2 + 5x_3 = 0 \implies x_2 = -5x_3 \implies x_1 = -2(-5x_3) - 3x_3 = 7x_3$.
   Taking $x_3 = 1$ gives $x = (7, -5, 1)^T$:
   $$A \begin{pmatrix} 7 \\ -5 \\ 1 \end{pmatrix} = \begin{pmatrix} 7 - 10 + 3 \\ 14 - 20 + 6 \\ 0 - 5 + 5 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix}$$
3. **Loss of Injectivity and Invertibility:** Because $x = (7, -5, 1)^T \ne 0$ maps to the zero vector, the linear transformation is not injective (one-to-one). No function can invert a transformation that collapses non-zero vectors to zero. Hence, $A$ cannot be invertible.

---

## 4. Verification and Consistency Checks

1. **Direct Calculation via Sarrus' Rule (Independent Verification):**
   $$\begin{array}{ccc|cc}
   1 & 2 & 3 & 1 & 2 \\
   2 & 4 & 6 & 2 & 4 \\
   0 & 1 & 5 & 0 & 1
   \end{array}$$
   - Positive diagonals:
     $$P = (1 \cdot 4 \cdot 5) + (2 \cdot 6 \cdot 0) + (3 \cdot 2 \cdot 1) = 20 + 0 + 6 = 26$$
   - Negative antidiagonals:
     $$N = (0 \cdot 4 \cdot 3) + (1 \cdot 6 \cdot 1) + (5 \cdot 2 \cdot 2) = 0 + 6 + 20 = 26$$
   $$\det A = P - N = 26 - 26 = 0 \quad \checkmark$$

2. **Rank Check via Gaussian Echelon Form:**
   $$\begin{pmatrix} 1 & 2 & 3 \\ 2 & 4 & 6 \\ 0 & 1 & 5 \end{pmatrix} \xrightarrow{R_2 \leftarrow R_2 - 2R_1} \begin{pmatrix} 1 & 2 & 3 \\ 0 & 0 & 0 \\ 0 & 1 & 5 \end{pmatrix} \xrightarrow{R_2 \leftrightarrow R_3} \begin{pmatrix} 1 & 2 & 3 \\ 0 & 1 & 5 \\ 0 & 0 & 0 \end{pmatrix}$$
   The echelon form has only 2 non-zero pivot rows. Therefore, $\operatorname{rank}(A) = 2 < 3$, confirming that the determinant must be $0$ and the matrix is singular.

