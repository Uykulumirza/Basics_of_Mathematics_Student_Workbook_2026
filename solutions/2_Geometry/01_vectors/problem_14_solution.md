# Solution: Exercise 14 — Closest Point on a Line

## 1. Problem Statement
Given a point $P=(4,1)$ and a line through the origin with direction $v=(1,2)$. Using projection, find the closest point on the line, the distance from $P$ to the line, and verify that the appropriate vector is perpendicular to the direction of the line.

---

## 2. Theoretical Background and Concepts
Let $\ell$ be the line passing through the origin $O = (0, 0)$ with non-zero direction vector $v = (1, 2)$, so every point $X \in \ell$ has position vector $\overrightarrow{OX} = tv$ for some $t \in \mathbb{R}$.
Given an external point $P$ with position vector $p = \overrightarrow{OP}$:
- For any point $X \in \ell$ and the orthogonal projection point $Q \in \ell$ defined by $\overrightarrow{OQ} = \operatorname{proj}_v \overrightarrow{OP}$, the vector $\overrightarrow{QP} = \overrightarrow{OP} - \overrightarrow{OQ}$ is **orthogonal** to the line direction $v$ ($\overrightarrow{QP} \cdot v = 0$).
- By the Pythagorean theorem applied to the right triangle $\triangle XQP$ (where $\overrightarrow{XQ} \parallel v$ and $\overrightarrow{QP} \perp v$):
  $$\|\overrightarrow{XP}\|^2 = \|\overrightarrow{XQ}\|^2 + \|\overrightarrow{QP}\|^2 \ge \|\overrightarrow{QP}\|^2,$$
  with equality if and only if $X = Q$. Therefore:
  1. The **closest point** on $\ell$ to $P$ is the foot of the perpendicular $Q = \operatorname{proj}_v \overrightarrow{OP}$.
  2. The **minimum distance** from $P$ to $\ell$ is the length of the perpendicular residual vector $\|\overrightarrow{QP}\| = \|P - Q\|$.

---

## 3. Detailed Step-by-Step Solution

### Step 1: Find the closest point $Q$ on the line using orthogonal projection
Representing $P = (4, 1)$ by its position vector $p = \overrightarrow{OP} = (4, 1)$ and projecting onto $v = (1, 2)$:
$$p \cdot v = (4)(1) + (1)(2) = 4 + 2 = 6,$$
$$\|v\|^2 = v \cdot v = 1^2 + 2^2 = 1 + 4 = 5.$$
Thus, the position vector of the closest point $Q$ on the line is:
$$\overrightarrow{OQ} = \operatorname{proj}_v \overrightarrow{OP} = \frac{p \cdot v}{\|v\|^2}v = \frac{6}{5}(1, 2) = \left(\frac{6}{5},\; \frac{12}{5}\right).$$
Therefore, the closest point on the line is:
$$Q = \left(\frac{6}{5},\; \frac{12}{5}\right) = (1.2,\; 2.4).$$

### Step 2: Construct the displacement vector $\overrightarrow{QP}$ and verify perpendicularity to $v$
The vector pointing from the closest point $Q$ on the line to $P = (4, 1) = \left(\frac{20}{5}, \frac{5}{5}\right)$ is:
$$\overrightarrow{QP} = P - Q = \left(4 - \frac{6}{5},\; 1 - \frac{12}{5}\right) = \left(\frac{20 - 6}{5},\; \frac{5 - 12}{5}\right) = \left(\frac{14}{5},\; -\frac{7}{5}\right).$$
Checking the dot product of $\overrightarrow{QP}$ with the line direction $v = (1, 2)$:
$$\overrightarrow{QP} \cdot v = \left(\frac{14}{5},\; -\frac{7}{5}\right) \cdot (1, 2) = \left(\frac{14}{5}\right)(1) + \left(-\frac{7}{5}\right)(2) = \frac{14}{5} - \frac{14}{5} = 0.$$
This confirms that the connecting vector $\overrightarrow{QP}$ is strictly perpendicular to the direction vector $v$ of the line.

### Step 3: Compute the distance from $P$ to the line
The distance $d(P, \ell)$ from $P$ to the line is the Euclidean length of the perpendicular vector $\overrightarrow{QP} = \left(\frac{14}{5}, -\frac{7}{5}\right) = \frac{7}{5}(2, -1)$:
$$d(P, \ell) = \|\overrightarrow{QP}\| = \sqrt{\left(\frac{14}{5}\right)^2 + \left(-\frac{7}{5}\right)^2} = \frac{7}{5}\sqrt{2^2 + (-1)^2} = \frac{7}{5}\sqrt{4 + 1} = \frac{7\sqrt{5}}{5} = \frac{7}{\sqrt{5}} \approx 3.1305.$$

---

## 4. Verification and Consistency Checks

### Verification via Point-to-Line Distance Formula in $\mathbb{R}^2$
The line through the origin with direction $v = (1, 2)$ has slope $2$, so its Cartesian equation is $2x - y = 0$. Using the standard point-to-line distance formula for $P = (4, 1)$ and $2x - y = 0$:
$$d(P, \ell) = \frac{|2(4) - 1(1)|}{\sqrt{2^2 + (-1)^2}} = \frac{|8 - 1|}{\sqrt{5}} = \frac{7}{\sqrt{5}} = \frac{7\sqrt{5}}{5},$$
which matches $\|\overrightarrow{QP}\|$ identically.

### Pythagorean Check on Right Triangle $\triangle OQP$
- $\|\overrightarrow{OQ}\|^2 = \left(\frac{6}{5}\right)^2 + \left(\frac{12}{5}\right)^2 = \frac{36 + 144}{25} = \frac{180}{25} = \frac{36}{5}$
- $\|\overrightarrow{QP}\|^2 = \left(\frac{7}{\sqrt{5}}\right)^2 = \frac{49}{5}$
- $\|\overrightarrow{OQ}\|^2 + \|\overrightarrow{QP}\|^2 = \frac{36}{5} + \frac{49}{5} = \frac{85}{5} = 17 = 4^2 + 1^2 = \|\overrightarrow{OP}\|^2$.
