# Exercise 15: Classifying Three Systems

## 1. Problem Statement
For each of the following systems, perform only as much elimination as necessary to recognize its type:

1. $\begin{cases}x+y=2,\\x-y=0,\end{cases}$
2. $\begin{cases}x+y=2,\\2x+2y=4,\end{cases}$
3. $\begin{cases}x+y=2,\\2x+2y=5.\end{cases}$

For each, justify the classification: one solution, infinitely many solutions, or no solution.

---

## 2. Theoretical Background and Concepts
To classify a $2\times 2$ linear system $Ax = b$, we only need **one forward-elimination step** to eliminate $x$ from the second row, bringing the augmented matrix $[A \mid b]$ into **row echelon form**:
$$\left[\begin{array}{cc|c}
a_{11} & a_{12} & b_1 \\
0 & \tilde{a}_{22} & \tilde{b}_2
\end{array}\right] \quad (a_{11} \ne 0).$$
We do **not** need to carry out back-substitution to classify the system; the second row $[0 \;\; \tilde{a}_{22} \mid \tilde{b}_2]$ immediately determines which of the three basic cases holds:
1. **$\tilde{a}_{22} \ne 0$:** Both columns have pivots ($\operatorname{rank}(A) = \operatorname{rank}([A \mid b]) = 2 = n$). The system has **exactly one solution**.
2. **$\tilde{a}_{22} = 0$ and $\tilde{b}_2 = 0$:** Row 2 is $[0 \;\; 0 \mid 0]$ ($0 = 0$). There is only $1$ pivot for $2$ unknowns ($\operatorname{rank}(A) = \operatorname{rank}([A \mid b]) = 1 < 2$), leaving $2 - 1 = 1$ free variable. The system has **infinitely many solutions**.
3. **$\tilde{a}_{22} = 0$ and $\tilde{b}_2 \ne 0$:** Row 2 is $[0 \;\; 0 \mid \tilde{b}_2]$ ($0 = \tilde{b}_2 \ne 0$), a contradiction ($\operatorname{rank}(A) = 1 < 2 = \operatorname{rank}([A \mid b])$). The system has **no solution** (inconsistent).

---

## 3. Detailed Step-by-Step Solution

### System 1: $\begin{cases}x+y=2,\\x-y=0\end{cases}$

- **Minimal Elimination Step:**
  Set up the augmented matrix and apply $R_2 \leftarrow R_2 - R_1$:
  $$\left[\begin{array}{cc|c}
  1 & 1 & 2 \\
  1 & -1 & 0
  \end{array}\right]
  \xrightarrow{R_2 \leftarrow R_2 - R_1}
  \left[\begin{array}{cc|c}
  \boxed{1} & 1 & 2 \\
  0 & \boxed{-2} & -2
  \end{array}\right].$$
- **Classification and Justification:**
  **Exactly one solution.**
  We stop elimination here: the row echelon form has a nonzero pivot in every column of $A$ ($1$ in Column 1 and $-2 \ne 0$ in Column 2). Because $\operatorname{rank}(A) = \operatorname{rank}([A \mid b]) = 2$ equals the number of unknowns $n = 2$, there are no free variables and no contradictory rows; back-substitution uniquely determines $y$ from $-2y = -2$ and then $x$ from $x + y = 2$.

---

### System 2: $\begin{cases}x+y=2,\\2x+2y=4\end{cases}$

- **Minimal Elimination Step:**
  Set up the augmented matrix and apply $R_2 \leftarrow R_2 - 2R_1$:
  $$\left[\begin{array}{cc|c}
  1 & 1 & 2 \\
  2 & 2 & 4
  \end{array}\right]
  \xrightarrow{R_2 \leftarrow R_2 - 2R_1}
  \left[\begin{array}{cc|c}
  \boxed{1} & 1 & 2 \\
  0 & 0 & 0
  \end{array}\right].$$
- **Classification and Justification:**
  **Infinitely many solutions.**
  The second row reduces completely to $[0 \;\; 0 \mid 0]$, which represents the identity $0 = 0$. Therefore, the system is consistent ($\operatorname{rank}(A) = \operatorname{rank}([A \mid b]) = 1$), but only Column 1 ($x$) has a pivot while Column 2 ($y$) has no pivot. Since there is $n - \operatorname{rank}(A) = 2 - 1 = 1$ free variable ($y = t \in \mathbb{R}$), the system has infinitely many solutions $(x, y) = (2 - t, t)$.

---

### System 3: $\begin{cases}x+y=2,\\2x+2y=5\end{cases}$

- **Minimal Elimination Step:**
  Set up the augmented matrix and apply $R_2 \leftarrow R_2 - 2R_1$:
  $$\left[\begin{array}{cc|c}
  1 & 1 & 2 \\
  2 & 2 & 5
  \end{array}\right]
  \xrightarrow{R_2 \leftarrow R_2 - 2R_1}
  \left[\begin{array}{cc|c}
  \boxed{1} & 1 & 2 \\
  0 & 0 & 1
  \end{array}\right].$$
- **Classification and Justification:**
  **No solution (inconsistent).**
  The second row reduces to $[0 \;\; 0 \mid 1]$, which corresponds to the impossible equation $0x + 0y = 1 \iff 0 = 1$. Because a row of zeros in the coefficient matrix is paired with a nonzero entry on the right-hand side ($\operatorname{rank}(A) = 1 < 2 = \operatorname{rank}([A \mid b])$), no pair $(x, y)$ can satisfy both equations.

---

## 4. Verification and Consistency Checks
We can verify all three classifications both algebraically and geometrically:
1. **System 1:** Solving $-2y = -2 \implies y = 1$ and $x = 2 - 1 = 1$ gives the unique intersection point $(1, 1)$ of the two perpendicular lines $y = -x + 2$ (slope $-1$) and $y = x$ (slope $+1$). Checking in the system: $1 + 1 = 2$ and $1 - 1 = 0$. $\checkmark$
2. **System 2:** Dividing the second equation $2x + 2y = 4$ by $2$ gives $x + y = 2$, which is identical to the first equation (two coincident lines). Every point $(2 - t, t)$ for $t \in \mathbb{R}$ satisfies $2(2 - t) + 2t = 4$. $\checkmark$
3. **System 3:** Dividing the second equation $2x + 2y = 5$ by $2$ gives $x + y = 2.5$, which contradicts the first equation $x + y = 2$ (two parallel, non-intersecting lines with slope $-1$ and different $y$-intercepts $2 \ne 2.5$). $\checkmark$
