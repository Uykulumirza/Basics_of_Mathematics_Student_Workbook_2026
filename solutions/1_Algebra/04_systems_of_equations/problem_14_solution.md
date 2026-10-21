# Exercise 14: A Small Change in the Right-Hand Side

## 1. Problem Statement
Compare the systems
$$\begin{cases}x+y=2,\\2x-y=1,\\3x=3\end{cases}$$
and
$$\begin{cases}x+y=2,\\2x-y=1,\\3x=3.1.\end{cases}$$
Check the consistency of each system and explain why a small change in one number can change the type of the system.

---

## 2. Theoretical Background and Concepts
A system with more equations than unknowns ($m > n$, here $m = 3$ equations in $n = 2$ unknowns $x, y$) is called **overdetermined**.
- **Algebraically:** In $\mathbb{R}^2$, two independent linear equations already lock in a unique point $(x, y)$. For the entire $3\times 2$ system to be **consistent**, the third equation must be satisfied by that exact same point—meaning that the right-hand side vector $b \in \mathbb{R}^3$ must satisfy the exact compatibility relation inherited from the linear dependence of the rows of $A$ (i.e., $b$ must lie in the $2$-dimensional column space of $A$, so $\operatorname{rank}(A) = \operatorname{rank}([A \mid b]) = 2$).
- **Geometrically:** Three lines in a plane generically intersect pairwise at three different points (forming a triangle). Only when all three lines are **concurrent** (pass through the exact same common intersection point) does a simultaneous solution exist. Perturbing the constant term of the third line translates it slightly off the intersection point of the first two lines, immediately destroying concurrency.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Analyze Both Systems Simultaneously via Elimination
Observe that in both systems, adding the left-hand sides of the first two equations ($E_1 + E_2$) directly gives the left-hand side of the third equation ($E_3$):
$$(x + y) + (2x - y) = 3x.$$
Let us perform Gaussian elimination on both augmented matrices side-by-side:

#### System 1: $\begin{cases}x+y=2,\\2x-y=1,\\3x=3\end{cases}$
$$\left[\begin{array}{cc|c}
1 & 1 & 2 \\
2 & -1 & 1 \\
3 & 0 & 3
\end{array}\right]
\xrightarrow{\substack{R_2 \leftarrow R_2 - 2R_1 \\ R_3 \leftarrow R_3 - 3R_1}}
\left[\begin{array}{cc|c}
1 & 1 & 2 \\
0 & -3 & -3 \\
0 & -3 & -3
\end{array}\right]
\xrightarrow{R_3 \leftarrow R_3 - R_2}
\left[\begin{array}{cc|c}
1 & 1 & 2 \\
0 & -3 & -3 \\
0 & 0 & 0
\end{array}\right].$$
- The third row reduces to $[0 \;\; 0 \mid 0]$ ($0 = 0$). Thus, $\operatorname{rank}(A) = \operatorname{rank}([A \mid b_1]) = 2 = n$.
- **System 1 is consistent and has a unique solution:**
  From Row 2: $-3y = -3 \implies y = 1$.
  From Row 1: $x + 1 = 2 \implies x = 1$.
  So $(x, y) = (1, 1)$.

#### System 2: $\begin{cases}x+y=2,\\2x-y=1,\\3x=3.1\end{cases}$
$$\left[\begin{array}{cc|c}
1 & 1 & 2 \\
2 & -1 & 1 \\
3 & 0 & 3.1
\end{array}\right]
\xrightarrow{\substack{R_2 \leftarrow R_2 - 2R_1 \\ R_3 \leftarrow R_3 - 3R_1}}
\left[\begin{array}{cc|c}
1 & 1 & 2 \\
0 & -3 & -3 \\
0 & -3 & -2.9
\end{array}\right]
\xrightarrow{R_3 \leftarrow R_3 - R_2}
\left[\begin{array}{cc|c}
1 & 1 & 2 \\
0 & -3 & -3 \\
0 & 0 & 0.1
\end{array}\right].$$
- The third row reduces to $[0 \;\; 0 \mid 0.1]$, which represents the contradiction $0x + 0y = 0.1 \iff 0 = 0.1$.
- Here $\operatorname{rank}(A) = 2 < 3 = \operatorname{rank}([A \mid b_2])$.
- **System 2 is inconsistent and has no solution.**

---

### Step 2: Explain why a small change in one number changes the type of the system
1. **Exact Algebraic Compatibility Condition:**
   Because the left-hand side of Equation 3 equals the sum of the left-hand sides of Equations 1 and 2 ($L_3 = L_1 + L_2$), any pair $(x, y)$ that satisfies the first two equations ($x + y = 2$ and $2x - y = 1$) **must** satisfy their sum:
   $$3x = (x + y) + (2x - y) = 2 + 1 = 3.$$
   There is zero flexibility in the value of $3x$: it is locked at $3$.
   - In **System 1**, the third equation asks for $3x = 3$, which agrees completely with $E_1 + E_2$, making Equation 3 redundant and keeping the system consistent.
   - In **System 2**, changing $3$ to $3.1$ demands $3x = 3.1$ while the first two equations force $3x = 3$, creating an immediate contradiction $3 = 3.1$ ($0 = 0.1$). Even an arbitrarily small perturbation $3 + \varepsilon$ with $\varepsilon \ne 0$ breaks the exact equality $b_3 = b_1 + b_2$.

2. **Geometric Explanation (Three Lines in $\mathbb{R}^2$):**
   The first two equations define two non-parallel lines $\ell_1: x + y = 2$ and $\ell_2: 2x - y = 1$, which intersect at the single point $P = (1, 1)$.
   - In **System 1**, the third line $\ell_3: x = 1$ ($3x = 3$) passes directly through $P = (1, 1)$, so all three lines are **concurrent** at $(1, 1)$.
   - In **System 2**, changing $3$ to $3.1$ shifts the vertical line slightly to the right to $\ell_3': x = \frac{3.1}{3} = 1.0333\dots$, which **misses** the intersection point $P = (1, 1)$ of the first two lines. Because there is no longer a single point lying on all three lines simultaneously, the system becomes inconsistent.

---

## 4. Verification and Consistency Checks
We verify by substituting the unique intersection point $(x, y) = (1, 1)$ of the first two equations into all equations of both systems:
- **Equation 1:** $1 + 1 = 2$. $\checkmark$
- **Equation 2:** $2(1) - 1 = 1$. $\checkmark$
- **Equation 3 of System 1:** $3(1) = 3$ (matches RHS $= 3$, so $(1, 1)$ is a valid solution of System 1). $\checkmark$
- **Equation 3 of System 2:** $3(1) = 3 \ne 3.1$ (fails RHS $= 3.1$, confirming System 2 has no solution). $\checkmark$
