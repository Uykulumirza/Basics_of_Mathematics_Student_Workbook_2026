# Solution to Exercise 4: Triangular Matrix

## 1. Problem Statement

Without expanding the determinant using brute-force permutations, compute:
$$\det T = \det\begin{pmatrix} 2 & 4 & 1 \\ 0 & -3 & 5 \\ 0 & 0 & 7 \end{pmatrix}$$

1. State the general rule for the determinant of an arbitrary triangular matrix.
2. Explain why this rule holds using the given example.

---

## 2. Theoretical Background and Concepts

### Triangular Matrices
A square matrix $T = (t_{ij}) \in M_n(\mathbb{R})$ is:
- **Upper triangular** if all entries strictly below the main diagonal are zero ($t_{ij} = 0$ for $i > j$).
- **Lower triangular** if all entries strictly above the main diagonal are zero ($t_{ij} = 0$ for $i < j$).
- **Diagonal** if all off-diagonal entries are zero ($t_{ij} = 0$ for $i \ne j$).

### General Determinant Theorem for Triangular Matrices
The determinant of any triangular matrix (upper triangular, lower triangular, or diagonal) is strictly equal to the product of its main diagonal entries:
$$\det T = \prod_{i=1}^n t_{ii} = t_{11} \cdot t_{22} \cdots t_{nn}$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identification of Matrix Type
Given:
$$T = \begin{pmatrix} 2 & 4 & 1 \\ 0 & -3 & 5 \\ 0 & 0 & 7 \end{pmatrix}$$

All entries in positions $(2, 1)$, $(3, 1)$, and $(3, 2)$ are zero. Because every entry strictly below the main diagonal is zero, $T$ is an **upper triangular matrix**.

### Step 2: Application of the Diagonal Product Rule
The entries along the main diagonal are:
- $t_{11} = 2$
- $t_{22} = -3$
- $t_{33} = 7$

Applying the theorem:
$$\det T = t_{11} \cdot t_{22} \cdot t_{33} = 2 \cdot (-3) \cdot 7 = -6 \cdot 7 = -42$$

### Step 3: Explanation of Why the Rule Holds
The diagonal product rule follows naturally from successive Laplace expansions:
1. **Expand along the first column of $T$:**
   The first column contains only one non-zero entry, $t_{11} = 2$, at the top:
   $$\det T = 2 \cdot \det\begin{pmatrix} -3 & 5 \\ 0 & 7 \end{pmatrix} - 0 \cdot C_{21} + 0 \cdot C_{31} = 2 \cdot \begin{vmatrix} -3 & 5 \\ 0 & 7 \end{vmatrix}$$

2. **Evaluate the remaining $2 \times 2$ determinant:**
   The resulting minor is itself upper triangular. Expanding along its first column (or directly using $ad - bc$):
   $$\begin{vmatrix} -3 & 5 \\ 0 & 7 \end{vmatrix} = (-3)(7) - (5)(0) = (-3)(7) = -21$$

3. **Combine factors:**
   $$\det T = 2 \cdot [(-3) \cdot 7] = -42$$

Every off-diagonal term in the permutation definition of the determinant contains at least one zero factor from below the diagonal. Thus, the only non-vanishing permutation is the identity permutation, which corresponds exclusively to the product of the diagonal elements.

---

## 4. Verification and Consistency Checks

1. **Verification via Sarrus' Rule:**
   Compute all 6 diagonal products explicitly:
   - Positive diagonals:
     $$(2)(-3)(7) + (4)(5)(0) + (1)(0)(0) = -42 + 0 + 0 = -42$$
   - Negative antidiagonals:
     $$(0)(-3)(1) + (0)(5)(2) + (7)(0)(4) = 0 + 0 + 0 = 0$$
   $$\det T = (-42) - (0) = -42 \quad \checkmark$$

2. **Eigenvalue Consistency Check:**
   For any triangular matrix, its eigenvalues are precisely the elements along its main diagonal:
   $$\lambda_1 = 2, \quad \lambda_2 = -3, \quad \lambda_3 = 7$$
   Since the determinant of any matrix equals the product of its eigenvalues:
   $$\det T = \lambda_1 \cdot \lambda_2 \cdot \lambda_3 = 2 \cdot (-3) \cdot 7 = -42 \quad \checkmark$$
