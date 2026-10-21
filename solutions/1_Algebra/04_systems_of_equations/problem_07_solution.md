# Exercise 7: Choosing a Method Deliberately

## 1. Problem Statement
Do not solve all of the following systems completely. For each situation, choose the method that best uses its structure and justify your choice:

1. one system with a triangular coefficient matrix
   $$\begin{cases}2x-y=3,\\4y=8;\end{cases}$$
2. three systems $Ax=b_i$ with the same invertible matrix $A$, when $A^{-1}$ is already known;
3. one $3\times3$ system for which the inverse matrix is not given and the goal is only to find one solution vector.

For case 1, carry out the chosen method completely. For cases 2 and 3, describe the plan and indicate which part of the computation would be reusable or unnecessary. Do not judge a method by its name alone — refer to the number of right-hand sides and the structure of the matrix.

---

## 2. Theoretical Background and Concepts
Different algebraic methods for solving $Ax = b$ have different computational costs depending on what information is already available and how many right-hand side vectors must be processed:
- **Direct Back-Substitution:** Applies immediately when $A$ is already in upper-triangular (row echelon) form. No forward elimination or matrix inversion is needed; solving an $n\times n$ triangular system requires only $O(n^2)$ arithmetic operations.
- **Multiplication by a Known Inverse ($x = A^{-1}b$):** If the inverse matrix $A^{-1}$ has **already been computed and given**, finding $x$ for any right-hand side $b_i$ reduces to a single matrix-vector multiplication $x_i = A^{-1}b_i$, costing $n^2$ multiplications and $n(n-1)$ additions per right-hand side.
- **Gaussian Elimination with Back-Substitution vs. Full Matrix Inversion:** When $A^{-1}$ is **not** known and we only need to solve $Ax = b$ for a single right-hand side $b$, Gaussian elimination reduces $[A \mid b]$ to upper-triangular form in roughly $\frac{2}{3}n^3$ operations. Computing $A^{-1}$ first via Gauss–Jordan elimination on $[A \mid I_n]$ is equivalent to solving **three** (or $n$) systems $Ax_j = e_j$ simultaneously, costing roughly $2n^3$ operations—three times as much work as Gaussian elimination for a single vector $b$.

---

## 3. Detailed Step-by-Step Solution

### Case 1: One System with a Triangular Coefficient Matrix
$$\begin{cases}2x-y=3,\\4y=8.\end{cases}$$

- **Chosen Method:** **Direct back-substitution** (with zero forward-elimination steps).
- **Justification from Structure:** Written in matrix form,
  $$\begin{bmatrix} 2 & -1 \\ 0 & 4 \end{bmatrix} \begin{bmatrix} x \\ y \end{bmatrix} = \begin{bmatrix} 3 \\ 8 \end{bmatrix},$$
  the coefficient matrix is **already upper-triangular** (the entry below the main diagonal is $0$, so the second equation contains only the single unknown $y$). Performing row reduction, computing determinants (Cramer's rule), or finding $A^{-1}$ would be completely redundant because the purpose of Gaussian elimination is precisely to reach this triangular structure.
- **Complete Calculation:**
  1. Solve the second equation directly for $y$:
     $$4y = 8 \implies y = \frac{8}{4} = 2.$$
  2. Substitute $y = 2$ upward into the first equation to solve for $x$:
     $$2x - 2 = 3 \implies 2x = 5 \implies x = \frac{5}{2}.$$
  Thus, the unique solution is $(x, y) = \left(\frac{5}{2}, \, 2\right)$.

---

### Case 2: Three Systems $Ax = b_i$ ($i = 1, 2, 3$) When $A^{-1}$ Is Already Known

- **Chosen Method:** **Direct matrix-vector multiplication** $x_i = A^{-1}b_i$ for each $i = 1, 2, 3$.
- **Computational Plan:**
  Since $A$ is invertible, each system $Ax_i = b_i$ has the unique solution $x_i = A^{-1}b_i$. We simply compute the three matrix-vector products:
  $$x_1 = A^{-1}b_1, \qquad x_2 = A^{-1}b_2, \qquad x_3 = A^{-1}b_3.$$
- **What Is Reused and What Would Be Unnecessary:**
  - **Reused:** The precomputed inverse matrix $A^{-1}$ is **reused across all three right-hand sides** $b_1, b_2, b_3$. All the work of inverting/factoring $A$ has already been paid for in advance.
  - **Unnecessary:** Running Gaussian elimination from scratch on $[A \mid b_1]$, $[A \mid b_2]$, and $[A \mid b_3]$ (or even on $[A \mid b_1 \mid b_2 \mid b_3]$) would be unnecessary work because reducing $A$ to row echelon form repeats work that is already encapsulated in $A^{-1}$.

---

### Case 3: One $3\times 3$ System Where $A^{-1}$ Is Not Given and Only One Solution Vector Is Needed

- **Chosen Method:** **Gaussian elimination to row echelon form followed by back-substitution** on the single augmented matrix $[A \mid b]$.
- **Computational Plan:**
  1. Form the $3\times 4$ augmented matrix $[A \mid b]$.
  2. Use elementary row operations (requiring at most $3$ elimination steps: two in column 1 and one in column 2) to reduce $[A \mid b]$ to upper-triangular row echelon form $[U \mid c]$.
  3. Solve the resulting $3\times 3$ upper-triangular system $Ux = c$ from bottom to top via back-substitution.
- **What Would Be Unnecessary (and What Could Be Reused If More RHS Appeared Later):**
  - **Unnecessary:** Computing the full $3\times 3$ inverse matrix $A^{-1}$ (e.g., via $[A \mid I_3] \to [I_3 \mid A^{-1}]$ or via the adjugate formula $A^{-1} = \frac{1}{\det A}\operatorname{adj}(A)$) and then multiplying $A^{-1}b$ would do **roughly three times as much work**. Specifically, finding $A^{-1}$ solves three systems $Ax = e_1$, $Ax = e_2$, and $Ax = e_3$ for the three columns of the $3\times 3$ identity matrix $I_3$, plus requires upward elimination above the pivots, whereas we only need the solution for **one** right-hand side vector $b$.
  - **Note on Reusability:** If we ever needed to solve for additional right-hand sides later, we could record the elimination multipliers from Gaussian elimination as an $LU$ factorization ($A = LU$), which reuses the forward-elimination work without paying the higher cost of computing $A^{-1}$.

---

## 4. Verification and Consistency Checks
Let us verify the solution $(x, y) = \left(\frac{5}{2}, 2\right)$ obtained in Case 1 by substituting it back into the original system:
1. **First equation:**
   $$2x - y = 2\left(\frac{5}{2}\right) - 2 = 5 - 2 = 3 \quad (\text{matches RHS } = 3). \quad \checkmark$$
2. **Second equation:**
   $$4y = 4(2) = 8 \quad (\text{matches RHS } = 8). \quad \checkmark$$

Both equations are satisfied, and our operation counts across Cases 1, 2, and 3 confirm that each chosen method minimizes redundant computation.
