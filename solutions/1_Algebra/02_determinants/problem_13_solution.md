# Solution to Exercise 13: Determinant by Elimination

## 1. Problem Statement

Compute the determinant of the matrix:
$$A = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 5 & 7 \\ 1 & 0 & 2 \end{pmatrix}$$
using Gaussian elimination to bring it into triangular form. 

Record explicitly the effect of each elementary row operation used on the value of the determinant.

---

## 2. Theoretical Background and Concepts

### Determinant Evaluation via Gaussian Elimination
Gaussian elimination transforms a matrix into upper triangular (echelon) form using elementary row operations:
1. **Type I (Row Swap $R_i \leftrightarrow R_j$):** Negates the determinant ($\det \to -\det$).
2. **Type II (Row Scaling $R_i \leftarrow c R_i$):** Multiplies the determinant by $c$ ($\det \to c \cdot \det$).
3. **Type III (Row Addition $R_i \leftarrow R_i + c R_j$):** Leaves the determinant **strictly invariant** ($\det \to \det$).

If a sequence of row operations transforms $A$ into an upper triangular matrix $U = (u_{ij})$ without row swaps or row scaling:
$$\det A = \det U = \prod_{i=1}^n u_{ii} = u_{11} \cdot u_{22} \cdots u_{nn}$$

---

## 3. Detailed Step-by-Step Solution

### Initial Matrix
$$A = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 5 & 7 \\ 1 & 0 & 2 \end{pmatrix}$$

---

### Step 1: Eliminate the $(2, 1)$ Entry
Perform the operation:
$$R_2 \leftarrow R_2 - 2R_1$$

- **Effect on Determinant:** Row addition; the determinant is **unchanged**.
- **Arithmetic:**
  $$R_2 = (2, 5, 7) - 2(1, 2, 3) = (2 - 2, \; 5 - 4, \; 7 - 6) = (0, 1, 1)$$

The matrix becomes:
$$A_1 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 1 & 1 \\ 1 & 0 & 2 \end{pmatrix}, \qquad \det A = \det A_1$$

---

### Step 2: Eliminate the $(3, 1)$ Entry
Perform the operation:
$$R_3 \leftarrow R_3 - R_1$$

- **Effect on Determinant:** Row addition; the determinant is **unchanged**.
- **Arithmetic:**
  $$R_3 = (1, 0, 2) - (1, 2, 3) = (1 - 1, \; 0 - 2, \; 2 - 3) = (0, -2, -1)$$

The matrix becomes:
$$A_2 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 1 & 1 \\ 0 & -2 & -1 \end{pmatrix}, \qquad \det A = \det A_2$$

---

### Step 3: Eliminate the $(3, 2)$ Entry
To clear the $-2$ beneath the pivot $1$ in column 2, add $2 \times R_2$ to $R_3$:
$$R_3 \leftarrow R_3 + 2R_2$$

- **Effect on Determinant:** Row addition; the determinant is **unchanged**.
- **Arithmetic:**
  $$R_3 = (0, -2, -1) + 2(0, 1, 1) = (0 + 0, \; -2 + 2, \; -1 + 2) = (0, 0, 1)$$

The matrix becomes:
$$A_3 = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 1 & 1 \\ 0 & 0 & 1 \end{pmatrix}, \qquad \det A = \det A_3$$

---

### Step 4: Evaluate the Determinant
Matrix $A_3$ is now in upper triangular form. Its determinant is the product of its main diagonal elements:
$$\det A_3 = 1 \cdot 1 \cdot 1 = 1$$

Because all operations performed were Type III operations ($R_i \leftarrow R_i + c R_j$), the determinant value was preserved at every stage:
$$\det A = \det A_1 = \det A_2 = \det A_3 = 1$$

---

## 4. Verification and Consistency Checks

1. **Direct Verification via Sarrus' Rule on $A$:**
   $$\begin{array}{ccc|cc}
   1 & 2 & 3 & 1 & 2 \\
   2 & 5 & 7 & 2 & 5 \\
   1 & 0 & 2 & 1 & 0
   \end{array}$$
   - **Positive diagonals:**
     $$P = (1 \cdot 5 \cdot 2) + (2 \cdot 7 \cdot 1) + (3 \cdot 2 \cdot 0) = 10 + 14 + 0 = 24$$
   - **Negative antidiagonals:**
     $$N = (1 \cdot 5 \cdot 3) + (0 \cdot 7 \cdot 1) + (2 \cdot 2 \cdot 2) = 15 + 0 + 8 = 23$$
   $$\det A = P - N = 24 - 23 = 1 \quad \checkmark$$

2. **LU Decomposition Check:**
   The row operations performed correspond to lower unitriangular elementary matrices:
   $$L = \begin{pmatrix} 1 & 0 & 0 \\ 2 & 1 & 0 \\ 1 & -2 & 1 \end{pmatrix}, \qquad U = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 1 & 1 \\ 0 & 0 & 1 \end{pmatrix}$$
   Computing $LU$:
   $$LU = \begin{pmatrix} 1 & 0 & 0 \\ 2 & 1 & 0 \\ 1 & -2 & 1 \end{pmatrix} \begin{pmatrix} 1 & 2 & 3 \\ 0 & 1 & 1 \\ 0 & 0 & 1 \end{pmatrix} = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 4+1 & 6+1 \\ 1 & 2-2 & 3-2+1 \end{pmatrix} = \begin{pmatrix} 1 & 2 & 3 \\ 2 & 5 & 7 \\ 1 & 0 & 2 \end{pmatrix} = A$$
   Since $\det L = 1$ and $\det U = 1$, $\det A = \det L \cdot \det U = 1 \cdot 1 = 1 \quad \checkmark$.

