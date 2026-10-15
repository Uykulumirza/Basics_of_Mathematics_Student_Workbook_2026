# Solution to Exercise 14: Rotation Matrices

## 1. Problem Statement

The matrix for a counterclockwise rotation through an angle $\theta$ in the Cartesian plane is given by:
$$R(\theta) = \begin{pmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{pmatrix}$$

1. Compute the matrix product $R(\alpha) R(\beta)$ for two arbitrary angles $\alpha, \beta \in \mathbb{R}$.
2. Using the angle-sum trigonometric identities for sine and cosine, show that:
   $$R(\alpha) R(\beta) = R(\alpha + \beta)$$
3. Explain the result geometrically.

---

## 2. Theoretical Background and Concepts

### Rotation in $\mathbb{R}^2$
A rotation by an angle $\theta$ counterclockwise about the origin maps the standard basis vectors as follows:
- $e_1 = \begin{pmatrix} 1 \\ 0 \end{pmatrix} \mapsto \begin{pmatrix} \cos\theta \\ \sin\theta \end{pmatrix}$
- $e_2 = \begin{pmatrix} 0 \\ 1 \end{pmatrix} \mapsto \begin{pmatrix} -\sin\theta \\ \cos\theta \end{pmatrix}$

Assembling these image vectors as columns yields the rotation matrix $R(\theta)$.

### Trigonometric Angle-Sum Identities
For any two angles $\alpha, \beta \in \mathbb{R}$:
$$\cos(\alpha + \beta) = \cos\alpha \cos\beta - \sin\alpha \sin\beta$$
$$\sin(\alpha + \beta) = \sin\alpha \cos\beta + \cos\alpha \sin\beta$$

### Group Structure of Rotations: $\mathrm{SO}(2)$
The set of all $2 \times 2$ rotation matrices forms the **Special Orthogonal Group** $\mathrm{SO}(2)$:
- Every rotation matrix is orthogonal: $R(\theta)^T = R(\theta)^{-1} = R(-\theta)$.
- The determinant is $\det(R(\theta)) = \cos^2\theta + \sin^2\theta = 1$ (preserves area and orientation).
- Because addition of real angles is commutative ($\alpha + \beta = \beta + \alpha$), 2D rotations commute: $R(\alpha)R(\beta) = R(\beta)R(\alpha)$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Set Up and Compute $R(\alpha) R(\beta)$
Write out the matrices:
$$R(\alpha) = \begin{pmatrix} \cos\alpha & -\sin\alpha \\ \sin\alpha & \cos\alpha \end{pmatrix}, \qquad R(\beta) = \begin{pmatrix} \cos\beta & -\sin\beta \\ \sin\beta & \cos\beta \end{pmatrix}$$

Multiply using standard row-by-column multiplication:
$$R(\alpha) R(\beta) = \begin{pmatrix} \cos\alpha & -\sin\alpha \\ \sin\alpha & \cos\alpha \end{pmatrix} \begin{pmatrix} \cos\beta & -\sin\beta \\ \sin\beta & \cos\beta \end{pmatrix}$$

We compute each of the four entries:

- **Row 1, Column 1:**
  $$\left(R(\alpha) R(\beta)\right)_{11} = (\cos\alpha)(\cos\beta) + (-\sin\alpha)(\sin\beta) = \cos\alpha \cos\beta - \sin\alpha \sin\beta$$

- **Row 1, Column 2:**
  $$\left(R(\alpha) R(\beta)\right)_{12} = (\cos\alpha)(-\sin\beta) + (-\sin\alpha)(\cos\beta) = -(\sin\alpha \cos\beta + \cos\alpha \sin\beta)$$

- **Row 2, Column 1:**
  $$\left(R(\alpha) R(\beta)\right)_{21} = (\sin\alpha)(\cos\beta) + (\cos\alpha)(\sin\beta) = \sin\alpha \cos\beta + \cos\alpha \sin\beta$$

- **Row 2, Column 2:**
  $$\left(R(\alpha) R(\beta)\right)_{22} = (\sin\alpha)(-\sin\beta) + (\cos\alpha)(\cos\beta) = \cos\alpha \cos\beta - \sin\alpha \sin\beta$$

---

### Step 2: Apply Trigonometric Identities
Using the angle-sum identities:
1. $\cos\alpha \cos\beta - \sin\alpha \sin\beta = \cos(\alpha + \beta)$
2. $\sin\alpha \cos\beta + \cos\alpha \sin\beta = \sin(\alpha + \beta)$

Substitute these expressions back into the entries:
- Entry $(1, 1) = \cos(\alpha + \beta)$
- Entry $(1, 2) = -\sin(\alpha + \beta)$
- Entry $(2, 1) = \sin(\alpha + \beta)$
- Entry $(2, 2) = \cos(\alpha + \beta)$

Assembling the matrix:
$$R(\alpha) R(\beta) = \begin{pmatrix} \cos(\alpha + \beta) & -\sin(\alpha + \beta) \\ \sin(\alpha + \beta) & \cos(\alpha + \beta) \end{pmatrix} = R(\alpha + \beta)$$
$\blacksquare$

---

### Step 3: Geometric Explanation
- Applying the transformation $R(\beta)$ to a vector $v \in \mathbb{R}^2$ rotates that vector counterclockwise around the origin by an angle $\beta$.
- Then, applying the transformation $R(\alpha)$ to the resulting vector rotates it further counterclockwise by an additional angle $\alpha$ around the exact same center of rotation (the origin).
- Geometrically, rotating sequentially by $\beta$ and then by $\alpha$ about a single fixed point is completely equivalent to performing a single unified rotation by the total accumulated angle $\alpha + \beta$.
- In addition, because scalar addition is commutative ($\alpha + \beta = \beta + \alpha$), we have $R(\alpha)R(\beta) = R(\alpha+\beta) = R(\beta+\alpha) = R(\beta)R(\alpha)$. Thus, unlike general matrices, **2D rotations about the origin always commute**.

---

## 4. Verification and Consistency Checks

1. **Specific Angle Test ($\alpha = 90^\circ = \frac{\pi}{2}$, $\beta = 90^\circ = \frac{\pi}{2}$):**
   - $R\left(\frac{\pi}{2}\right) = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}$
   - Compute $R\left(\frac{\pi}{2}\right) R\left(\frac{\pi}{2}\right)$:
     $$\begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} = \begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix} = -I$$
   - Using the theorem:
     $$R\left(\frac{\pi}{2} + \frac{\pi}{2}\right) = R(\pi) = \begin{pmatrix} \cos\pi & -\sin\pi \\ \sin\pi & \cos\pi \end{pmatrix} = \begin{pmatrix} -1 & 0 \\ 0 & -1 \end{pmatrix} = -I \quad \checkmark$$

2. **Inverse / Identity Check ($\beta = -\alpha$):**
   $$R(\alpha) R(-\alpha) = R(\alpha + (-\alpha)) = R(0) = \begin{pmatrix} \cos 0 & -\sin 0 \\ \sin 0 & \cos 0 \end{pmatrix} = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = I$$
   This proves that $R(-\alpha) = R(\alpha)^{-1}$, confirming that rotating in reverse cancels the initial rotation.

3. **Determinant Multiplicativity Check:**
   $$\det(R(\alpha)) = \cos^2\alpha + \sin^2\alpha = 1, \qquad \det(R(\beta)) = \cos^2\beta + \sin^2\beta = 1$$
   $$\det(R(\alpha)R(\beta)) = \det(R(\alpha))\det(R(\beta)) = 1 \cdot 1 = 1 = \det(R(\alpha+\beta)) \quad \checkmark$$

