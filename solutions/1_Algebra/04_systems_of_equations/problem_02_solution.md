# Exercise 2: Gaussian Elimination — One Solution

## 1. Problem Statement
Solve using Gaussian elimination:
$$\begin{cases}x+y+z=6,\\2x-y+z=3,\\x+2y-z=2.\end{cases}$$
After solving, substitute the result into all equations and check consistency.

---

## 2. Theoretical Background and Concepts
**Gaussian elimination** is a systematic algorithm for solving a linear system $Ax = b$ by transforming its **augmented matrix** $[A \mid b]$ into an upper-triangular (row echelon) form using three **elementary row operations**:
1. Swapping two rows ($R_i \leftrightarrow R_j$),
2. Multiplying a row by a nonzero scalar ($R_i \leftarrow c R_i$, $c \ne 0$),
3. Adding a scalar multiple of one row to another row ($R_i \leftarrow R_i + c R_j$).

Elementary row operations are **reversible**, meaning they preserve the solution set of the linear system. Once the augmented matrix is in row echelon form, we solve for the unknowns from the bottom equation upward using **back-substitution**.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Set up the augmented matrix
We write the coefficients of $x, y, z$ and the right-hand side constants in the augmented matrix $[A \mid b]$:
$$[A \mid b] = \left[\begin{array}{ccc|c}
1 & 1 & 1 & 6 \\
2 & -1 & 1 & 3 \\
1 & 2 & -1 & 2
\end{array}\right].$$

### Step 2: Eliminate $x$ from the second and third rows
The top-left entry $a_{11} = 1$ serves as our first **pivot**. To create zeros below this pivot in column 1, we perform:
- $R_2 \leftarrow R_2 - 2R_1$: $(2, -1, 1 \mid 3) - 2(1, 1, 1 \mid 6) = (0, -3, -1 \mid -9)$,
- $R_3 \leftarrow R_3 - R_1$: $(1, 2, -1 \mid 2) - (1, 1, 1 \mid 6) = (0, 1, -2 \mid -4)$.

This transforms the augmented matrix into:
$$\left[\begin{array}{ccc|c}
1 & 1 & 1 & 6 \\
0 & -3 & -1 & -9 \\
0 & 1 & -2 & -4
\end{array}\right].$$

### Step 3: Eliminate $y$ from the third row
To avoid fractions during elimination, we can swap Row 2 and Row 3 ($R_2 \leftrightarrow R_3$) so that the second pivot is $1$:
$$\left[\begin{array}{ccc|c}
1 & 1 & 1 & 6 \\
0 & 1 & -2 & -4 \\
0 & -3 & -1 & -9
\end{array}\right].$$
Now we eliminate the entry below the second pivot (in position $(3,2)$) using the row operation:
- $R_3 \leftarrow R_3 + 3R_2$: $(0, -3, -1 \mid -9) + 3(0, 1, -2 \mid -4) = (0, 0, -7 \mid -21)$.

The augmented matrix is now in **row echelon form**:
$$\left[\begin{array}{ccc|c}
1 & 1 & 1 & 6 \\
0 & 1 & -2 & -4 \\
0 & 0 & -7 & -21
\end{array}\right].$$

### Step 4: Back-substitution
Translating the row echelon matrix back into equations gives the equivalent triangular system:
$$\begin{cases}
x + y + z = 6, \\
y - 2z = -4, \\
-7z = -21.
\end{cases}$$

We solve from the last equation upward:
1. From the third equation:
   $$-7z = -21 \implies z = \frac{-21}{-7} = 3.$$
2. Substitute $z = 3$ into the second equation:
   $$y - 2(3) = -4 \implies y - 6 = -4 \implies y = 2.$$
3. Substitute $y = 2$ and $z = 3$ into the first equation:
   $$x + 2 + 3 = 6 \implies x + 5 = 6 \implies x = 1.$$

Thus, the system has a unique solution:
$$(x, y, z) = (1, 2, 3).$$

---

## 4. Verification and Consistency Checks
We substitute $(x, y, z) = (1, 2, 3)$ into each of the three original equations to verify consistency:

1. **First equation:**
   $$x + y + z = 1 + 2 + 3 = 6 \quad \text{(matches RHS } = 6\text{)}. \quad \checkmark$$
2. **Second equation:**
   $$2x - y + z = 2(1) - 2 + 3 = 2 - 2 + 3 = 3 \quad \text{(matches RHS } = 3\text{)}. \quad \checkmark$$
3. **Third equation:**
   $$x + 2y - z = 1 + 2(2) - 3 = 1 + 4 - 3 = 2 \quad \text{(matches RHS } = 2\text{)}. \quad \checkmark$$

All three equations are satisfied simultaneously, confirming that $(x, y, z) = (1, 2, 3)$ is the exact solution.
