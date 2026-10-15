# Solution to Exercise 3: Swapping Two Rows

## 1. Problem Statement

Given the matrix:
$$A = \begin{pmatrix} 1 & 2 & 0 \\ 0 & 3 & 1 \\ 2 & 1 & 1 \end{pmatrix}$$

1. Compute $\det A$.
2. Form the matrix $B$ by swapping the first and second rows of $A$.
3. Predict the value of $\det B$ using a fundamental property of determinants.
4. Verify the prediction by directly computing $\det B$.

---

## 2. Theoretical Background and Concepts

### Alternating Property of the Determinant (Row Swaps)
The determinant is an **alternating multilinear form** on the rows (and columns) of a matrix. 
- Swapping any two distinct rows (or columns) reverses the orientation of the row vectors in $\mathbb{R}^n$.
- Algebraically, interchanging two rows negates the sign of the determinant:
  $$\det(E_{ij} M) = -\det(M)$$
  where $E_{ij}$ is the elementary permutation matrix representing the row operation $R_i \leftrightarrow R_j$.

Therefore, if matrix $B$ is obtained from matrix $A$ by performing a single row swap, then:
$$\det B = -\det A$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $\det A$
We compute $\det A$ using Laplace expansion along the first row (exploiting $a_{13} = 0$):
$$\det A = 1 \cdot C_{11} + 2 \cdot C_{12} + 0 \cdot C_{13}$$

Compute the required $2 \times 2$ minors:
- Minor for entry $(1, 1)$:
  $$C_{11} = (-1)^{1+1} \begin{vmatrix} 3 & 1 \\ 1 & 1 \end{vmatrix} = +(3 \cdot 1 - 1 \cdot 1) = 3 - 1 = 2$$

- Minor for entry $(1, 2)$:
  $$C_{12} = (-1)^{1+2} \begin{vmatrix} 0 & 1 \\ 2 & 1 \end{vmatrix} = -(0 \cdot 1 - 1 \cdot 2) = -(-2) = 2$$

Substitute into the expansion:
$$\det A = 1(2) + 2(2) = 2 + 4 = 6$$

---

### Step 2: Form Matrix $B$
Interchange the first and second rows of $A$ ($R_1 \leftrightarrow R_2$):
$$B = \begin{pmatrix} 0 & 3 & 1 \\ 1 & 2 & 0 \\ 2 & 1 & 1 \end{pmatrix}$$

---

### Step 3: Theoretical Prediction for $\det B$
Because $B$ is obtained from $A$ by exactly one elementary row swap ($R_1 \leftrightarrow R_2$), the alternating property dictates:
$$\det B = -\det A = -6$$

---

### Step 4: Verification by Direct Computation of $\det B$
We compute $\det B$ directly using Laplace expansion along its first row:
$$\det B = 0 \cdot C_{11} + 3 \cdot C_{12} + 1 \cdot C_{13}$$

- For entry $(1, 2) = 3$:
  $$C_{12} = (-1)^{1+2} \begin{vmatrix} 1 & 0 \\ 2 & 1 \end{vmatrix} = -(1 \cdot 1 - 0 \cdot 2) = -1$$

- For entry $(1, 3) = 1$:
  $$C_{13} = (-1)^{1+3} \begin{vmatrix} 1 & 2 \\ 2 & 1 \end{vmatrix} = +(1 \cdot 1 - 2 \cdot 2) = 1 - 4 = -3$$

Combine the terms:
$$\det B = 0 - 3(1) + 1(-3) = -3 - 3 = -6$$

The direct calculation strictly confirms the theoretical prediction $\det B = -6$.

---

## 4. Verification and Consistency Checks

1. **Independent Check via Sarrus' Rule for $A$:**
   $$\det A = (1 \cdot 3 \cdot 1 + 2 \cdot 1 \cdot 2 + 0 \cdot 0 \cdot 1) - (2 \cdot 3 \cdot 0 + 1 \cdot 1 \cdot 1 + 1 \cdot 0 \cdot 2)$$
   $$\det A = (3 + 4 + 0) - (0 + 1 + 0) = 7 - 1 = 6 \quad \checkmark$$

2. **Independent Check via Sarrus' Rule for $B$:**
   $$\det B = (0 \cdot 2 \cdot 1 + 3 \cdot 0 \cdot 2 + 1 \cdot 1 \cdot 1) - (2 \cdot 2 \cdot 1 + 1 \cdot 0 \cdot 0 + 1 \cdot 1 \cdot 3)$$
   $$\det B = (0 + 0 + 1) - (4 + 0 + 3) = 1 - 7 = -6 \quad \checkmark$$

3. **Elementary Matrix Formulation:**
   The swap corresponds to left-multiplication by the permutation matrix $P$:
   $$P = \begin{pmatrix} 0 & 1 & 0 \\ 1 & 0 & 0 \\ 0 & 0 & 1 \end{pmatrix}$$
   Here $\det P = -1$. By the product theorem of determinants:
   $$\det B = \det(PA) = \det(P) \cdot \det(A) = (-1) \cdot 6 = -6 \quad \checkmark$$
