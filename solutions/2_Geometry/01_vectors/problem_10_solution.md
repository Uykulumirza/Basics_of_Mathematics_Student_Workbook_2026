# Solution: Exercise 10 — Triangle Area from Vectors

## 1. Problem Statement
The points $A=(0,0,0)$, $B=(2,1,0)$, and $C=(1,3,2)$ form a triangle. Construct $\overrightarrow{AB}$ and $\overrightarrow{AC}$, compute the area of the parallelogram using the cross product, and then find the area of the triangle. Explain the factor $\frac12$.

---

## 2. Theoretical Background and Concepts
Given two vectors $u = \overrightarrow{AB}$ and $v = \overrightarrow{AC}$ anchored at a common vertex $A$ in $\mathbb{R}^3$ with angle $\theta \in [0, \pi]$ between them:
- **Magnitude of the Cross Product and Parallelogram Area:** The length of the cross product equals:
  $$\|\overrightarrow{AB} \times \overrightarrow{AC}\| = \|\overrightarrow{AB}\|\,\|\overrightarrow{AC}\|\sin\theta.$$
  Since $\|\overrightarrow{AB}\|$ is the base of the parallelogram spanned by $\overrightarrow{AB}$ and $\overrightarrow{AC}$ and $h = \|\overrightarrow{AC}\|\sin\theta$ is the perpendicular height of that parallelogram, the norm $\|\overrightarrow{AB} \times \overrightarrow{AC}\|$ equals the **area of the parallelogram**:
  $$\text{Area}_{\text{parallelogram}} = \|\overrightarrow{AB} \times \overrightarrow{AC}\|.$$
- **Area of the Triangle:** Because triangle $ABC$ occupies half of the parallelogram spanned by $\overrightarrow{AB}$ and $\overrightarrow{AC}$, its area is:
  $$\text{Area}_{\triangle ABC} = \frac{1}{2}\|\overrightarrow{AB} \times \overrightarrow{AC}\|.$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Construct $\overrightarrow{AB}$ and $\overrightarrow{AC}$
Subtracting the coordinates of $A = (0, 0, 0)$ from $B = (2, 1, 0)$ and $C = (1, 3, 2)$:
$$\overrightarrow{AB} = B - A = (2 - 0,\; 1 - 0,\; 0 - 0) = (2, 1, 0),$$
$$\overrightarrow{AC} = C - A = (1 - 0,\; 3 - 0,\; 2 - 0) = (1, 3, 2).$$

### Step 2: Compute $\overrightarrow{AB} \times \overrightarrow{AC}$ and the area of the parallelogram
Evaluating the cross product:
$$\overrightarrow{AB} \times \overrightarrow{AC} = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 2 & 1 & 0 \\ 1 & 3 & 2 \end{vmatrix} = \big((1)(2) - (0)(3),\; -[(2)(2) - (0)(1)],\; (2)(3) - (1)(1)\big) = (2, -4, 5).$$
The area of the parallelogram spanned by $\overrightarrow{AB}$ and $\overrightarrow{AC}$ is the Euclidean length of this cross product:
$$\text{Area}_{\text{parallelogram}} = \|\overrightarrow{AB} \times \overrightarrow{AC}\| = \sqrt{2^2 + (-4)^2 + 5^2} = \sqrt{4 + 16 + 25} = \sqrt{45} = 3\sqrt{5} \approx 6.7082.$$

### Step 3: Compute the area of triangle $ABC$
Dividing the parallelogram area by $2$ gives the area of $\triangle ABC$:
$$\text{Area}_{\triangle ABC} = \frac{1}{2}\|\overrightarrow{AB} \times \overrightarrow{AC}\| = \frac{\sqrt{45}}{2} = \frac{3\sqrt{5}}{2} \approx 3.3541.$$

### Step 4: Explain the factor $\frac{1}{2}$ geometrically
The vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$ placed tail-to-tail at $A$ define a parallelogram $ABDC$ (where $D = A + \overrightarrow{AB} + \overrightarrow{AC} = (3, 4, 2)$). The third side of triangle $ABC$ is the segment $BC$, which is a **diagonal** of the parallelogram $ABDC$. 

A diagonal divides any parallelogram into two **congruent** triangles ($\triangle ABC \cong \triangle DCB$ by Side-Side-Side congruence, since opposite sides of a parallelogram have equal length and they share the diagonal $BC$). Because the two congruent triangles have equal area and together partition the parallelogram, the area of $\triangle ABC$ is exactly **one-half** ($\frac{1}{2}$) the area of the parallelogram. Equivalently, in terms of base $b = \|\overrightarrow{AB}\|$ and height $h = \|\overrightarrow{AC}\|\sin\theta$, the parallelogram has area $b \cdot h$, whereas the triangle has area $\frac{1}{2} b \cdot h$.

---

## 4. Verification and Consistency Checks

### Orthogonality Check of $\overrightarrow{AB} \times \overrightarrow{AC} = (2, -4, 5)$
- $(2, -4, 5) \cdot \overrightarrow{AB} = (2)(2) + (-4)(1) + (5)(0) = 4 - 4 + 0 = 0$
- $(2, -4, 5) \cdot \overrightarrow{AC} = (2)(1) + (-4)(3) + (5)(2) = 2 - 12 + 10 = 0$

### Verification via Dot Product and $\sin^2\theta + \cos^2\theta = 1$
We can independently compute the area using $\text{Area}_{\triangle ABC} = \frac{1}{2}\sqrt{\|\overrightarrow{AB}\|^2\|\overrightarrow{AC}\|^2 - (\overrightarrow{AB} \cdot \overrightarrow{AC})^2}$:
- $\|\overrightarrow{AB}\|^2 = 2^2 + 1^2 + 0^2 = 5$
- $\|\overrightarrow{AC}\|^2 = 1^2 + 3^2 + 2^2 = 14$
- $\overrightarrow{AB} \cdot \overrightarrow{AC} = (2)(1) + (1)(3) + (0)(2) = 5$

Substituting these gives:
$$\text{Area}_{\triangle ABC} = \frac{1}{2}\sqrt{(5)(14) - 5^2} = \frac{1}{2}\sqrt{70 - 25} = \frac{\sqrt{45}}{2} = \frac{3\sqrt{5}}{2},$$
which matches our cross-product calculation identically.
