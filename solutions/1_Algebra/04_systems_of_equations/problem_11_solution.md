# Exercise 11: A Parameter in a System of Three Equations

## 1. Problem Statement
Analyze the number of solutions depending on $t$:
$$\begin{cases}x+y+z=1,\\x+ty+z=2,\\x+y+tz=3.\end{cases}$$
Use elimination and separately analyze the parameter values for which a standard calculation step ceases to be valid.

---

## 2. Theoretical Background and Concepts
When solving a linear system containing a parameter $t \in \mathbb{R}$ via Gaussian elimination:
- **Row addition operations** of the form $R_i \leftarrow R_i + c(t) R_j$ are valid for **every** $t \in \mathbb{R}$.
- **Row scaling / division operations** of the form $R_i \leftarrow \frac{1}{f(t)} R_i$ (or dividing by a pivot expression $f(t)$ during back-substitution) are valid **if and only if $f(t) \ne 0$**.

Whenever a pivot depends on the parameter $t$, we must split the analysis into branches:
1. The **generic branch** where $f(t) \ne 0$ and division is permissible,
2. The **critical (singular) branch(es)** where $f(t) = 0$, which must be analyzed by substituting the critical value of $t$ directly into the echelon matrix before any division takes place.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Perform Gaussian elimination without dividing by expressions in $t$
We write the augmented matrix of the system:
$$[A \mid b] = \left[\begin{array}{ccc|c}
1 & 1 & 1 & 1 \\
1 & t & 1 & 2 \\
1 & 1 & t & 3
\end{array}\right].$$

The first pivot is $a_{11} = 1$ (a nonzero constant independent of $t$). We eliminate $x$ from Row 2 and Row 3 using the elementary row operations:
- $R_2 \leftarrow R_2 - R_1$: $(1, t, 1 \mid 2) - (1, 1, 1 \mid 1) = (0, t - 1, 0 \mid 1)$,
- $R_3 \leftarrow R_3 - R_1$: $(1, 1, t \mid 3) - (1, 1, 1 \mid 1) = (0, 0, t - 1 \mid 2)$.

Because these operations only subtract $1\cdot R_1$, they are valid for **all** $t \in \mathbb{R}$. The augmented matrix is already in upper-triangular form:
$$\left[\begin{array}{ccc|c}
1 & 1 & 1 & 1 \\
0 & t - 1 & 0 & 1 \\
0 & 0 & t - 1 & 2
\end{array}\right],$$
which corresponds to the reduced system:
$$\begin{cases}
x + y + z = 1, \\
(t - 1)y = 1, \\
(t - 1)z = 2.
\end{cases}$$

### Step 2: Identify when the standard calculation step ceases to be valid
To solve the second and third equations for $y$ and $z$, the standard back-substitution step requires **dividing both sides by $t - 1$** (equivalently, scaling Rows 2 and 3 by $\frac{1}{t - 1}$). Division by $t - 1$ ceases to be valid precisely when:
$$t - 1 = 0 \iff t = 1.$$
Therefore, we must analyze $t = 1$ and $t \ne 1$ separately.

### Step 3: Case 1 — $t = 1$ (Singular Case: No Solution)
Substituting $t = 1$ into the reduced augmented matrix gives:
$$\left[\begin{array}{ccc|c}
1 & 1 & 1 & 1 \\
0 & 0 & 0 & 1 \\
0 & 0 & 0 & 2
\end{array}\right].$$
Rows 2 and 3 translate to the contradictory equations:
$$0y = 1 \iff 0 = 1 \quad \text{and} \quad 0z = 2 \iff 0 = 2.$$
*(Indeed, in the original system, setting $t = 1$ makes all three left-hand sides equal to $x + y + z$, requiring $x + y + z$ to equal $1$, $2$, and $3$ simultaneously.)*
Here $\operatorname{rank}(A) = 1 < 2 = \operatorname{rank}([A \mid b])$, so for $t = 1$ the system is **inconsistent** and has **no solution**.

### Step 4: Case 2 — $t \ne 1$ (Non-Singular Case: Unique Solution)
When $t \ne 1$, we have $t - 1 \ne 0$, so both diagonal entries $t - 1$ in Rows 2 and 3 are nonzero pivots ($\operatorname{rank}(A) = \operatorname{rank}([A \mid b]) = 3$). Dividing by $t - 1$ is valid and yields:
1. From Row 3:
   $$(t - 1)z = 2 \implies z = \frac{2}{t - 1}.$$
2. From Row 2:
   $$(t - 1)y = 1 \implies y = \frac{1}{t - 1}.$$
3. Substituting $y$ and $z$ into Row 1 ($x + y + z = 1$):
   $$x = 1 - y - z = 1 - \frac{1}{t - 1} - \frac{2}{t - 1} = 1 - \frac{3}{t - 1} = \frac{(t - 1) - 3}{t - 1} = \frac{t - 4}{t - 1}.$$

Thus, for every $t \in \mathbb{R} \setminus \{1\}$, the system has **exactly one (unique) solution**:
$$(x, y, z) = \left(\frac{t - 4}{t - 1}, \; \frac{1}{t - 1}, \; \frac{2}{t - 1}\right).$$

### Summary of Classification
- **For $t = 1$:** **No solution** (inconsistent system).
- **For $t \ne 1$:** **Exactly one solution**, $(x, y, z) = \left(\frac{t - 4}{t - 1}, \frac{1}{t - 1}, \frac{2}{t - 1}\right)$.
- **Infinitely many solutions:** **Never occurs** for any $t \in \mathbb{R}$.

---

## 4. Verification and Consistency Checks
For $t \ne 1$, let us substitute $(x, y, z) = \left(\frac{t - 4}{t - 1}, \frac{1}{t - 1}, \frac{2}{t - 1}\right)$ into all three original equations:
1. **Equation 1:**
   $$x + y + z = \frac{(t - 4) + 1 + 2}{t - 1} = \frac{t - 1}{t - 1} = 1 \quad (\text{matches RHS } = 1). \quad \checkmark$$
2. **Equation 2:**
   $$x + ty + z = \frac{(t - 4) + t(1) + 2}{t - 1} = \frac{2t - 2}{t - 1} = \frac{2(t - 1)}{t - 1} = 2 \quad (\text{matches RHS } = 2). \quad \checkmark$$
3. **Equation 3:**
   $$x + y + tz = \frac{(t - 4) + 1 + t(2)}{t - 1} = \frac{3t - 3}{t - 1} = \frac{3(t - 1)}{t - 1} = 3 \quad (\text{matches RHS } = 3). \quad \checkmark$$

Also, $\det(A) = (t - 1)^2$, which confirms that $A$ is invertible if and only if $t \ne 1$.
