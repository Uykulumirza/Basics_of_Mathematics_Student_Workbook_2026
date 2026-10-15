# Solution to Exercise 2: Determinant of a 3×3 Matrix

## 1. Problem Statement

For the matrix:
$$A = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 3 & 4 \\ 2 & 1 & 5 \end{pmatrix}$$

1. Compute $\det A$ using Sarrus' rule.
2. Perform a verification check of the result using an alternative determinant property (e.g., Laplace cofactor expansion).

---

## 2. Theoretical Background and Concepts

### Sarrus' Rule for $3 \times 3$ Determinants
Sarrus' rule is a mnemonic for evaluating the determinant of a $3 \times 3$ matrix. By appending the first two columns of the matrix to the right:
$$\begin{matrix}
a_{11} & a_{12} & a_{13} & a_{11} & a_{12} \\
a_{21} & a_{22} & a_{23} & a_{21} & a_{22} \\
a_{31} & a_{32} & a_{33} & a_{31} & a_{32}
\end{matrix}$$

The determinant is calculated by taking the sum of the products along the three main diagonal directions (top-left to bottom-right) and subtracting the sum of the products along the three antidiagonal directions (bottom-left to top-right):
$$\det A = (a_{11} a_{22} a_{33} + a_{12} a_{23} a_{31} + a_{13} a_{21} a_{32}) - (a_{31} a_{22} a_{13} + a_{32} a_{23} a_{11} + a_{33} a_{21} a_{12})$$

### Laplace Cofactor Expansion
The determinant of an $n \times n$ matrix can also be computed by expanding along any row or column. Expanding along the $j$-th column gives:
$$\det A = \sum_{i=1}^n (-1)^{i+j} a_{ij} \det(M_{ij})$$
where $M_{ij}$ is the $(n-1) \times (n-1)$ submatrix obtained by deleting row $i$ and column $j$. Selecting a column with zero entries simplifies the computation significantly.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $\det A$ via Sarrus' Rule
Write out matrix $A$ and append the first two columns:
$$\begin{array}{ccc|cc}
1 & 2 & -1 & 1 & 2 \\
0 & 3 & 4 & 0 & 3 \\
2 & 1 & 5 & 2 & 1
\end{array}$$

#### Positive Diagonal Products (from top-left to bottom-right):
1. First diagonal: $1 \cdot 3 \cdot 5 = 15$
2. Second diagonal: $2 \cdot 4 \cdot 2 = 16$
3. Third diagonal: $(-1) \cdot 0 \cdot 1 = 0$

Sum of positive products:
$$P = 15 + 16 + 0 = 31$$

#### Negative Antidiagonal Products (from bottom-left to top-right):
1. First antidiagonal: $2 \cdot 3 \cdot (-1) = -6$
2. Second antidiagonal: $1 \cdot 4 \cdot 1 = 4$
3. Third antidiagonal: $5 \cdot 0 \cdot 2 = 0$

Sum of negative products:
$$N = (-6) + 4 + 0 = -2$$

#### Combine the Products:
$$\det A = P - N = 31 - (-2) = 31 + 2 = 33$$

---

## 4. Verification and Consistency Checks

We verify the result using **Laplace expansion along the first column**, which is computationally efficient due to the zero entry $a_{21} = 0$:

$$\det A = a_{11} C_{11} + a_{21} C_{21} + a_{31} C_{31}$$

where the cofactors are:
- For $a_{11} = 1$:
  $$C_{11} = (-1)^{1+1} \begin{vmatrix} 3 & 4 \\ 1 & 5 \end{vmatrix} = +1 \cdot (3 \cdot 5 - 4 \cdot 1) = 15 - 4 = 11$$

- For $a_{21} = 0$:
  $$a_{21} C_{21} = 0$$

- For $a_{31} = 2$:
  $$C_{31} = (-1)^{3+1} \begin{vmatrix} 2 & -1 \\ 3 & 4 \end{vmatrix} = +1 \cdot (2 \cdot 4 - (-1) \cdot 3) = 8 - (-3) = 11$$

Summing the terms:
$$\det A = 1 \cdot (11) + 0 + 2 \cdot (11) = 11 + 22 = 33$$

Both methods yield precisely $33$, confirming the calculation.
