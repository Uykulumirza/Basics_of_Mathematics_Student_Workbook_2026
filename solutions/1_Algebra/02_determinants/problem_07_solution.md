# Solution to Exercise 7: Using Properties Instead of Recomputing

## 1. Problem Statement

Suppose that for a $3 \times 3$ matrix $A$, the determinant is:
$$\det A = -4$$

Compute the following determinants without knowing or reconstructing the individual entries of $A$:
1. $\det(2A)$
2. $\det(A^T)$
3. $\det(A^2)$
4. $\det(-A)$

Justify each answer by stating and explaining the corresponding property of determinants.

---

## 2. Theoretical Background and Concepts

Let $M \in M_n(\mathbb{R})$ be an $n \times n$ matrix. The determinant satisfies the following algebraic properties:

### 1. Homogeneity (Scalar Multiplication)
Because the determinant is an $n$-linear function of its rows, multiplying the entire matrix by a scalar $c \in \mathbb{R}$ scales each of its $n$ individual rows by $c$:
$$\det(c M) = c^n \det(M)$$
For an $n \times n$ matrix, each row contributes a factor of $c$, resulting in an overall factor of $c^n$.

### 2. Transposition Invariance
Transposing a matrix swaps its rows and columns without changing the permutation structure of the determinant:
$$\det(M^T) = \det(M)$$

### 3. Multiplicativity
The determinant of a product of square matrices equals the product of their individual determinants:
$$\det(MN) = \det(M) \det(N)$$
Consequently, for any positive integer power $k \ge 1$:
$$\det(M^k) = (\det M)^k$$

### 4. Negation (Odd vs. Even Dimension)
Negating a matrix corresponds to scalar multiplication by $c = -1$:
$$\det(-M) = \det((-1)M) = (-1)^n \det(M)$$
- If $n$ is even, $\det(-M) = \det(M)$.
- If $n$ is odd, $\det(-M) = -\det(M)$.

---

## 3. Detailed Step-by-Step Solution

The matrix $A$ has dimension $n = 3$, and its determinant is given as $\det A = -4$.

### Part 1: Compute $\det(2A)$
- **Property used:** $\det(c A) = c^n \det A$ with $c = 2$ and $n = 3$.
- **Calculation:**
  $$\det(2A) = 2^3 \cdot \det A = 8 \cdot (-4) = -32$$
- **Justification:** Multiplying $A$ by $2$ doubles each of the $3$ rows. By multilinearity, each doubled row factors out a $2$, giving $2 \cdot 2 \cdot 2 = 8$.

---

### Part 2: Compute $\det(A^T)$
- **Property used:** $\det(A^T) = \det A$.
- **Calculation:**
  $$\det(A^T) = \det A = -4$$
- **Justification:** Transposition exchanges rows and columns. Because the determinant can be evaluated identically along rows or along columns, the numerical value remains unchanged.

---

### Part 3: Compute $\det(A^2)$
- **Property used:** $\det(A^2) = (\det A)^2$.
- **Calculation:**
  $$\det(A^2) = (\det A)^2 = (-4)^2 = 16$$
- **Justification:** By the multiplicativity of the determinant, $\det(A \cdot A) = \det A \cdot \det A = (-4) \cdot (-4) = 16$.

---

### Part 4: Compute $\det(-A)$
- **Property used:** $\det(-A) = (-1)^n \det A$ with $n = 3$.
- **Calculation:**
  $$\det(-A) = (-1)^3 \cdot \det A = (-1) \cdot (-4) = 4$$
- **Justification:** Negating the matrix multiplies all $3$ rows by $-1$. Factoring out $-1$ from each of the three rows gives $(-1)^3 = -1$. Multiplying by $\det A = -4$ yields $+4$.

---

## 4. Verification and Consistency Checks

We can independently verify these results using a concrete representative diagonal matrix in $M_3(\mathbb{R})$ satisfying $\det A = -4$:
$$A_0 = \begin{pmatrix} -4 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix}$$

1. **Check $\det A_0$:**
   $$\det A_0 = (-4)(1)(1) = -4 \quad \checkmark$$

2. **Check $\det(2A_0)$:**
   $$2A_0 = \begin{pmatrix} -8 & 0 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 2 \end{pmatrix} \implies \det(2A_0) = (-8)(2)(2) = -32 \quad \checkmark$$

3. **Check $\det(A_0^T)$:**
   $$A_0^T = A_0 \implies \det(A_0^T) = -4 \quad \checkmark$$

4. **Check $\det(A_0^2)$:**
   $$A_0^2 = \begin{pmatrix} 16 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix} \implies \det(A_0^2) = (16)(1)(1) = 16 \quad \checkmark$$

5. **Check $\det(-A_0)$:**
   $$-A_0 = \begin{pmatrix} 4 & 0 & 0 \\ 0 & -1 & 0 \\ 0 & 0 & -1 \end{pmatrix} \implies \det(-A_0) = (4)(-1)(-1) = 4 \quad \checkmark$$

All four results match the theoretical predictions exactly.
