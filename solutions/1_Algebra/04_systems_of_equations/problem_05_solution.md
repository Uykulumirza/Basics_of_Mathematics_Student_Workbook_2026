# Exercise 5: Row Echelon Form and Number of Solutions

## 1. Problem Statement
For the augmented matrix
$$\left[\begin{array}{ccc|c}1&2&-1&3\\0&1&2&1\\0&0&0&0\end{array}\right]$$
determine the number of solutions and write them in parametric form. Explain how you know how many variables may be chosen freely.

---

## 2. Theoretical Background and Concepts
From an augmented matrix $[A \mid b]$ that is already in **row echelon form**, we can read off the complete structure of the solution set without any further forward elimination:
1. **Consistency check:** The system is consistent if and only if there is no row of the form $[0 \;\; 0 \;\; \dots \;\; 0 \mid c]$ with $c \ne 0$. Equivalently, $\operatorname{rank}(A) = \operatorname{rank}([A \mid b])$.
2. **Counting pivots and free variables:** Every nonzero row has a single **leading entry** (the first nonzero number from the left), called a **pivot**. If the system has $n$ unknowns and $r = \operatorname{rank}(A)$ pivots:
   - The $r$ columns containing pivots correspond to the **basic (pivot) variables**, which are uniquely determined once the remaining variables are fixed.
   - The remaining $n - r$ columns without pivots correspond to the **free variables**, which may be chosen arbitrarily in $\mathbb{R}$.
   - Whenever the system is consistent and $n - r \ge 1$, there are **infinitely many solutions** (an $(n-r)$-parameter family).

---

## 3. Detailed Step-by-Step Solution

### Step 1: Analyze the row echelon structure and determine the number of solutions
Let the three columns to the left of the vertical bar correspond to the unknowns $x, y, z$ (so $n = 3$). Examining the given augmented matrix:
$$\left[\begin{array}{ccc|c}
\boxed{1} & 2 & -1 & 3 \\
0 & \boxed{1} & 2 & 1 \\
0 & 0 & 0 & 0
\end{array}\right]$$
- The third row is $[0 \;\; 0 \;\; 0 \mid 0]$, which represents the identity $0 = 0$ (not a contradiction). Hence, the system is **consistent**: $\operatorname{rank}(A) = \operatorname{rank}([A \mid b]) = 2$.
- There are $r = 2$ nonzero rows, with pivots located in **Column 1** (for $x$) and **Column 2** (for $y$).
- **Column 3** (for $z$) contains **no pivot**.

### Step 2: Explain how many variables may be chosen freely
The total number of unknowns is $n = 3$ (the number of columns of $A$), and the number of independent constraints (nonzero rows / pivots in $A$) is $r = \operatorname{rank}(A) = 2$. Each pivot equation locks in the value of its leading variable in terms of the variables to its right. Therefore, the number of variables that are not constrained by a pivot is:
$$\text{Number of free variables} = n - \operatorname{rank}(A) = 3 - 2 = 1.$$
Specifically, $z$ corresponds to the single non-pivot column (Column 3), so **$1$ variable ($z$) may be chosen freely**, and the system has **infinitely many solutions**.

### Step 3: Derive the parametric solution via back-substitution
Translating the two nonzero rows into equations in $x, y, z$:
$$\begin{cases}
x + 2y - z = 3, \\
y + 2z = 1.
\end{cases}$$

1. Set the free variable $z$ equal to an arbitrary real parameter $t \in \mathbb{R}$:
   $$z = t, \quad t \in \mathbb{R}.$$
2. Solve the second equation for the second pivot variable $y$:
   $$y + 2t = 1 \implies y = 1 - 2t.$$
3. Substitute $y = 1 - 2t$ and $z = t$ into the first equation to solve for the first pivot variable $x$:
   $$x + 2(1 - 2t) - t = 3 \implies x + 2 - 4t - t = 3 \implies x - 5t = 1 \implies x = 1 + 5t.$$

Thus, the complete parametric solution set is:
$$\begin{cases}
x = 1 + 5t, \\
y = 1 - 2t, \\
z = t,
\end{cases} \quad t \in \mathbb{R},$$
or in vector notation:
$$\begin{bmatrix} x \\ y \\ z \end{bmatrix} = \begin{bmatrix} 1 + 5t \\ 1 - 2t \\ t \end{bmatrix} = \begin{bmatrix} 1 \\ 1 \\ 0 \end{bmatrix} + t \begin{bmatrix} 5 \\ -2 \\ 1 \end{bmatrix}, \quad t \in \mathbb{R}.$$

---

## 4. Verification and Consistency Checks
We verify that the parametric vector $(x, y, z) = (1 + 5t, 1 - 2t, t)$ satisfies all three rows of the augmented matrix for every $t \in \mathbb{R}$:
1. **Row 1:**
   $$1(x) + 2(y) - 1(z) = (1 + 5t) + 2(1 - 2t) - t = 1 + 5t + 2 - 4t - t = 3 \quad (\text{matches RHS } = 3). \quad \checkmark$$
2. **Row 2:**
   $$0(x) + 1(y) + 2(z) = (1 - 2t) + 2t = 1 \quad (\text{matches RHS } = 1). \quad \checkmark$$
3. **Row 3:**
   $$0(x) + 0(y) + 0(z) = 0 \quad (\text{matches RHS } = 0). \quad \checkmark$$

All equations hold identically for every $t \in \mathbb{R}$.
