# Exercise 8: Two Systems with the Same Coefficient Matrix

## 1. Problem Statement
Solve by elimination the two systems
$$\begin{cases}2x+y=5,\\x-y=1,\end{cases}$$
$$\begin{cases}2x+y=1,\\x-y=4.\end{cases}$$
Compare the successive elimination steps. Which part of the calculation is the same in both cases, and why?

---

## 2. Theoretical Background and Concepts
When solving a linear system $Ax = b$ by Gaussian elimination, the sequence of elementary row operations (which rows to swap, which pivot to use, and which elimination multipliers $m_{ij} = \frac{a_{ij}}{a_{jj}}$ to subtract) is determined **exclusively by the entries of the coefficient matrix $A$**.

The right-hand side vector $b$ plays a passive role: it undergoes the exact same row operations alongside $A$, but its values never influence the choice of row operations or the resulting upper-triangular matrix $U$. Because of this property, multiple systems sharing the same coefficient matrix $A$,
$$Ax = b_1, \qquad Ax = b_2,$$
can either be reduced using the identical sequence of row operations or solved simultaneously inside a doubly augmented matrix $[A \mid b_1 \mid b_2]$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Identify the shared coefficient matrix and the two right-hand sides
Both systems share the same $2\times 2$ coefficient matrix $A$, while differing only in their right-hand side vectors $b_1$ and $b_2$:
$$A = \begin{bmatrix} 2 & 1 \\ 1 & -1 \end{bmatrix}, \qquad b_1 = \begin{bmatrix} 5 \\ 1 \end{bmatrix}, \qquad b_2 = \begin{bmatrix} 1 \\ 4 \end{bmatrix}.$$

### Step 2: Solve both systems side-by-side using the exact same elimination steps

#### Operation 1: Swap Row 1 and Row 2 ($R_1 \leftrightarrow R_2$) to place a pivot of $1$ in position $(1,1)$
- **System 1 ($[A \mid b_1]$):**
  $$\left[\begin{array}{cc|c} 2 & 1 & 5 \\ 1 & -1 & 1 \end{array}\right] \xrightarrow{R_1 \leftrightarrow R_2} \left[\begin{array}{cc|c} 1 & -1 & 1 \\ 2 & 1 & 5 \end{array}\right].$$
- **System 2 ($[A \mid b_2]$):**
  $$\left[\begin{array}{cc|c} 2 & 1 & 1 \\ 1 & -1 & 4 \end{array}\right] \xrightarrow{R_1 \leftrightarrow R_2} \left[\begin{array}{cc|c} 1 & -1 & 4 \\ 2 & 1 & 1 \end{array}\right].$$

#### Operation 2: Eliminate $x$ from Row 2 using $R_2 \leftarrow R_2 - 2R_1$
- **System 1:**
  $$\left[\begin{array}{cc|c} 1 & -1 & 1 \\ 2 & 1 & 5 \end{array}\right] \xrightarrow{R_2 \leftarrow R_2 - 2R_1} \left[\begin{array}{cc|c} 1 & -1 & 1 \\ 0 & 3 & 3 \end{array}\right].$$
- **System 2:**
  $$\left[\begin{array}{cc|c} 1 & -1 & 4 \\ 2 & 1 & 1 \end{array}\right] \xrightarrow{R_2 \leftarrow R_2 - 2R_1} \left[\begin{array}{cc|c} 1 & -1 & 4 \\ 0 & 3 & -7 \end{array}\right].$$

*(Equivalently, written as a single doubly augmented matrix $[A \mid b_1 \mid b_2]$, both reductions happen at once:)*
$$\left[\begin{array}{cc|c|c} 2 & 1 & 5 & 1 \\ 1 & -1 & 1 & 4 \end{array}\right] \xrightarrow{R_1 \leftrightarrow R_2} \left[\begin{array}{cc|c|c} 1 & -1 & 1 & 4 \\ 2 & 1 & 5 & 1 \end{array}\right] \xrightarrow{R_2 \leftarrow R_2 - 2R_1} \left[\begin{array}{cc|c|c} 1 & -1 & 1 & 4 \\ 0 & 3 & 3 & -7 \end{array}\right].$$

### Step 3: Perform back-substitution for each system
- **For System 1:**
  From Row 2: $3y = 3 \implies y = 1$.
  Substituting $y = 1$ into Row 1 ($x - y = 1$):
  $$x - 1 = 1 \implies x = 2.$$
  **Solution to System 1:** $(x, y) = (2, 1)$.

- **For System 2:**
  From Row 2: $3y = -7 \implies y = -\frac{7}{3}$.
  Substituting $y = -\frac{7}{3}$ into Row 1 ($x - y = 4$):
  $$x - \left(-\frac{7}{3}\right) = 4 \implies x + \frac{7}{3} = \frac{12}{3} \implies x = \frac{5}{3}.$$
  **Solution to System 2:** $(x, y) = \left(\frac{5}{3}, \, -\frac{7}{3}\right)$.

### Step 4: Compare the steps — What is the same and why?
1. **What is identical:**
   - The **choice of row operations** ($R_1 \leftrightarrow R_2$ followed by $R_2 \leftarrow R_2 - 2R_1$),
   - The **elimination multiplier** ($m_{21} = 2$),
   - Every intermediate and final entry on the **left-hand side** of the augmented matrix, which reduces from $A = \begin{bmatrix} 2 & 1 \\ 1 & -1 \end{bmatrix}$ to the exact same upper-triangular matrix $U = \begin{bmatrix} 1 & -1 \\ 0 & 3 \end{bmatrix}$,
   - The **divisors** used during back-substitution (dividing by the pivots $3$ and $1$).
2. **Why it is identical:**
   The goal of forward elimination is to create zeros below the main diagonal of the **coefficient matrix $A$**. Since the entries of $A$ are identical in both systems, the ratios of coefficients that dictate which multiples of rows to subtract depend solely on $A$ and are completely independent of the numbers on the right-hand side $b$.

---

## 4. Verification and Consistency Checks
- **Verification of System 1 with $(x, y) = (2, 1)$:**
  - $2x + y = 2(2) + 1 = 5$ (matches RHS $= 5$). $\checkmark$
  - $x - y = 2 - 1 = 1$ (matches RHS $= 1$). $\checkmark$

- **Verification of System 2 with $(x, y) = \left(\frac{5}{3}, -\frac{7}{3}\right)$:**
  - $2x + y = 2\left(\frac{5}{3}\right) + \left(-\frac{7}{3}\right) = \frac{10 - 7}{3} = \frac{3}{3} = 1$ (matches RHS $= 1$). $\checkmark$
  - $x - y = \frac{5}{3} - \left(-\frac{7}{3}\right) = \frac{5 + 7}{3} = \frac{12}{3} = 4$ (matches RHS $= 4$). $\checkmark$
