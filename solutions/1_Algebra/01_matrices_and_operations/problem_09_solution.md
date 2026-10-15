# Solution to Exercise 9: Composing Transformations

## 1. Problem Statement

Let:
$$S = \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix}, \qquad R = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}, \qquad x = \begin{pmatrix} 1 \\ 2 \end{pmatrix}$$

The matrix $S$ describes nonuniform scaling (horizontal stretch by a factor of $2$), while $R$ describes a counterclockwise rotation by $90^\circ$.

1. Compute $RSx$.
2. Compute $SRx$.
3. Compare the results.
4. Explain geometrically why the order of these two transformations matters.

---

## 2. Theoretical Background and Concepts

### Linear Transformations and Matrix Composition
A matrix $M \in \mathbb{R}^{2 \times 2}$ represents a linear map $T_M: \mathbb{R}^2 \to \mathbb{R}^2$ sending $v \mapsto Mv$.
When two linear transformations are composed, say $T_1$ followed by $T_2$:
$$(T_2 \circ T_1)(x) = T_2(T_1(x)) = M_2 (M_1 x) = (M_2 M_1) x$$
Notice that matrix multiplication works from right to left: the matrix closest to the vector acts first.

### Nonuniform Scaling and Rotation
- **Scaling $S$:** Doubles the $x$-coordinate while leaving the $y$-coordinate unchanged:
  $$\begin{pmatrix} x \\ y \end{pmatrix} \mapsto \begin{pmatrix} 2x \\ y \end{pmatrix}$$
- **Rotation $R$ ($90^\circ$ CCW):** Maps the positive $x$-axis to the positive $y$-axis, and the positive $y$-axis to the negative $x$-axis:
  $$\begin{pmatrix} x \\ y \end{pmatrix} \mapsto \begin{pmatrix} -y \\ x \end{pmatrix}$$

Because $S$ acts anisotropically (differently along the $x$ and $y$ directions), rotating the plane changes which geometric features align with the axis of stretching. Consequently, the transformations do not commute.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Compute $RSx$ (Scale first, then Rotate)
First, apply $S$ to vector $x$:
$$Sx = \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 \\ 2 \end{pmatrix} = \begin{pmatrix} 2 \cdot 1 + 0 \cdot 2 \\ 0 \cdot 1 + 1 \cdot 2 \end{pmatrix} = \begin{pmatrix} 2 \\ 2 \end{pmatrix}$$

Next, apply $R$ to the resulting vector $Sx$:
$$RSx = R(Sx) = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 2 \\ 2 \end{pmatrix} = \begin{pmatrix} 0 \cdot 2 + (-1) \cdot 2 \\ 1 \cdot 2 + 0 \cdot 2 \end{pmatrix} = \begin{pmatrix} -2 \\ 2 \end{pmatrix}$$

---

### Step 2: Compute $SRx$ (Rotate first, then Scale)
First, apply $R$ to vector $x$:
$$Rx = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 1 \\ 2 \end{pmatrix} = \begin{pmatrix} 0 \cdot 1 + (-1) \cdot 2 \\ 1 \cdot 1 + 0 \cdot 2 \end{pmatrix} = \begin{pmatrix} -2 \\ 1 \end{pmatrix}$$

Next, apply $S$ to the resulting vector $Rx$:
$$SRx = S(Rx) = \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} -2 \\ 1 \end{pmatrix} = \begin{pmatrix} 2 \cdot (-2) + 0 \cdot 1 \\ 0 \cdot (-2) + 1 \cdot 1 \end{pmatrix} = \begin{pmatrix} -4 \\ 1 \end{pmatrix}$$

---

### Step 3: Comparison
Comparing the two final vectors:
$$RSx = \begin{pmatrix} -2 \\ 2 \end{pmatrix} \qquad \text{and} \qquad SRx = \begin{pmatrix} -4 \\ 1 \end{pmatrix}$$
Clearly:
$$RSx \ne SRx$$

---

### Step 4: Geometric Interpretation
- In the sequence $RSx$ (**Scale, then Rotate**):
  1. The initial vector $(1, 2)$ is stretched along the $x$-axis to $(2, 2)$.
  2. Rotating $(2, 2)$ by $90^\circ$ counterclockwise swings the newly stretched horizontal component into the vertical direction, producing $(-2, 2)$. The stretched component now lies along the $y$-axis.

- In the sequence $SRx$ (**Rotate, then Scale**):
  1. The initial vector $(1, 2)$ is rotated by $90^\circ$ counterclockwise to $(-2, 1)$. Here, the original $y$-component ($2$) has become the new $x$-component ($-2$).
  2. The scaling matrix $S$ then acts on the new horizontal coordinate, doubling $-2$ to $-4$, while leaving $1$ unchanged, yielding $(-4, 1)$.

**Conclusion:** 
Because nonuniform scaling operates strictly along fixed spatial coordinate axes (the $x$-axis), changing the orientation of the vector *prior* to scaling subjects a completely different coordinate component to the expansion. Thus, geometric transformation composition is inherently non-commutative.

---

## 4. Verification and Consistency Checks

1. **Composite Matrix Verification:**
   We compute the composite matrices directly and multiply by $x$:
   $$RS = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 0 \cdot 2 + (-1) \cdot 0 & 0 \cdot 0 + (-1) \cdot 1 \\ 1 \cdot 2 + 0 \cdot 0 & 1 \cdot 0 + 0 \cdot 1 \end{pmatrix} = \begin{pmatrix} 0 & -1 \\ 2 & 0 \end{pmatrix}$$
   $$(RS)x = \begin{pmatrix} 0 & -1 \\ 2 & 0 \end{pmatrix} \begin{pmatrix} 1 \\ 2 \end{pmatrix} = \begin{pmatrix} 0(1) - 1(2) \\ 2(1) + 0(2) \end{pmatrix} = \begin{pmatrix} -2 \\ 2 \end{pmatrix} \quad \checkmark$$

   $$SR = \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} 2 \cdot 0 + 0 \cdot 1 & 2 \cdot (-1) + 0 \cdot 0 \\ 0 \cdot 0 + 1 \cdot 1 & 0 \cdot (-1) + 1 \cdot 0 \end{pmatrix} = \begin{pmatrix} 0 & -2 \\ 1 & 0 \end{pmatrix}$$
   $$(SR)x = \begin{pmatrix} 0 & -2 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 1 \\ 2 \end{pmatrix} = \begin{pmatrix} 0(1) - 2(2) \\ 1(1) + 0(2) \end{pmatrix} = \begin{pmatrix} -4 \\ 1 \end{pmatrix} \quad \checkmark$$

2. **Area / Determinant Check:**
   - $\det(S) = 2 \cdot 1 - 0 \cdot 0 = 2$ (area scales by 2).
   - $\det(R) = 0 \cdot 0 - (-1) \cdot 1 = 1$ (area is preserved under rotation).
   - $\det(RS) = \det(R)\det(S) = 1 \cdot 2 = 2$.
   - $\det(SR) = \det(S)\det(R) = 2 \cdot 1 = 2$.
   Both composite transformations scale signed area by the factor $2$, consistent with theory.

