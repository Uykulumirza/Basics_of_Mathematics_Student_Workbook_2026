# Solution to Problem 3: A Box Made from Cardboard

## 1. Problem Statement
From a $30\text{ cm}\times40\text{ cm}$ sheet, squares of side length $x$ are cut from the corners and the edges are folded up to form an open box.

Write the volume as a function of $x$, determine the physically meaningful domain, and find the value of $x$ for which the volume is greatest.

---

## 2. Theoretical Background and Concepts
In three-dimensional geometric optimization problems:
1. **Geometric Construction of the Objective Function**: We express the three dimensions (height, width, length) of the solid in terms of a single decision variable $x$ and multiply them to obtain the volume $V(x) = \text{height} \times \text{width} \times \text{length}$.
2. **Physical/Geometric Domain**: Every linear dimension of a physical three-dimensional box must be strictly positive ($\text{height} > 0$, $\text{width} > 0$, $\text{length} > 0$). The intersection of these inequalities defines the open interval $(a, b)$ of physically feasible values of $x$.
3. **Optimization on an Open Interval with Vanishing Endpoint Limits**:
   If $V(x)$ is continuous and differentiable on $(a, b)$, $V(x) > 0$ on $(a, b)$, and $\lim_{x \to a^+} V(x) = \lim_{x \to b^-} V(x) = 0$, then by the Extreme Value Theorem on $[a, b]$, $V(x)$ must attain an absolute maximum at an interior critical point $x^* \in (a, b)$ where $V'(x^*) = 0$.

---

## 3. Detailed Step-by-Step Solution

### Choosing Variables and Building the Geometric Model
Let $x\text{ [cm]}$ be the side length of each of the four identical squares removed from the corners of the $30\text{ cm} \times 40\text{ cm}$ rectangular cardboard sheet.

```
      |<---------------- 40 cm ---------------->|
      +-----+-----------------------------+-----+  ---
      |  x  |                             |  x  |   ^
      +-----+ - - - - - - - - - - - - - - +-----+   |
      |     :                             :     |   |
      |     :      Base of the box        :     | 30 cm
      |     :  (40 - 2x) cm x (30 - 2x) cm:     |   |
      |     :                             :     |   |
      +-----+ - - - - - - - - - - - - - - +-----+   v
      |  x  |                             |  x  |  ---
      +-----+-----------------------------+-----+
```

When the four side flaps are folded upward by $90^\circ$ along the dashed lines:
- **Height of the box**: $h(x) = x\text{ [cm]}$.
- **Width of the base** (formed from the $30\text{ cm}$ side after removing $x$ from both ends): $w(x) = 30 - 2x\text{ [cm]}$.
- **Length of the base** (formed from the $40\text{ cm}$ side after removing $x$ from both ends): $l(x) = 40 - 2x\text{ [cm]}$.

Since we want to maximize a differentiable volume function $V(x)$ over an interval of continuous cut lengths $x$, **differential calculus** (finding critical points via the first derivative) is the appropriate tool.

---

### Step 1: Volume as a Function of $x$
The volume $V(x)$ of the rectangular box (in $\text{cm}^3$) is the product of its height, width, and length:
$$
V(x) = x(30 - 2x)(40 - 2x).
$$
Expanding the product to obtain a polynomial in standard form:
$$
\begin{aligned}
V(x) &= x\left(1200 - 60x - 80x + 4x^2\right) \\
&= x\left(4x^2 - 140x + 1200\right) \\
&= 4x^3 - 140x^2 + 1200x \quad [\text{cm}^3].
\end{aligned}
$$

---

### Step 2: Physically Meaningful Domain
For a non-degenerate three-dimensional box to exist, all three dimensions must be strictly positive:
1. Positive height: $x > 0$.
2. Positive base width: $30 - 2x > 0 \iff 2x < 30 \iff x < 15$.
3. Positive base length: $40 - 2x > 0 \iff 2x < 40 \iff x < 20$.

The intersection of $x > 0$, $x < 15$, and $x < 20$ is governed by the shorter side of the cardboard sheet ($30\text{ cm}$):
$$
D_V = (0, 15)\text{ [cm]}.
$$
*(If $x \ge 15\text{ cm}$, the two cuts along the $30\text{ cm}$ side meet or overlap, leaving no base width.)*

---

### Step 3: Finding the Value of $x$ That Maximizes the Volume
Differentiating $V(x) = 4x^3 - 140x^2 + 1200x$ with respect to $x$ gives:
$$
V'(x) = \frac{d}{dx}\left(4x^3 - 140x^2 + 1200x\right) = 12x^2 - 280x + 1200.
$$
Factoring out $4$ simplifies the derivative:
$$
V'(x) = 4\left(3x^2 - 70x + 300\right).
$$
To find the critical points, we solve $V'(x) = 0$:
$$
3x^2 - 70x + 300 = 0.
$$
Using the quadratic formula with $a = 3$, $b = -70$, and $c = 300$:
$$
\Delta = b^2 - 4ac = (-70)^2 - 4(3)(300) = 4900 - 3600 = 1300 = 100 \times 13,
$$
$$
\sqrt{\Delta} = 10\sqrt{13}.
$$
Hence the roots of $V'(x) = 0$ are:
$$
x = \frac{70 \pm 10\sqrt{13}}{2 \cdot 3} = \frac{35 \pm 5\sqrt{13}}{3}.
$$
Using $\sqrt{13} \approx 3.605551$, we evaluate both roots against the physical domain $D_V = (0, 15)$:
1. **First root**:
   $$
   x_1 = \frac{35 + 5\sqrt{13}}{3} \approx \frac{35 + 18.027756}{3} \approx 17.676\text{ cm} \notin (0, 15).
   $$
   We reject $x_1$ because for $x_1 > 15\text{ cm}$ the width $30 - 2x_1 \approx -5.35\text{ cm} < 0$ is physically impossible.
2. **Second root**:
   $$
   x^* = \frac{35 - 5\sqrt{13}}{3}\text{ cm} \approx \frac{35 - 18.027756}{3}\text{ cm} \approx 5.6574\text{ cm} \in (0, 15).
   $$
   This is the **unique critical point** inside the physical domain $(0, 15)$.

---

### Step 4: Justification of the Maximum and Optimal Dimensions
- **First Derivative Sign Analysis on $(0, 15)$**:
  The quadratic $3x^2 - 70x + 300$ opens upward ($a = 3 > 0$) and has roots at $x^* \approx 5.657$ and $x_1 \approx 17.676$. Therefore:
  - On $(0, x^*)$, $V'(x) > 0$, so $V(x)$ is **strictly increasing**.
  - On $(x^*, 15)$, $V'(x) < 0$, so $V(x)$ is **strictly decreasing**.
- **Second Derivative Test**:
  $$
  V''(x) = 24x - 280 \implies V''(x^*) = 24\left(\frac{35 - 5\sqrt{13}}{3}\right) - 280 = 280 - 40\sqrt{13} - 280 = -40\sqrt{13} \approx -144.22 < 0.
  $$
  Thus $x^* = \frac{35 - 5\sqrt{13}}{3}\text{ cm}$ is the **unique global maximum** of $V(x)$ on $(0, 15)$.

#### Optimal Dimensions and Maximum Volume
At $x^* = \frac{35 - 5\sqrt{13}}{3} \approx 5.657\text{ cm}$:
- **Height**: $h = x^* = \frac{35 - 5\sqrt{13}}{3} \approx 5.66\text{ cm}$.
- **Width**: $w = 30 - 2x^* = \frac{20 + 10\sqrt{13}}{3} \approx 18.69\text{ cm}$.
- **Length**: $l = 40 - 2x^* = \frac{50 + 10\sqrt{13}}{3} \approx 28.69\text{ cm}$.
- **Maximum Volume**:
  $$
  V_{\max} = V\left(\frac{35 - 5\sqrt{13}}{3}\right) = \frac{2000\left(26\sqrt{13} - 35\right)}{27}\text{ cm}^3 \approx 3032.30\text{ cm}^3.
  $$

---

## 4. Verification and Consistency Checks

1. **Endpoint Limit Check**:
   - At $x \to 0^+$ (no cut, flat sheet of height $0$): $V(0) = 0\text{ cm}^3$.
   - At $x \to 15^-$ (sheet folded in half with width $0$): $V(15) = 15(0)(10) = 0\text{ cm}^3$.
   Since $V(x) > 0$ on $(0, 15)$ and vanishes at both endpoints, the interior critical point $x^* \approx 5.657\text{ cm}$ must be the global maximum.

2. **Numerical Check Around $x^* \approx 5.6574\text{ cm}$**:
   | Cut $x\text{ [cm]}$ | Width $30-2x\text{ [cm]}$ | Length $40-2x\text{ [cm]}$ | Volume $V(x)\text{ [cm}^3\text{]}$ | $V'(x)\text{ [cm}^2\text{]}$ |
   | :---: | :---: | :---: | :---: | :---: |
   | $5.0000$ | $20.0000$ | $30.0000$ | $3000.00$ | $+100.00 > 0$ |
   | $5.5000$ | $19.0000$ | $29.0000$ | $3030.50$ | $+23.00 > 0$ |
   | **$5.6574$** | **$18.6852$** | **$28.6852$** | **$3032.30$ (Max)** | **$0.00$** |
   | $6.0000$ | $18.0000$ | $28.0000$ | $3024.00$ | $-48.00 < 0$ |

   The table confirms that the volume peaks at $x^* = \frac{35 - 5\sqrt{13}}{3} \approx 5.66\text{ cm}$ with $V_{\max} \approx 3032.30\text{ cm}^3$.
