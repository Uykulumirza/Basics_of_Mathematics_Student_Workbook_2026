# Solution to Problem 10: A Cable Through Water and Land

## 1. Problem Statement
Point $A$ lies on one bank of a river of width $100$ m, and point $B$ lies on the other bank, $500$ m along the bank from the point directly opposite $A$.

The cost per meter of cable underwater is twice the cost per meter of cable on land.

Build a cost function depending on the point where the cable comes out of the water, determine the domain, and find the solution that minimizes the cost.

---

## 2. Theoretical Background and Concepts
1. **Geometric Modeling of Two-Medium Routing (Snell's Law / Fermat's Principle Analog)**:
   When connecting two points across two media with different unit costs (or travel speeds), the total path consists of a straight segment underwater (of length determined by the Pythagorean theorem) and a straight segment along the bank on land.
2. **Optimization on a Closed, Bounded Interval $[a, b]$**:
   By the **Extreme Value Theorem**, a continuous cost function $C(x)$ on a closed interval $[0, 500]$ attains an absolute minimum on $[0, 500]$. The absolute minimum must occur either:
   - at an interior **critical point** $x^* \in (0, 500)$ where $C'(x^*) = 0$, or
   - at one of the **endpoints** $x = 0$ or $x = 500$.

---

## 3. Detailed Step-by-Step Solution

### Choosing Variables and Sketching the Geometry
Let the river banks be parallel straight lines separated by a perpendicular width of $100\text{ m}$:
- Let $O$ be the point on the far bank directly opposite $A$, so that $AO \perp OB$, $|AO| = 100\text{ m}$, and $|OB| = 500\text{ m}$.
- Let $P$ be the landing point on the far bank (between $O$ and $B$) where the cable comes out of the water and continues along the bank to $B$.
- Let **$x\text{ [m]} = |OP|$** denote the distance along the far bank from $O$ to the landing point $P$.
- Let **$c > 0\text{ [currency/m]}$** denote the unit cost per meter of laying the cable **on land**. Then the unit cost per meter **underwater** is **$2c\text{ [currency/m]}$**.

```
       O <--- x m ---> P <--------- (500 - x) m ---------> B   (Far bank: land cost = c/m)
       +---------------+-----------------------------------+
       |              /
 100 m |             /   Underwater cable:
       |            /    length = sqrt(x^2 + 100^2) m
       |           /     cost   = 2c per meter
       +----------+----------------------------------------+
       A                                                       (Near bank)
```

Because we want to minimize a continuous, differentiable cost function $C(x)$ over an interval of landing positions $x$, we use **differential calculus**.

---

### Step 1: Building the Cost Function and Determining the Domain

#### Lengths of the Two Cable Segments
1. **Underwater segment $AP$**: Since $\triangle AOP$ is a right triangle with legs $|AO| = 100\text{ m}$ and $|OP| = x\text{ m}$, the Pythagorean theorem gives the underwater length:
   $$
   L_{\text{water}}(x) = |AP| = \sqrt{100^2 + x^2} = \sqrt{x^2 + 10\,000}\text{ [m]}.
   $$
2. **Land segment $PB$**: Since $P$ lies on the segment $OB$ of total length $500\text{ m}$ at distance $x$ from $O$, the remaining distance along the bank from $P$ to $B$ is:
   $$
   L_{\text{land}}(x) = |PB| = 500 - x\text{ [m]}.
   $$

#### Domain of $x$
Landing to the left of $O$ ($x < 0$) or beyond $B$ ($x > 500$) would simultaneously increase both the underwater distance and the land distance compared to $x = 0$ or $x = 500$. Thus, the physically and economically meaningful domain for the landing point $P$ on segment $OB$ is:
$$
D_C = [0, 500]\text{ [m]}.
$$
- $x = 0\text{ m}$ corresponds to crossing the river perpendicularly from $A$ to $O$ ($100\text{ m}$ underwater) and running $500\text{ m}$ on land.
- $x = 500\text{ m}$ corresponds to laying the entire cable underwater in a straight line directly from $A$ to $B$ ($0\text{ m}$ on land).

#### Total Cost Function
Multiplying each segment length by its respective unit cost ($2c$ underwater and $c$ on land) gives the total cost function:
$$
C(x) = 2c\sqrt{x^2 + 10\,000} + c(500 - x) = c\left(2\sqrt{x^2 + 10\,000} + 500 - x\right), \qquad x \in [0, 500],
$$
where $c > 0$ is the cost per meter on land. *(Equivalently, measuring cost in units of $c$, the dimensionless relative cost function is $f(x) = \frac{C(x)}{c} = 2\sqrt{x^2 + 10\,000} + 500 - x$.)*

---

### Step 2: Differentiating $C(x)$ and Finding Critical Points
We differentiate $C(x)$ with respect to $x$ on $(0, 500)$ using the chain rule $\frac{d}{dx}\sqrt{x^2 + 10\,000} = \frac{2x}{2\sqrt{x^2 + 10\,000}} = \frac{x}{\sqrt{x^2 + 10\,000}}$:
$$
C'(x) = c\left(\frac{2x}{\sqrt{x^2 + 10\,000}} - 1\right) = c\,\frac{2x - \sqrt{x^2 + 10\,000}}{\sqrt{x^2 + 10\,000}}.
$$
Since $c > 0$, we set $C'(x) = 0$:
$$
\frac{2x}{\sqrt{x^2 + 10\,000}} - 1 = 0 \iff 2x = \sqrt{x^2 + 10\,000}.
$$
Since $x \in [0, 500]$, both sides are non-negative (specifically $x > 0$), so squaring both sides yields an equivalent equation:
$$
(2x)^2 = x^2 + 10\,000 \iff 4x^2 = x^2 + 10\,000 \iff 3x^2 = 10\,000 \iff x^2 = \frac{10\,000}{3}.
$$
Taking the positive square root ($x \ge 0$):
$$
x^* = \frac{100}{\sqrt{3}} = \frac{100\sqrt{3}}{3}\text{ m} \approx 57.735\text{ m}.
$$
Since $0 \le 57.735 \le 500$, the critical point $x^* = \frac{100\sqrt{3}}{3}\text{ m}$ lies strictly inside the domain $[0, 500]$.

---

### Step 3: Verification of the Global Minimum and Interpretation
1. **First Derivative Sign Chart on $[0, 500]$**:
   - On $\left[0, \frac{100\sqrt{3}}{3}\right)$, we have $3x^2 < 10\,000 \iff 2x < \sqrt{x^2 + 10\,000} \implies C'(x) < 0$, so $C(x)$ is **strictly decreasing**.
   - On $\left(\frac{100\sqrt{3}}{3}, 500\right]$, we have $3x^2 > 10\,000 \iff 2x > \sqrt{x^2 + 10\,000} \implies C'(x) > 0$, so $C(x)$ is **strictly increasing**.
2. **Second Derivative Check**:
   $$
   C''(x) = \frac{20\,000\,c}{(x^2 + 10\,000)^{3/2}} > 0 \quad \text{for all } x \in [0, 500].
   $$
   Thus $C(x)$ is strictly convex on $[0, 500]$, and $x^* = \frac{100\sqrt{3}}{3}\text{ m}$ is the **unique global minimum**.

#### Optimal Routing Summary
- **Optimal emergence point $P$**: $x^* = \frac{100\sqrt{3}}{3}\text{ m} \approx 57.74\text{ m}$ downstream from $O$ (the point directly opposite $A$).
- **Length of cable underwater**:
  $$
  L_{\text{water}}(x^*) = \sqrt{\frac{10\,000}{3} + 10\,000} = \sqrt{\frac{40\,000}{3}} = \frac{200}{\sqrt{3}} = \frac{200\sqrt{3}}{3}\text{ m} \approx 115.47\text{ m}.
  $$
- **Length of cable on land**:
  $$
  L_{\text{land}}(x^*) = 500 - \frac{100\sqrt{3}}{3}\text{ m} \approx 442.26\text{ m}.
  $$
- **Minimum total cost**:
  $$
  C_{\min} = C\left(\frac{100\sqrt{3}}{3}\right) = c\left(2 \cdot \frac{200\sqrt{3}}{3} + 500 - \frac{100\sqrt{3}}{3}\right) = \left(500 + 100\sqrt{3}\right)c \approx 673.21\,c.
  $$

---

## 4. Verification and Consistency Checks

1. **Comparison with Endpoint Routing Strategies**:
   | Strategy | $x\text{ [m]}$ | Underwater Length $\text{[m]}$ | Land Length $\text{[m]}$ | Total Cost $C(x)$ |
   | :--- | :---: | :---: | :---: | :---: |
   | Perpendicular crossing ($A \to O \to B$) | $0$ | $100.00$ | $500.00$ | $700.00\,c$ |
   | **Optimal routing ($A \to P^* \to B$)** | **$\frac{100\sqrt{3}}{3} \approx 57.74$** | **$\frac{200\sqrt{3}}{3} \approx 115.47$** | **$500 - \frac{100\sqrt{3}}{3} \approx 442.26$** | **$(500 + 100\sqrt{3})c \approx 673.21\,c$ (Min)** |
   | All-underwater diagonal ($A \to B$) | $500$ | $\sqrt{260\,000} = 100\sqrt{26} \approx 509.90$ | $0.00$ | $200\sqrt{26}\,c \approx 1019.80\,c$ |

   The optimal landing point saves $(200 - 100\sqrt{3})c \approx 26.79\,c$ compared to crossing straight across at $x = 0$, and saves $\approx 346.59\,c$ compared to going diagonally underwater to $B$.

2. **Trigonometric / Snell's Law Interpretation**:
   In $\triangle AOP$, let $\theta = \angle OAP$ be the angle between the underwater cable and the perpendicular $AO$. Then $\sin\theta = \frac{x}{\sqrt{x^2 + 10\,000}}$. The optimality condition $C'(x) = 0 \iff \frac{x}{\sqrt{x^2 + 10\,000}} = \frac{1}{2}$ simply states that $\sin\theta = \frac{c}{2c} = \frac{1}{2}$, so $\theta = 30^\circ$ and $x^* = 100\tan 30^\circ = \frac{100}{\sqrt{3}}\text{ m}$.
