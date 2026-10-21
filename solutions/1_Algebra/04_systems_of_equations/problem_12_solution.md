# Exercise 12: Homogeneous System

## 1. Problem Statement
Solve
$$\begin{cases}x+2y-z=0,\\2x+4y-2z=0,\\x-y+2z=0.\end{cases}$$
Give all solutions in parametric form and explain why $(0,0,0)$ always satisfies a homogeneous system.

---

## 2. Theoretical Background and Concepts
A system of linear equations is called **homogeneous** if every constant term on the right-hand side is zero:
$$Ax = \mathbf{0}.$$
Unlike general systems $Ax = b$, a homogeneous system is **always consistent** because it is guaranteed to possess at least the **trivial solution** $x = \mathbf{0} = (0, 0, \dots, 0)^T$. Consequently, a homogeneous system in $n$ unknowns has only two possible outcomes:
1. **Unique (trivial) solution $x = \mathbf{0}$:** when $\operatorname{rank}(A) = n$ (no free variables).
2. **Infinitely many solutions (nontrivial solutions exist):** when $\operatorname{rank}(A) < n$, producing an $(n - \operatorname{rank}(A))$-dimensional subspace (the null space or kernel of $A$) that passes through the origin.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Explain why $(0, 0, 0)$ always satisfies a homogeneous system
- **Algebraic Explanation:**
  In any homogeneous linear equation $a_1 x + a_2 y + a_3 z = 0$, there is no constant term. Substituting $(x, y, z) = (0, 0, 0)$ into the left-hand side always yields:
  $$a_1(0) + a_2(0) + a_3(0) = 0 + 0 + 0 = 0,$$
  regardless of what the coefficients $a_1, a_2, a_3$ are. In matrix notation, multiplying any $m \times n$ matrix $A$ by the zero vector $\mathbf{0} \in \mathbb{R}^n$ always produces the zero vector $\mathbf{0} \in \mathbb{R}^m$: $A\mathbf{0} = \mathbf{0}$.
- **Geometric Explanation:**
  In $\mathbb{R}^3$, a linear equation $a_1 x + a_2 y + a_3 z = d$ represents a plane that passes through the origin $(0, 0, 0)$ if and only if $d = 0$. Since every equation in a homogeneous system has $d = 0$, every equation describes a plane through the origin; therefore, the origin $(0, 0, 0)$ automatically lies on their common intersection.

### Step 2: Set up the augmented matrix and apply Gaussian elimination
We write the augmented matrix $[A \mid \mathbf{0}]$ for the given system:
$$\left[\begin{array}{ccc|c}
1 & 2 & -1 & 0 \\
2 & 4 & -2 & 0 \\
1 & -1 & 2 & 0
\end{array}\right].$$

Using the pivot $a_{11} = 1$ in Row 1, we eliminate $x$ from Row 2 and Row 3:
- $R_2 \leftarrow R_2 - 2R_1$: $(2, 4, -2 \mid 0) - 2(1, 2, -1 \mid 0) = (0, 0, 0 \mid 0)$,
- $R_3 \leftarrow R_3 - R_1$: $(1, -1, 2 \mid 0) - (1, 2, -1 \mid 0) = (0, -3, 3 \mid 0)$.

This yields:
$$\left[\begin{array}{ccc|c}
1 & 2 & -1 & 0 \\
0 & 0 & 0 & 0 \\
0 & -3 & 3 & 0
\end{array}\right].$$

Swapping Row 2 and Row 3 ($R_2 \leftrightarrow R_3$) and dividing the new Row 2 by $-3$ ($R_2 \leftarrow -\frac{1}{3}R_2$) gives the row echelon form:
$$\left[\begin{array}{ccc|c}
1 & 2 & -1 & 0 \\
0 & 1 & -1 & 0 \\
0 & 0 & 0 & 0
\end{array}\right].$$

### Step 3: Identify the free variable and write the parametric solution
From the row echelon form:
- There are $r = \operatorname{rank}(A) = 2$ pivots, located in **Column 1** ($x$) and **Column 2** ($y$).
- **Column 3** ($z$) has no pivot, so there is $n - r = 3 - 2 = 1$ **free variable**, namely $z$.

Setting $z = t \in \mathbb{R}$ and using back-substitution:
1. From Row 2 ($y - z = 0$):
   $$y = z = t.$$
2. Substitute $y = t$ and $z = t$ into Row 1 ($x + 2y - z = 0$):
   $$x + 2t - t = 0 \implies x + t = 0 \implies x = -t.$$

Thus, the complete parametric solution set is:
$$\begin{cases}
x = -t, \\
y = t, \\
z = t,
\end{cases} \quad t \in \mathbb{R},$$
or in vector form:
$$\begin{bmatrix} x \\ y \\ z \end{bmatrix} = \begin{bmatrix} -t \\ t \\ t \end{bmatrix} = t \begin{bmatrix} -1 \\ 1 \\ 1 \end{bmatrix}, \quad t \in \mathbb{R}.$$
Geometrically, the solution set is the straight line through the origin $(0,0,0)$ directed along the vector $(-1, 1, 1)^T$ (notice that setting $t = 0$ recovers the trivial solution $(0,0,0)$).

---

## 4. Verification and Consistency Checks
We substitute $(x, y, z) = (-t, t, t)$ into all three original equations for an arbitrary $t \in \mathbb{R}$:
1. **First equation:**
   $$x + 2y - z = (-t) + 2(t) - t = 0 \quad (\text{matches RHS } = 0). \quad \checkmark$$
2. **Second equation:**
   $$2x + 4y - 2z = 2(-t) + 4(t) - 2(t) = 0 \quad (\text{matches RHS } = 0). \quad \checkmark$$
3. **Third equation:**
   $$x - y + 2z = (-t) - t + 2(t) = 0 \quad (\text{matches RHS } = 0). \quad \checkmark$$

All three equations are identically satisfied for all $t \in \mathbb{R}$.
