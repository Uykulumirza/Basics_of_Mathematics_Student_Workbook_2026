# Exercise 13: Does Every Equation Add New Information?

## 1. Problem Statement
Consider the system
$$x_1+x_2=10,\qquad x_2+x_3=8,\qquad x_1-x_3=2.$$
Solve it and check whether all three equations are independently necessary to describe the solution set. If one follows from the others, show this by calculation.

---

## 2. Theoretical Background and Concepts
In a system of linear equations, an equation is **redundant** (linearly dependent on the others) if it can be obtained as a linear combination of the remaining equations. Removing a redundant equation does not alter the solution set of the system.

During Gaussian elimination, a redundant equation manifests as a **zero row** $[0 \;\; 0 \;\; \dots \;\; 0 \mid 0]$ ($0 = 0$) in the row echelon form of the augmented matrix. Each zero row reduces the number of independent constraints ($\operatorname{rank}(A)$) by one below the total number of equations.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Set up the augmented matrix and solve by Gaussian elimination
Writing the three equations in aligned columns for $x_1, x_2, x_3$:
$$\begin{cases}
E_1: \;\; x_1 + x_2 \phantom{{}+ x_3} = 10, \\
E_2: \;\; \phantom{x_1 +{}} x_2 + x_3 = 8, \\
E_3: \;\; x_1 \phantom{{}+ x_2} - x_3 = 2,
\end{cases}$$
the augmented matrix is:
$$[A \mid b] = \left[\begin{array}{ccc|c}
1 & 1 & 0 & 10 \\
0 & 1 & 1 & 8 \\
1 & 0 & -1 & 2
\end{array}\right].$$

1. Eliminate $x_1$ from Row 3 using $R_3 \leftarrow R_3 - R_1$:
   $$(1, 0, -1 \mid 2) - (1, 1, 0 \mid 10) = (0, -1, -1 \mid -8).$$
   The augmented matrix becomes:
   $$\left[\begin{array}{ccc|c}
   1 & 1 & 0 & 10 \\
   0 & 1 & 1 & 8 \\
   0 & -1 & -1 & -8
   \end{array}\right].$$

2. Eliminate $x_2$ from Row 3 using $R_3 \leftarrow R_3 + R_2$:
   $$(0, -1, -1 \mid -8) + (0, 1, 1 \mid 8) = (0, 0, 0 \mid 0).$$
   This yields the row echelon form:
   $$\left[\begin{array}{ccc|c}
   1 & 1 & 0 & 10 \\
   0 & 1 & 1 & 8 \\
   0 & 0 & 0 & 0
   \end{array}\right].$$

### Step 2: Write the parametric solution
The row echelon matrix has $r = 2$ pivots in Columns 1 ($x_1$) and 2 ($x_2$), while Column 3 ($x_3$) has no pivot. Setting the free variable $x_3 = t \in \mathbb{R}$ and back-substituting:
1. From Row 2 ($x_2 + x_3 = 8$):
   $$x_2 = 8 - x_3 = 8 - t.$$
2. From Row 1 ($x_1 + x_2 = 10$):
   $$x_1 = 10 - x_2 = 10 - (8 - t) = 2 + t.$$

Thus, the general solution is:
$$\begin{cases}
x_1 = 2 + t, \\
x_2 = 8 - t, \\
x_3 = t,
\end{cases} \quad t \in \mathbb{R}, \qquad \text{or} \qquad \begin{bmatrix} x_1 \\ x_2 \\ x_3 \end{bmatrix} = \begin{bmatrix} 2 \\ 8 \\ 0 \end{bmatrix} + t \begin{bmatrix} 1 \\ -1 \\ 1 \end{bmatrix}, \quad t \in \mathbb{R}.$$

### Step 3: Check whether all three equations are independently necessary
**No**, all three equations are **not** independently necessary to describe the solution set. As shown by the zero row $[0 \;\; 0 \;\; 0 \mid 0]$ produced via $R_3 - R_1 + R_2 = \mathbf{0}$, the third equation follows automatically from the first two (in fact, any one of the three equations follows from the other two).

**Direct Algebraic Calculation Showing Redundancy:**
Suppose $(x_1, x_2, x_3)$ satisfies the first two equations:
$$E_1: \;\; x_1 + x_2 = 10 \qquad \text{and} \qquad E_2: \;\; x_2 + x_3 = 8.$$
Subtracting Equation $E_2$ from Equation $E_1$ side-by-side cancels $x_2$:
$$\underbrace{(x_1 + x_2)}_{10} - \underbrace{(x_2 + x_3)}_{8} = 10 - 8 \implies x_1 - x_3 = 2,$$
which is **identically the third equation $E_3$** ($E_3 = E_1 - E_2$). Therefore, $E_3$ adds **no new information** beyond what is already contained in $E_1$ and $E_2$; the first two equations alone completely determine the solution set.

---

## 4. Verification and Consistency Checks
Let us substitute $(x_1, x_2, x_3) = (2 + t, 8 - t, t)$ into all three original equations:
1. **Equation 1:**
   $$x_1 + x_2 = (2 + t) + (8 - t) = 10 \quad (\text{matches RHS } = 10). \quad \checkmark$$
2. **Equation 2:**
   $$x_2 + x_3 = (8 - t) + t = 8 \quad (\text{matches RHS } = 8). \quad \checkmark$$
3. **Equation 3:**
   $$x_1 - x_3 = (2 + t) - t = 2 \quad (\text{matches RHS } = 2). \quad \checkmark$$

All three equations are satisfied for every $t \in \mathbb{R}$, and the solution set of the two-equation system $\{x_1 + x_2 = 10, \; x_2 + x_3 = 8\}$ is identical to that of the full three-equation system.
