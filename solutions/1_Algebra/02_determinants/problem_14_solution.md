# Solution to Exercise 14: A System of Equations and the Determinant

## 1. Problem Statement

Consider the linear system $Ax = b$, where the coefficient matrix is:
$$A = \begin{pmatrix} 1 & 2 \\ k & 4 \end{pmatrix}, \qquad k \in \mathbb{R}$$
and $b = \begin{pmatrix} b_1 \\ b_2 \end{pmatrix} \in \mathbb{R}^2$ is an arbitrary right-hand side vector.

1. Determine all values of the parameter $k$ for which the system $Ax = b$ has a **unique solution** for every vector $b$.
2. For the remaining value of $k$:
   - Provide an example of a right-hand side vector $b$ for which the system has **infinitely many solutions**, and write the general parametric solution.
   - Provide an example of a right-hand side vector $b$ for which the system has **no solution** (is inconsistent), and explain why contradiction arises.

---

## 2. Theoretical Background and Concepts

### Determinant and Solvability (Cramer's Rule & Invertibility)
For a square system of linear equations $Ax = b$ with $A \in M_n(\mathbb{R})$:
1. **Case $\det A \ne 0$ (Non-singular):**
   - $A$ is invertible, and the unique solution is given by $x = A^{-1}b$.
   - By Cramer's Rule, each coordinate is uniquely determined by $x_i = \frac{\det(A_i)}{\det A}$.
   - The system is guaranteed to have **exactly one solution for every possible vector $b$**.

2. **Case $\det A = 0$ (Singular):**
   - The matrix rows are linearly dependent, so the coefficient matrix cannot span the full output space.
   - By the **Rouché–Capelli Theorem**, solvability depends on whether the augmented matrix $[A | b]$ has the same rank as $A$:
     - If $\operatorname{rank}[A | b] = \operatorname{rank}(A) = 1$, the system is consistent and admits **infinitely many solutions** (with $2 - 1 = 1$ free parameter).
     - If $\operatorname{rank}[A | b] = 2 > \operatorname{rank}(A) = 1$, the right-hand side lies outside the column space of $A$, resulting in a contradiction and **no solution**.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $\det A$ and Determine the Unique Solution Condition
Compute the determinant of the coefficient matrix:
$$\det A = \begin{vmatrix} 1 & 2 \\ k & 4 \end{vmatrix} = (1)(4) - (2)(k) = 4 - 2k$$

The system has a unique solution for every $b$ if and only if $\det A \ne 0$:
$$4 - 2k \ne 0 \implies 2k \ne 4 \implies k \ne 2$$

**Conclusion:** The system has **exactly one solution for every $b$** if and only if:
$$k \ne 2$$

---

### Step 2: Analyze the Singular Case $k = 2$
When $k = 2$, the matrix is:
$$A = \begin{pmatrix} 1 & 2 \\ 2 & 4 \end{pmatrix}$$
Notice that Row 2 is exactly twice Row 1 ($R_2 = 2R_1$).
The linear system written out in component form is:
$$\begin{cases}
1x_1 + 2x_2 = b_1 \\
2x_1 + 4x_2 = b_2
\end{cases}$$

Multiplying the first equation by $2$ gives $2x_1 + 4x_2 = 2b_1$. Comparing this with the second equation yields:
$$2b_1 \stackrel{?}{=} b_2$$

---

### Step 3: Example with Infinitely Many Solutions ($k = 2$)
To obtain consistency, we must choose $b_2 = 2b_1$. 
Let:
$$b = \begin{pmatrix} 1 \\ 2 \end{pmatrix}$$

The system becomes:
$$\begin{cases}
x_1 + 2x_2 = 1 \\
2x_1 + 4x_2 = 2
\end{cases}$$
The second equation is a duplicate of the first ($2(x_1 + 2x_2) = 2 \cdot 1$).
The entire system reduces to a single equation:
$$x_1 + 2x_2 = 1 \implies x_1 = 1 - 2x_2$$

Letting $x_2 = t \in \mathbb{R}$ be a free parameter, the general solution is:
$$x = \begin{pmatrix} 1 - 2t \\ t \end{pmatrix} = \begin{pmatrix} 1 \\ 0 \end{pmatrix} + t \begin{pmatrix} -2 \\ 1 \end{pmatrix}, \qquad t \in \mathbb{R}$$
This represents a continuous line of solutions, hence **infinitely many solutions**.

---

### Step 4: Example with No Solution ($k = 2$)
To produce an inconsistent system, we choose $b_2 \ne 2b_1$.
Let:
$$b = \begin{pmatrix} 1 \\ 3 \end{pmatrix}$$

The system becomes:
$$\begin{cases}
x_1 + 2x_2 = 1 \quad &\implies \quad 2(x_1 + 2x_2) = 2 \\
2x_1 + 4x_2 = 3 \quad &\implies \quad 2x_1 + 4x_2 = 3
\end{cases}$$

Subtracting twice the first equation from the second equation:
$$(2x_1 + 4x_2) - 2(x_1 + 2x_2) = 3 - 2(1) \implies 0 = 1$$
This is an impossible contradiction ($0 = 1$). 

Therefore, for $b = \begin{pmatrix} 1 \\ 3 \end{pmatrix}$, the system is inconsistent and has **no solution**.

---

## 4. Verification and Consistency Checks

1. **Unique Solution Verification for $k \ne 2$:**
   For any $k \ne 2$, $\det A = 4 - 2k \ne 0$.
   Using the explicit matrix inverse:
   $$A^{-1} = \frac{1}{4 - 2k} \begin{pmatrix} 4 & -2 \\ -k & 1 \end{pmatrix}$$
   For any arbitrary $b = \begin{pmatrix} b_1 \\ b_2 \end{pmatrix}$, the unique solution is explicitly:
   $$x = A^{-1} b = \frac{1}{4 - 2k} \begin{pmatrix} 4b_1 - 2b_2 \\ -k b_1 + b_2 \end{pmatrix}$$
   This confirms that a well-defined, unique solution exists for every $b \in \mathbb{R}^2$ whenever $k \ne 2$.

2. **Rouché–Capelli Rank Verification for $k = 2$:**
   - Augmented matrix for $b = \begin{pmatrix} 1 \\ 2 \end{pmatrix}$:
     $$[A | b] = \begin{pmatrix} 1 & 2 & 1 \\ 2 & 4 & 2 \end{pmatrix} \xrightarrow{R_2 \leftarrow R_2 - 2R_1} \begin{pmatrix} 1 & 2 & 1 \\ 0 & 0 & 0 \end{pmatrix}$$
     Here $\operatorname{rank}(A) = \operatorname{rank}[A | b] = 1 < 2$ (consistent with 1 degree of freedom $\implies$ infinitely many solutions) $\checkmark$.
   - Augmented matrix for $b = \begin{pmatrix} 1 \\ 3 \end{pmatrix}$:
     $$[A | b] = \begin{pmatrix} 1 & 2 & 1 \\ 2 & 4 & 3 \end{pmatrix} \xrightarrow{R_2 \leftarrow R_2 - 2R_1} \begin{pmatrix} 1 & 2 & 1 \\ 0 & 0 & 1 \end{pmatrix}$$
     Here $\operatorname{rank}(A) = 1 \ne 2 = \operatorname{rank}[A | b]$ (inconsistent $\implies$ no solution) $\checkmark$.

