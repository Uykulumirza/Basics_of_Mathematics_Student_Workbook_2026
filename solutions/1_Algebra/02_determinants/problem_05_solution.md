# Solution to Exercise 5: Row Operations

## 1. Problem Statement

For the matrix:
$$A = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 1 & 0 \\ -1 & 4 & 2 \end{pmatrix}$$

Find $\det A$ by simplifying the matrix into upper triangular form using elementary row operations. At each step, explicitly indicate whether and how the value of the determinant changes.

---

## 2. Theoretical Background and Concepts

### Effects of Elementary Row Operations on the Determinant
1. **Row addition ($R_i \leftarrow R_i + c R_j$, $i \ne j$):**
   Adding a scalar multiple of one row to another **leaves the determinant unchanged**:
   $$\det(A_{\text{new}}) = \det(A_{\text{old}})$$
2. **Row scaling ($R_i \leftarrow c R_i$, $c \ne 0$):**
   Multiplying a single row by a scalar factor $c$ multiplies the determinant by $c$:
   $$\det(A_{\text{new}}) = c \cdot \det(A_{\text{old}})$$
3. **Row interchange ($R_i \leftrightarrow R_j$):**
   Swapping two rows negates the determinant:
   $$\det(A_{\text{new}}) = -\det(A_{\text{old}})$$

By applying row addition operations systematically, we can reduce any square matrix to an upper triangular matrix $U$ without altering the determinant, reducing the computation to the product of diagonal pivots.

---

## 3. Detailed Step-by-Step Solution

### Initial Matrix
$$A = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 1 & 0 \\ -1 & 4 & 2 \end{pmatrix}$$

---

### Step 1: Eliminate the $(2, 1)$ Entry
Perform the row operation:
$$R_2 \leftarrow R_2 - 2R_1$$

- **Effect on Determinant:** Row addition operation; the determinant is **unchanged**.
- **Calculation:**
  $$R_2 = (2, 1, 0) - 2(1, 2, 3) = (2 - 2, \; 1 - 4, \; 0 - 6) = (0, -3, -6)$$

The matrix becomes:
$$A_1 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & -3 & -6 \\ -1 & 4 & 2 \end{pmatrix}, \qquad \det A = \det A_1$$

---

### Step 2: Eliminate the $(3, 1)$ Entry
Perform the row operation:
$$R_3 \leftarrow R_3 + R_1$$

- **Effect on Determinant:** Row addition operation; the determinant is **unchanged**.
- **Calculation:**
  $$R_3 = (-1, 4, 2) + (1, 2, 3) = (-1 + 1, \; 4 + 2, \; 2 + 3) = (0, 6, 5)$$

The matrix becomes:
$$A_2 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & -3 & -6 \\ 0 & 6 & 5 \end{pmatrix}, \qquad \det A = \det A_2$$

---

### Step 3: Eliminate the $(3, 2)$ Entry
To clear the entry in row 3 beneath the pivot $-3$ in row 2, add $2 \times R_2$ to $R_3$:
$$R_3 \leftarrow R_3 + 2R_2$$

- **Effect on Determinant:** Row addition operation; the determinant is **unchanged**.
- **Calculation:**
  $$R_3 = (0, 6, 5) + 2(0, -3, -6) = (0 + 0, \; 6 - 6, \; 5 - 12) = (0, 0, -7)$$

The matrix becomes:
$$A_3 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & -3 & -6 \\ 0 & 0 & -7 \end{pmatrix}, \qquad \det A = \det A_3$$

---

### Step 4: Evaluate the Determinant of the Triangular Matrix
Matrix $A_3$ is in upper triangular form. Its determinant is the product of its main diagonal elements:
$$\det A_3 = 1 \cdot (-3) \cdot (-7) = 21$$

Since no row swaps or row scaling operations were used, each transition preserved the determinant value:
$$\det A = \det A_1 = \det A_2 = \det A_3 = 21$$

---

## 4. Verification and Consistency Checks

We verify the result using **Sarrus' Rule** directly on the original matrix $A$:
$$\begin{array}{ccc|cc}
1 & 2 & 3 & 1 & 2 \\
2 & 1 & 0 & 2 & 1 \\
-1 & 4 & 2 & -1 & 4
\end{array}$$

- **Positive Diagonals:**
  $$P = (1 \cdot 1 \cdot 2) + (2 \cdot 0 \cdot (-1)) + (3 \cdot 2 \cdot 4) = 2 + 0 + 24 = 26$$

- **Negative Antidiagonals:**
  $$N = ((-1) \cdot 1 \cdot 3) + (4 \cdot 0 \cdot 1) + (2 \cdot 2 \cdot 2) = -3 + 0 + 8 = 5$$

Subtracting the two sums:
$$\det A = P - N = 26 - 5 = 21 \quad \checkmark$$

The independent Sarrus calculation confirms $\det A = 21$.
