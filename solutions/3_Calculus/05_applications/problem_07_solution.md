# Solution to Problem 7: Exponential Growth

## 1. Problem Statement
Assume the model
$$
N(t)=N_0e^{kt},\qquad k>0.
$$

1. Verify by differentiation that the model satisfies the relation $N'(t)=kN(t)$.
2. Find the population doubling time.
3. Explain why the doubling time does not depend on $N_0$.

---

## 2. Theoretical Background and Concepts
1. **Continuous Exponential Growth Model**:
   In biology, physics, and economics, a population or quantity $N(t)$ grows exponentially when its **instantaneous rate of growth** $N'(t) = \frac{dN}{dt}$ is directly proportional to the **current population size** $N(t)$:
   $$
   N'(t) = k\,N(t), \qquad k > 0,
   $$
   where:
   - $N_0 = N(0) > 0$ is the initial population at time $t = 0$.
   - $k = \frac{N'(t)}{N(t)} > 0$ is the constant **relative (per-capita) growth rate** (with units of $\text{time}^{-1}$).
2. **Chain Rule for the Exponential Function**:
   For any differentiable function $u(t)$, $\frac{d}{dt}\left(e^{u(t)}\right) = e^{u(t)} u'(t)$. In particular, for $u(t) = kt$, $\frac{d}{dt}\left(e^{kt}\right) = k e^{kt}$.
3. **Doubling Time**:
   The **doubling time** $T_{\text{double}}$ (or $T$) is the time interval required for the population to grow to twice its initial (or current) value: $N(T) = 2N_0$, or more generally $N(t + T) = 2N(t)$.

---

## 3. Detailed Step-by-Step Solution

### Variable Definitions and Physical Domain
- $t \ge 0$: time (in time units, e.g., hours, days, or years), with domain $[0, \infty)$.
- $N(t) > 0$: population size at time $t$.
- $N_0 = N(0) > 0$: initial population size at $t = 0$.
- $k > 0$: constant relative growth rate (in $\text{time}^{-1}$).
- $T > 0$: doubling time (in time units).

To verify the differential relation in Part 1 we use **differentiation** (via the chain rule), and to find the doubling time in Part 2 we solve an exponential equation using the natural logarithm.

---

### Part 1: Verification That $N'(t) = kN(t)$
We differentiate $N(t) = N_0 e^{kt}$ with respect to $t$, treating the constant initial value $N_0$ as a constant multiplier and applying the chain rule to $e^{kt}$:
$$
\begin{aligned}
N'(t) &= \frac{d}{dt}\left(N_0 e^{kt}\right) \\
&= N_0 \frac{d}{dt}\left(e^{kt}\right) \\
&= N_0 \left(e^{kt} \cdot \frac{d}{dt}(kt)\right) \\
&= N_0 \left(e^{kt} \cdot k\right) \\
&= k \left(N_0 e^{kt}\right).
\end{aligned}
$$
Since $N(t) = N_0 e^{kt}$, substituting $N(t)$ for the parenthesized expression yields:
$$
N'(t) = k\,N(t).
$$
This confirms that at every instant $t \ge 0$, the instantaneous rate of change $N'(t)$ is equal to $k$ times the current value $N(t)$.

---

### Part 2: Finding the Population Doubling Time
Let $T$ denote the doubling time from $t = 0$, i.e., the time at which the population reaches twice its initial size $N_0$:
$$
N(T) = 2N_0.
$$
Substituting $N(T) = N_0 e^{kT}$ into this condition gives:
$$
N_0 e^{kT} = 2N_0.
$$
Since the initial population is non-zero ($N_0 > 0$), we divide both sides by $N_0$:
$$
e^{kT} = 2.
$$
Taking the natural logarithm ($\ln$) of both sides and using the identity $\ln(e^x) = x$:
$$
\ln\left(e^{kT}\right) = \ln 2 \implies kT = \ln 2.
$$
Since $k > 0$, dividing by $k$ yields the **doubling time**:
$$
T = \frac{\ln 2}{k} \approx \frac{0.69315}{k}.
$$

*(Note: Even if we start from an arbitrary time $t_1 \ge 0$ with population $N(t_1)$ and ask for the elapsed time $T$ until $N(t_1 + T) = 2N(t_1)$, we obtain $N_0 e^{k(t_1 + T)} = 2 N_0 e^{kt_1} \implies e^{kT} = 2 \implies T = \frac{\ln 2}{k}$.)*

---

### Part 3: Explaining Why the Doubling Time Does Not Depend on $N_0$
The independence of the doubling time $T = \frac{\ln 2}{k}$ from $N_0$ can be explained both algebraically and conceptually:

1. **Algebraic Explanation (Scale Invariance)**:
   In the doubling equation $N_0 e^{kT} = 2N_0$, the initial population $N_0$ appears as a common multiplicative factor on both sides and cancels out immediately when we form the ratio $\frac{N(T)}{N_0} = e^{kT} = 2$. Because exponential growth multiplies the population by the same factor $e^{k\Delta t}$ over any time interval of length $\Delta t$, the time needed to multiply by a factor of $2$ depends only on the rate constant $k$.

2. **Physical / Conceptual Explanation (Constant Per-Capita Growth Rate)**:
   From $N'(t) = kN(t)$, the **relative (per-capita) growth rate** is constant:
   $$
   \frac{N'(t)}{N(t)} = k.
   $$
   Each individual member of the population reproduces at the same average rate $k$ regardless of how many other individuals exist. If we start with a twice-as-large initial population ($2N_0$ instead of $N_0$), it has twice as much population to gain to double (it must add $2N_0$ instead of $N_0$), **but** it also has twice as many reproducing individuals, so its absolute growth rate $N'(t)$ is twice as fast at every moment. The larger required increase and the proportionally faster absolute growth rate cancel each other out exactly, leaving the doubling time $T = \frac{\ln 2}{k}$ unchanged.

---

## 4. Verification and Consistency Checks

1. **Direct Substitution Check**:
   Evaluating $N(t)$ at $t = T = \frac{\ln 2}{k}$:
   $$
   N\left(\frac{\ln 2}{k}\right) = N_0 \exp\left(k \cdot \frac{\ln 2}{k}\right) = N_0 e^{\ln 2} = 2N_0,
   $$
   and after $m$ doubling periods ($t = mT = m\frac{\ln 2}{k}$):
   $$
   N(mT) = N_0 e^{k m (\ln 2)/k} = N_0 \left(e^{\ln 2}\right)^m = N_0 \cdot 2^m.
   $$

2. **Dimensional (Unit) Consistency**:
   Since the exponent $kt$ in $e^{kt}$ must be dimensionless, the units of $k$ are $\text{time}^{-1}$ (e.g., $\text{hours}^{-1}$). Since $\ln 2$ is a pure dimensionless number, the formula $T = \frac{\ln 2}{k}$ has units of $\frac{1}{\text{time}^{-1}} = \text{time}$, which is dimensionally consistent.
