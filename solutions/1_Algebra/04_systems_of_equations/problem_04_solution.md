# Exercise 4: Infinitely Many Solutions

## 1. Problem Statement
Solve
$$\begin{cases}x+y+z=2,\\2x+2y+2z=4,\\x-y+z=0.\end{cases}$$
Give the solution in parametric form, identify a free variable, and for one chosen parameter value check that the resulting point really satisfies the system.

---

## 2. Theoretical Background and Concepts
When Gaussian elimination on a consistent system $Ax = b$ in $n$ unknowns terminates with $r = \operatorname{rank}(A) < n$ nonzero rows, the variables split into two classes:
- **Pivot (basic) variables:** the $r$ variables corresponding to columns that contain the leading nonzero entry (pivot) of a row.
- **Free variables (parameters):** the remaining $n - r$ variables corresponding to columns without pivots.

The free variables can take any real values independently, and the pivot variables are expressed uniquely as linear functions of those parameters. With $n - r = 1$ free variable $t \in \mathbb{R}$, the solution set forms a straight line in $\mathbb{R}^3$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Set up the augmented matrix and apply Gaussian elimination
We write the augmented matrix for the system:
$$[A \mid b] = \left[\begin{array}{ccc|c}
1 & 1 & 1 & 2 \\
2 & 2 & 2 & 4 \\
1 & -1 & 1 & 0
\end{array}\right].$$

Using the first pivot $a_{11} = 1$, we eliminate $x$ from Rows 2 and 3:
- $R_2 \leftarrow R_2 - 2R_1$: $(2, 2, 2 \mid 4) - 2(1, 1, 1 \mid 2) = (0, 0, 0 \mid 0)$,
- $R_3 \leftarrow R_3 - R_1$: $(1, -1, 1 \mid 0) - (1, 1, 1 \mid 2) = (0, -2, 0 \mid -2)$.

This gives:
$$\left[\begin{array}{ccc|c}
1 & 1 & 1 & 2 \\
0 & 0 & 0 & 0 \\
0 & -2 & 0 & -2
\end{array}\right].$$

Next, we swap Row 2 and Row 3 ($R_2 \leftrightarrow R_3$) to move the zero row to the bottom, and divide the new Row 2 by $-2$ ($R_2 \leftarrow -\frac{1}{2}R_2$):
$$\left[\begin{array}{ccc|c}
1 & 1 & 1 & 2 \\
0 & 1 & 0 & 1 \\
0 & 0 & 0 & 0
\end{array}\right].$$

### Step 2: Identify the pivot variables and the free variable
Looking at the row echelon form:
- **Row 1** has its leading nonzero entry (pivot) in **Column 1** ($x$).
- **Row 2** has its leading nonzero entry (pivot) in **Column 2** ($y$).
- **Row 3** is a zero row $0 = 0$, which shows that the second equation in the original system ($2x+2y+2z=4$) was simply twice the first equation and adds no new constraint.
- **Column 3** ($z$) has **no pivot**.

Therefore:
- **Pivot (basic) variables:** $x$ and $y$.
- **Free variable:** $z$.

### Step 3: Write the solution in parametric form
Let the free variable be assigned a real parameter $t \in \mathbb{R}$:
$$z = t, \quad t \in \mathbb{R}.$$
From the second row of the echelon matrix ($0x + 1y + 0z = 1$):
$$y = 1.$$
Substituting $y = 1$ and $z = t$ into the first row ($x + y + z = 2$):
$$x + 1 + t = 2 \implies x = 1 - t.$$

Hence, the general parametric solution is:
$$\begin{cases}
x = 1 - t, \\
y = 1, \\
z = t,
\end{cases} \quad t \in \mathbb{R},$$
or in vector form:
$$\begin{bmatrix} x \\ y \\ z \end{bmatrix} = \begin{bmatrix} 1 - t \\ 1 \\ t \end{bmatrix} = \begin{bmatrix} 1 \\ 1 \\ 0 \end{bmatrix} + t \begin{bmatrix} -1 \\ 0 \\ 1 \end{bmatrix}, \quad t \in \mathbb{R}.$$

---

## 4. Verification and Consistency Checks

### Check 1: Specific parameter value $t = 0$
Setting $t = 0$ in $(x, y, z) = (1 - t, 1, t)$ gives the point $(x, y, z) = (1, 1, 0)$. Substituting into the three original equations:
1. $x + y + z = 1 + 1 + 0 = 2$ (matches RHS $= 2$). $\checkmark$
2. $2x + 2y + 2z = 2(1) + 2(1) + 2(0) = 4$ (matches RHS $= 4$). $\checkmark$
3. $x - y + z = 1 - 1 + 0 = 0$ (matches RHS $= 0$). $\checkmark$

### Check 2: Specific parameter value $t = 2$
Setting $t = 2$ gives the point $(x, y, z) = (-1, 1, 2)$. Substituting into the three original equations:
1. $x + y + z = -1 + 1 + 2 = 2$ (matches RHS $= 2$). $\checkmark$
2. $2x + 2y + 2z = 2(-1) + 2(1) + 2(2) = -2 + 2 + 4 = 4$ (matches RHS $= 4$). $\checkmark$
3. $x - y + z = -1 - 1 + 2 = 0$ (matches RHS $= 0$). $\checkmark$

### Check 3: General parameter $t \in \mathbb{R}$
- Equation 1: $(1 - t) + 1 + t = 2$. $\checkmark$
- Equation 2: $2(1 - t) + 2(1) + 2t = 2 - 2t + 2 + 2t = 4$. $\checkmark$
- Equation 3: $(1 - t) - 1 + t = 0$. $\checkmark$
