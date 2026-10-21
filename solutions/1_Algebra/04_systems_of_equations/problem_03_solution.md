# Exercise 3: Inconsistent System

## 1. Problem Statement
Solve or show that the system is inconsistent:
$$\begin{cases}x+2y=3,\\2x+4y=7.\end{cases}$$
Show how the contradiction appears in the matrix after elimination and interpret it in terms of equations.

---

## 2. Theoretical Background and Concepts
A system of linear equations is called **inconsistent** if its solution set is empty (no tuple of unknowns satisfies all equations simultaneously).

During Gaussian elimination on the augmented matrix $[A \mid b]$, inconsistency is revealed unambiguously when row reduction produces a **contradictory row** of the form:
$$[0 \quad 0 \quad \dots \quad 0 \mid c] \quad \text{with } c \ne 0.$$
In terms of the Rouché–Capelli theorem, this occurs when the rank of the coefficient matrix is strictly less than the rank of the augmented matrix:
$$\operatorname{rank}(A) < \operatorname{rank}([A \mid b]).$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Write the augmented matrix
For the system
$$\begin{cases}x+2y=3,\\2x+4y=7,\end{cases}$$
the augmented matrix is:
$$[A \mid b] = \left[\begin{array}{cc|c}
1 & 2 & 3 \\
2 & 4 & 7
\end{array}\right].$$

### Step 2: Perform Gaussian elimination
Using the pivot $a_{11} = 1$ in the first row, we eliminate $x$ from the second row by applying the elementary row operation $R_2 \leftarrow R_2 - 2R_1$:
$$(2, 4 \mid 7) - 2(1, 2 \mid 3) = (2 - 2, \, 4 - 4 \mid 7 - 6) = (0, 0 \mid 1).$$
The augmented matrix in row echelon form becomes:
$$\left[\begin{array}{cc|c}
1 & 2 & 3 \\
0 & 0 & 1
\end{array}\right].$$

### Step 3: Interpret the contradiction in the matrix and in the equations
- **Matrix and Equation Interpretation:**
  The second row of the reduced augmented matrix is $[0 \;\; 0 \mid 1]$, which translates directly to the linear equation:
  $$0x + 0y = 1 \iff 0 = 1.$$
  Since $0x + 0y = 0$ for every possible choice of real numbers $x, y \in \mathbb{R}$, the condition $0 = 1$ can never be satisfied. Therefore, the system is **inconsistent** and has **no solution** (the solution set is $\emptyset$).

- **Direct Algebraic Interpretation:**
  Notice that the left-hand side of the second equation, $2x + 4y$, is exactly twice the left-hand side of the first equation, $2(x + 2y)$. If a pair $(x, y)$ satisfies the first equation $x + 2y = 3$, then multiplying both sides by $2$ forces:
  $$2x + 4y = 2(x + 2y) = 2(3) = 6.$$
  However, the second equation simultaneously requires $2x + 4y = 7$. Because a single quantity cannot equal both $6$ and $7$ at the same time ($6 \ne 7$), the two conditions contradict each other.

- **Geometric Interpretation:**
  In the Cartesian plane $\mathbb{R}^2$, the two equations represent two straight lines:
  $$\ell_1: y = -\frac{1}{2}x + \frac{3}{2}, \qquad \ell_2: y = -\frac{1}{2}x + \frac{7}{4}.$$
  Both lines have the exact same slope $m = -\frac{1}{2}$, but different $y$-intercepts ($\frac{3}{2} \ne \frac{7}{4}$). Thus, $\ell_1$ and $\ell_2$ are **distinct parallel lines** that never intersect.

---

## 4. Verification and Consistency Checks
We can verify the rank condition from the row echelon form:
- The coefficient matrix $A$ reduces to $\begin{bmatrix} 1 & 2 \\ 0 & 0 \end{bmatrix}$, which has $1$ nonzero row, so $\operatorname{rank}(A) = 1$ (and $\det(A) = 1\cdot 4 - 2\cdot 2 = 0$).
- The augmented matrix $[A \mid b]$ reduces to $\left[\begin{array}{cc|c} 1 & 2 & 3 \\ 0 & 0 & 1 \end{array}\right]$, which has $2$ nonzero rows, so $\operatorname{rank}([A \mid b]) = 2$.

Since $\operatorname{rank}(A) = 1 < 2 = \operatorname{rank}([A \mid b])$, the Rouché–Capelli theorem confirms that the system is inconsistent.
