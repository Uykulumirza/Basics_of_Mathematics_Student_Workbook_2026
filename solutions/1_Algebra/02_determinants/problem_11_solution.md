# Solution to Exercise 11: Shortening the Calculation with Row Operations

## 1. Problem Statement

Compute the determinant:
$$\det A = \det\begin{pmatrix} 1 & 2 & 3 \\ 1 & 3 & 4 \\ 1 & 4 & 6 \end{pmatrix}$$
by first performing elementary row operations to introduce as many zeros as possible. 

State explicitly which row operations preserve the value of the determinant throughout the process.

---

## 2. Theoretical Background and Concepts

### Invariance of Determinants Under Row Additions
An elementary row operation of type III ($R_i \leftarrow R_i + c R_j$ with $i \ne j$) adds a scalar multiple of row $j$ to row $i$.
- **Theorem:** For any matrix $M$ and any scalar $c \in \mathbb{R}$,
  $$\det(E_{i+cj} M) = \det(M)$$
  where $E_{i+cj}$ is the corresponding elementary shear matrix (which has ones along the main diagonal, $c$ in position $(i, j)$, and determinant $\det(E) = 1$).
- **Strategic Zero-Creation:** When multiple rows share identical or easily cancelable leading coefficients, subtracting the pivot row from subsequent rows creates leading zeros in a single step without introducing fractions or altering the determinant.

### Determinant of an Upper Triangular Matrix
Once a matrix is brought to upper triangular form (where all entries below the main diagonal are zero), its determinant is simply the product of its diagonal entries:
$$\det U = \prod_{i=1}^n u_{ii}$$

---

## 3. Detailed Step-by-Step Solution

### Initial Matrix
$$A = \begin{pmatrix} 1 & 2 & 3 \\ 1 & 3 & 4 \\ 1 & 4 & 6 \end{pmatrix}$$

Notice that the entire first column consists of ones: $\begin{pmatrix} 1 \\ 1 \\ 1 \end{pmatrix}$. We can use the first row as a pivot to clear all other entries in column 1.

---

### Step 1: Create Zeros in Column 1
1. **Subtract Row 1 from Row 2 ($R_2 \leftarrow R_2 - R_1$):**
   - **Determinant Effect:** Preserves the determinant ($\det A_1 = \det A$).
   - **Working:**
     $$R_2 - R_1 = (1 - 1, \; 3 - 2, \; 4 - 3) = (0, 1, 1)$$

2. **Subtract Row 1 from Row 3 ($R_3 \leftarrow R_3 - R_1$):**
   - **Determinant Effect:** Preserves the determinant ($\det A_2 = \det A_1$).
   - **Working:**
     $$R_3 - R_1 = (1 - 1, \; 4 - 2, \; 6 - 3) = (0, 2, 3)$$

Applying both operations yields:
$$A' = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 1 & 1 \\ 0 & 2 & 3 \end{pmatrix}, \qquad \det A = \det A'$$

---

### Step 2: Create a Zero in Column 2
To eliminate the $2$ in row 3, column 2, subtract $2 \times R_2$ from $R_3$:
$$R_3 \leftarrow R_3 - 2R_2$$

- **Determinant Effect:** Preserves the determinant ($\det A'' = \det A'$).
- **Working:**
  $$R_3 - 2R_2 = (0 - 2(0), \; 2 - 2(1), \; 3 - 2(1)) = (0, 0, 1)$$

Applying this operation yields the upper triangular matrix:
$$A'' = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 1 & 1 \\ 0 & 0 & 1 \end{pmatrix}, \qquad \det A = \det A''$$

---

### Step 3: Compute the Determinant
Matrix $A''$ is in upper triangular form. Its determinant is the product of the diagonal elements:
$$\det A'' = 1 \cdot 1 \cdot 1 = 1$$

Because all operations applied were of the type $R_i \leftarrow R_i + c R_j$, none changed the determinant:
$$\det A = \det A'' = 1$$

---

## 4. Verification and Consistency Checks

1. **Verification via Sarrus' Rule on Original Matrix $A$:**
   $$\begin{array}{ccc|cc}
   1 & 2 & 3 & 1 & 2 \\
   1 & 3 & 4 & 1 & 3 \\
   1 & 4 & 6 & 1 & 4
   \end{array}$$
   - **Positive diagonals:**
     $$P = (1 \cdot 3 \cdot 6) + (2 \cdot 4 \cdot 1) + (3 \cdot 1 \cdot 4) = 18 + 8 + 12 = 38$$
   - **Negative antidiagonals:**
     $$N = (1 \cdot 3 \cdot 3) + (4 \cdot 4 \cdot 1) + (6 \cdot 1 \cdot 2) = 9 + 16 + 12 = 37$$
   $$\det A = P - N = 38 - 37 = 1 \quad \checkmark$$

2. **Verification via Laplace Expansion along Column 1 of $A'$:**
   After the first step, matrix $A' = \begin{pmatrix} 1 & 2 & 3 \\ 0 & 1 & 1 \\ 0 & 2 & 3 \end{pmatrix}$.
   Expanding along column 1:
   $$\det A' = 1 \cdot \begin{vmatrix} 1 & 1 \\ 2 & 3 \end{vmatrix} - 0 + 0 = 1 \cdot (1 \cdot 3 - 1 \cdot 2) = 3 - 2 = 1 \quad \checkmark$$
   Both checks confirm that $\det A = 1$.
