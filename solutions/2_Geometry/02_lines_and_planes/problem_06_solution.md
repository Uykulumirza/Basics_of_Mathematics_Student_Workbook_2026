# Exercise 6: Angle Between Planes — Solution

## 1. Problem Statement

Given
$$\Pi_1:x+y+z=1,\qquad \Pi_2:x-y=2.$$
First use the normal vectors to decide whether the planes are parallel. If not, compute the angle between them and explain why the normal vectors alone are enough for this calculation.

---

## 2. Theoretical Background and Concepts

Let two planes in $\mathbb{R}^3$ be given in general form:
$$\Pi_1: A_1 x + B_1 y + C_1 z = d_1, \qquad \Pi_2: A_2 x + B_2 y + C_2 z = d_2,$$
with respective normal vectors $n_1 = (A_1, B_1, C_1)$ and $n_2 = (A_2, B_2, C_2)$.

### 1. Parallelism of Planes via Normal Vectors
Because a plane's orientation in $\mathbb{R}^3$ is completely determined by its orthogonal complement (the normal line), two planes $\Pi_1$ and $\Pi_2$ are parallel ($\Pi_1 \parallel \Pi_2$) if and only if their normal vectors $n_1$ and $n_2$ are collinear (proportional):
$$\Pi_1 \parallel \Pi_2 \iff \exists \lambda \neq 0 \text{ such that } n_1 = \lambda n_2 \iff n_1 \times n_2 = \mathbf{0}.$$
If $n_1$ and $n_2$ are not proportional, the planes must intersect along a line.

### 2. Why Normal Vectors Alone Determine the Dihedral Angle
When two planes $\Pi_1$ and $\Pi_2$ intersect along a line $L$, the angle $\theta \in [0, \pi/2]$ between them (the acute dihedral angle) is measured in any plane $\Sigma$ perpendicular to the intersection line $L$.
Within this cross-sectional plane $\Sigma$:
- $\Pi_1 \cap \Sigma$ and $\Pi_2 \cap \Sigma$ are two intersecting lines meeting at angle $\theta$.
- The normal vectors $n_1$ and $n_2$ also lie in (or project full-length onto) $\Sigma$ because both $n_1$ and $n_2$ are perpendicular to $L$.
- Rotating two lines in a plane by $90^\circ$ preserves the angle between them (up to supplementary angles $\theta$ and $\pi - \theta$).

Therefore, the acute angle $\theta \in [0, \pi/2]$ between the planes $\Pi_1$ and $\Pi_2$ is equal to the acute angle between their normal lines:
$$\cos\theta = \frac{|n_1 \cdot n_2|}{\|n_1\|\,\|n_2\|}.$$
In particular, $\Pi_1 \perp \Pi_2 \iff n_1 \cdot n_2 = 0$. Notice that neither the constant terms $d_1, d_2$ nor the explicit parameterization of the intersection line $L$ are needed!

---

## 3. Detailed Step-by-Step Solution

### Step 1: Extract the Normal Vectors
Writing both plane equations with all three variables $(x, y, z)$ explicitly:
$$\Pi_1: 1x + 1y + 1z = 1 \implies n_1 = (1, 1, 1),$$
$$\Pi_2: 1x - 1y + 0z = 2 \implies n_2 = (1, -1, 0).$$

### Step 2: Check Whether the Planes Are Parallel
Two vectors $n_1 = (1, 1, 1)$ and $n_2 = (1, -1, 0)$ are parallel if and only if $n_1 = \lambda n_2$ for some scalar $\lambda \in \mathbb{R}$:
- Comparing the first components ($1 = \lambda \cdot 1$) requires $\lambda = 1$.
- Comparing the second components ($1 = \lambda \cdot (-1)$) requires $\lambda = -1$.
- Comparing the third components ($1 = \lambda \cdot 0 = 0$) is a direct contradiction.

Since no such $\lambda$ exists (or equivalently, $n_1 \times n_2 = (1, 1, -2) \neq (0, 0, 0)$), the normal vectors are not collinear. Thus, **the planes $\Pi_1$ and $\Pi_2$ are not parallel**; they intersect along a line.

### Step 3: Compute the Angle Between the Planes
We compute the dot product $n_1 \cdot n_2$ and the norms $\|n_1\|, \|n_2\|$:
$$n_1 \cdot n_2 = (1)(1) + (1)(-1) + (1)(0) = 1 - 1 + 0 = 0,$$
$$\|n_1\| = \sqrt{1^2 + 1^2 + 1^2} = \sqrt{3}, \qquad \|n_2\| = \sqrt{1^2 + (-1)^2 + 0^2} = \sqrt{2}.$$
Substituting into the angle formula:
$$\cos\theta = \frac{|n_1 \cdot n_2|}{\|n_1\|\,\|n_2\|} = \frac{|0|}{\sqrt{3}\sqrt{2}} = 0.$$
Since $\theta \in [0, \pi/2]$, we obtain:
$$\theta = \arccos(0) = \frac{\pi}{2} = 90^\circ.$$
The two planes $\Pi_1$ and $\Pi_2$ are **perpendicular (orthogonal)** to each other.

---

## 4. Verification and Consistency Checks

### 1. Cross Product Check of Non-Parallelism
$$n_1 \times n_2 = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 1 & 1 & 1 \\ 1 & -1 & 0 \end{vmatrix} = \bigl(1(0) - 1(-1), \, -(1(0) - 1(1)), \, 1(-1) - 1(1)\bigr) = (1, 1, -2) \neq \mathbf{0}.$$
Furthermore, by the Lagrange identity $\|n_1 \times n_2\|^2 + (n_1 \cdot n_2)^2 = \|n_1\|^2 \|n_2\|^2$:
$$\|(1, 1, -2)\|^2 + 0^2 = (1 + 1 + 4) + 0 = 6 = (\sqrt{3})^2 (\sqrt{2})^2 = 3 \cdot 2 = 6. \quad \checkmark$$
Since $\|n_1 \times n_2\| = \|n_1\|\|n_2\|\sin\theta$, having $\|n_1 \times n_2\| = \sqrt{6} = \|n_1\|\|n_2\|$ confirms $\sin\theta = 1$, i.e., $\theta = 90^\circ$.

### 2. Geometric Interpretation of Orthogonality
Because $n_1 \cdot n_2 = 0$, the normal vector $n_2 = (1, -1, 0)$ of $\Pi_2$ is orthogonal to $n_1$, which means the direction $n_2$ is parallel to $\Pi_1$ (and conversely $n_1$ is parallel to $\Pi_2$). Whenever a plane contains a direction normal to another plane, the two planes meet at a right angle ($90^\circ$).
