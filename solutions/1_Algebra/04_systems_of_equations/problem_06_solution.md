# Exercise 6: A System with a Parameter — Which Cases Actually Occur?

## 1. Problem Statement
Analyze, depending on the parameter $a$, the system
$$\begin{cases}x+y=2,\\ax+ay=4.\end{cases}$$

Among the three possibilities — exactly one solution, infinitely many solutions, no solution — determine which actually occur and for which values of $a$. If one type cannot occur, explain why.

---

## 2. Theoretical Background and Concepts
For a general linear system $Ax = b$ in $n$ unknowns, the Rouché–Capelli theorem classifies the solution set into three mutually exclusive cases:
1. **No solution (inconsistent):** $\operatorname{rank}(A) < \operatorname{rank}([A \mid b])$.
2. **Exactly one solution (unique):** $\operatorname{rank}(A) = \operatorname{rank}([A \mid b]) = n$.
3. **Infinitely many solutions:** $\operatorname{rank}(A) = \operatorname{rank}([A \mid b]) < n$.

When a system depends on a real parameter $a \in \mathbb{R}$, it is tempting to assume that all three cases must occur for different values of $a$. However, whether a given case can occur depends on whether $\operatorname{rank}(A)$ can ever reach $n$. For a $2\times 2$ coefficient matrix $A$, a unique solution requires $\operatorname{rank}(A) = 2 \iff \det(A) \ne 0$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Perform Gaussian elimination on the augmented matrix
We write the augmented matrix of the system for an arbitrary $a \in \mathbb{R}$:
$$[A \mid b] = \left[\begin{array}{cc|c}
1 & 1 & 2 \\
a & a & 4
\end{array}\right].$$

Using the pivot $a_{11} = 1$ in the first row, we eliminate $x$ from the second row via the elementary row operation $R_2 \leftarrow R_2 - aR_1$:
$$(a, a \mid 4) - a(1, 1 \mid 2) = (a - a, \, a - a \mid 4 - 2a) = (0, 0 \mid 4 - 2a).$$
Thus, for every $a \in \mathbb{R}$, the row echelon form of the augmented matrix is:
$$\left[\begin{array}{cc|c}
1 & 1 & 2 \\
0 & 0 & 4 - 2a
\end{array}\right].$$

### Step 2: Analyze the cases depending on the parameter $a$
The second row represents the equation:
$$0x + 0y = 4 - 2a \iff 0 = 4 - 2a.$$
The behavior of this equation depends entirely on whether the right-hand side $4 - 2a$ is zero or nonzero:

1. **Case 1: $4 - 2a = 0 \iff a = 2$ (Infinitely Many Solutions)**
   When $a = 2$, the augmented matrix becomes:
   $$\left[\begin{array}{cc|c}
   1 & 1 & 2 \\
   0 & 0 & 0
   \end{array}\right].$$
   Here $\operatorname{rank}(A) = \operatorname{rank}([A \mid b]) = 1 < 2$. The second equation $2x + 2y = 4$ is simply twice the first equation $x + y = 2$, so both equations describe the exact same line in $\mathbb{R}^2$. Setting the free variable $y = t \in \mathbb{R}$ yields **infinitely many solutions**:
   $$(x, y) = (2 - t, \, t), \quad t \in \mathbb{R}.$$

2. **Case 2: $4 - 2a \ne 0 \iff a \ne 2$ (No Solution)**
   When $a \ne 2$, the second row of the echelon matrix is $[0 \;\; 0 \mid 4 - 2a]$ with $4 - 2a \ne 0$, which translates to the contradiction:
   $$0 = 4 - 2a \ne 0.$$
   Here $\operatorname{rank}(A) = 1 < 2 = \operatorname{rank}([A \mid b])$. Thus, for every $a \in \mathbb{R} \setminus \{2\}$, the system is **inconsistent** and has **no solution**.
   *(Even for $a = 0$, the second equation reads $0x + 0y = 4$, which is still inconsistent.)*

### Step 3: Explain why the "Exactly One Solution" case NEVER occurs
The case of **exactly one solution** cannot occur for **any** real value of $a \in \mathbb{R}$ for three equivalent reasons:
- **Row Echelon / Pivot Perspective:** Regardless of the value of $a$, eliminating $x$ from the second equation simultaneously eliminates $y$ because the coefficients of $x$ and $y$ appear in the exact same $1:1$ ratio in both equations. Consequently, the second row of $A$ always becomes $[0 \;\; 0]$, leaving only $r = 1$ pivot for $n = 2$ unknowns.
- **Determinant / Rank Perspective:** A $2\times 2$ system has a unique solution if and only if $\det(A) \ne 0$. Here,
  $$\det(A) = \det\begin{bmatrix} 1 & 1 \\ a & a \end{bmatrix} = 1\cdot a - 1\cdot a = 0 \quad \text{for all } a \in \mathbb{R}.$$
  Because $\det(A)$ is identically zero for every $a$, $\operatorname{rank}(A) = 1 < 2$ for all $a$.
- **Geometric Perspective:** For $a \ne 0$, both equations $x + y = 2$ and $x + y = \frac{4}{a}$ represent straight lines with the same slope $m = -1$ (parallel normal vectors $(1,1)$ and $(a,a)$). Two lines with the same slope are either **coincident** (when $\frac{4}{a} = 2 \iff a = 2$, giving infinitely many intersection points) or **parallel and distinct** (when $a \ne 2$, giving zero intersection points). They can never cross at a single point.

---

## 4. Verification and Consistency Checks
Let us check representative values of $a$ directly in the original system $\begin{cases}x+y=2,\\ax+ay=4\end{cases}$:
- If $(x,y)$ satisfies the first equation, then $x + y = 2$.
- Substituting $x + y = 2$ directly into the factored left-hand side of the second equation gives:
  $$ax + ay = a(x + y) = a(2) = 2a.$$
- Therefore, the second equation $ax + ay = 4$ holds if and only if $2a = 4 \iff a = 2$, in which case every point on the line $x + y = 2$ satisfies both equations. If $a \ne 2$, $2a \ne 4$, so no point on $x + y = 2$ can ever satisfy the second equation.
