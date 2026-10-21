# Exercise 1: From a System to a Matrix

## 1. Problem Statement
Write the system
$$\begin{cases}2x-y+z=4,\\x+3y-2z=1,\\3x+y+z=7.\end{cases}$$
in the form $Ax=b$.
Identify the coefficient matrix, the vector of unknowns, and the right-hand side vector. Explain how each row of the matrix corresponds to one equation.

---

## 2. Theoretical Background and Concepts
A system of $m$ linear equations in $n$ unknowns $x_1, x_2, \dots, x_n$:
$$\begin{cases}
a_{11}x_1 + a_{12}x_2 + \dots + a_{1n}x_n = b_1, \\
a_{21}x_1 + a_{22}x_2 + \dots + a_{2n}x_n = b_2, \\
\vdots \\
a_{m1}x_1 + a_{m2}x_2 + \dots + a_{mn}x_n = b_m
\end{cases}$$
can be expressed compactly as a single matrix equation:
$$Ax = b,$$
where:
- $A = [a_{ij}] \in \mathbb{R}^{m\times n}$ is the **coefficient matrix**, whose entry $a_{ij}$ in row $i$ and column $j$ is the scalar coefficient multiplying the $j$-th unknown $x_j$ in the $i$-th equation.
- $x = \begin{bmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{bmatrix} \in \mathbb{R}^{n\times 1}$ is the column **vector of unknowns**.
- $b = \begin{bmatrix} b_1 \\ b_2 \\ \vdots \\ b_m \end{bmatrix} \in \mathbb{R}^{m\times 1}$ is the **right-hand side vector** (constant vector).

By the definition of matrix-vector multiplication, the $i$-th entry of the product $Ax$ is the dot product of the $i$-th row of $A$ with the column vector $x$. Equating the two column vectors $Ax$ and $b$ component-by-component reproduces the original system of scalar equations.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Align the variables and read off the coefficients
First, we ensure that the variables $x, y, z$ appear in the same order in all three equations, explicitly noting implicit coefficients of $1$ or $-1$:
$$\begin{cases}
2x + (-1)y + 1z = 4, \\
1x + 3y + (-2)z = 1, \\
3x + 1y + 1z = 7.
\end{cases}$$

### Step 2: Identify the three components of $Ax = b$
1. **Coefficient matrix $A$ ($3\times 3$):**
   Each row collects the coefficients of $(x, y, z)$ from one equation, and each column corresponds to one specific variable (column 1 for $x$, column 2 for $y$, column 3 for $z$):
   $$A = \begin{bmatrix} 2 & -1 & 1 \\ 1 & 3 & -2 \\ 3 & 1 & 1 \end{bmatrix}.$$

2. **Vector of unknowns $x$ ($3\times 1$):**
   The three variables are arranged in a vertical column vector matching the column order of $A$:
   $$x = \begin{bmatrix} x \\ y \\ z \end{bmatrix}.$$
   *(Note: Here the bold/vector symbol $x$ denotes the column vector of all three unknowns $(x,y,z)^T$, whereas the first entry inside the vector is the scalar coordinate $x$.)*

3. **Right-hand side vector $b$ ($3\times 1$):**
   The constants on the right-hand side of each equation form a column vector in the same row order:
   $$b = \begin{bmatrix} 4 \\ 1 \\ 7 \end{bmatrix}.$$

### Step 3: Write the complete matrix equation $Ax = b$
Putting these three components together gives the matrix form of the system:
$$\begin{bmatrix} 2 & -1 & 1 \\ 1 & 3 & -2 \\ 3 & 1 & 1 \end{bmatrix} \begin{bmatrix} x \\ y \\ z \end{bmatrix} = \begin{bmatrix} 4 \\ 1 \\ 7 \end{bmatrix}.$$

### Step 4: Explain how each row of $A$ corresponds to one equation
When we multiply the $3\times 3$ matrix $A$ by the $3\times 1$ column vector $x$, the $i$-th entry of the resulting $3\times 1$ vector $Ax$ is obtained by taking the dot product of the $i$-th row of $A$, denoted $r_i$, with the vector $x$:
- **Row 1:** $r_1 \cdot x = \begin{bmatrix} 2 & -1 & 1 \end{bmatrix} \begin{bmatrix} x \\ y \\ z \end{bmatrix} = 2x - y + z$. Setting this equal to the first entry of $b$ gives $2x - y + z = 4$ (Equation 1).
- **Row 2:** $r_2 \cdot x = \begin{bmatrix} 1 & 3 & -2 \end{bmatrix} \begin{bmatrix} x \\ y \\ z \end{bmatrix} = x + 3y - 2z$. Setting this equal to the second entry of $b$ gives $x + 3y - 2z = 1$ (Equation 2).
- **Row 3:** $r_3 \cdot x = \begin{bmatrix} 3 & 1 & 1 \end{bmatrix} \begin{bmatrix} x \\ y \\ z \end{bmatrix} = 3x + y + z$. Setting this equal to the third entry of $b$ gives $3x + y + z = 7$ (Equation 3).

---

## 4. Verification and Consistency Checks
Let us expand the matrix product $Ax$ explicitly and equate it to $b$:
$$Ax = \begin{bmatrix} 2(x) + (-1)(y) + 1(z) \\ 1(x) + 3(y) + (-2)(z) \\ 3(x) + 1(y) + 1(z) \end{bmatrix} = \begin{bmatrix} 2x - y + z \\ x + 3y - 2z \\ 3x + y + z \end{bmatrix}.$$
Two vectors in $\mathbb{R}^3$ are equal if and only if their corresponding components are equal:
$$\begin{bmatrix} 2x - y + z \\ x + 3y - 2z \\ 3x + y + z \end{bmatrix} = \begin{bmatrix} 4 \\ 1 \\ 7 \end{bmatrix} \iff \begin{cases}2x-y+z=4,\\x+3y-2z=1,\\3x+y+z=7.\end{cases}$$
The dimensions also match: $A$ is $3\times 3$ and $x$ is $3\times 1$, so $Ax$ is a well-defined $3\times 1$ vector, matching the dimension of $b$.
