# Solution to Problem 13: A Multi-Layer Composition

## 1. Problem Statement

For
$$f(x)=e^{\sin(x^2)}$$
compute the derivative. First write the layers
$$x\longrightarrow x^2\longrightarrow \sin(x^2)\longrightarrow e^{\sin(x^2)}$$
and explain why differentiation moves through them in the reverse order.

> **Why this problem:** it develops the chain rule as a method for working with multiple layers.

---

## 2. Theoretical Background and Concepts

1. **Three-Layer Composite Functions**:
   When a function $f(x) = (g_3 \circ g_2 \circ g_1)(x) = g_3(g_2(g_1(x)))$ is built from three nested operations, we can introduce intermediate variables:
   $$u = g_1(x), \qquad v = g_2(u), \qquad y = g_3(v)$$
2. **The Multi-Layer Chain Rule**:
   If $g_1$ is differentiable at $x$, $g_2$ is differentiable at $u = g_1(x)$, and $g_3$ is differentiable at $v = g_2(g_1(x))$, then the composite function $f = g_3 \circ g_2 \circ g_1$ is differentiable at $x$, and its derivative is the product of the derivatives of all three layers:
   $$f'(x) = g_3'\left(g_2(g_1(x))\right) \cdot g_2'\left(g_1(x)\right) \cdot g_1'(x)$$
   In Leibniz notation:
   $$\frac{dy}{dx} = \frac{dy}{dv} \cdot \frac{dv}{du} \cdot \frac{du}{dx}$$

---

## 3. Detailed Step-by-Step Solution

### Step 1: Write the forward evaluation layers

To evaluate $f(x) = e^{\sin(x^2)}$ for a given input $x$, we apply three elementary functions sequentially from the **inside out**:
$$x \xrightarrow{\text{Layer 1: square}} u = x^2 \xrightarrow{\text{Layer 2: sine}} v = \sin(u) = \sin(x^2) \xrightarrow{\text{Layer 3: exponential}} y = e^v = e^{\sin(x^2)}$$

Explicitly, the three component functions and their individual derivatives with respect to their own inputs are:
1. **Innermost layer ($g_1$)**:
   $$u = g_1(x) = x^2 \implies \frac{du}{dx} = g_1'(x) = 2x$$
2. **Middle layer ($g_2$)**:
   $$v = g_2(u) = \sin u \implies \frac{dv}{du} = g_2'(u) = \cos u = \cos(x^2)$$
3. **Outermost layer ($g_3$)**:
   $$y = g_3(v) = e^v \implies \frac{dy}{dv} = g_3'(v) = e^v = e^{\sin(x^2)}$$

---

### Step 2: Explain why differentiation moves through the layers in the reverse order

Why does **evaluation** proceed from inside out ($x \to x^2 \to \sin(x^2) \to e^{\sin(x^2)}$), whereas **differentiation** proceeds from **outside in** (starting with $e^{(\cdot)}$, then $\sin(\cdot)$, and finally $x^2$)?

1. **The "Unwrapping the Package" Principle (Algebraic Structure)**:
   At the top level, the expression $f(x) = e^{\sin(x^2)}$ is an **exponential function** $e^v$ whose input happens to be the sub-expression $v = \sin(x^2)$. Before we can reach or differentiate the inner expression $v = \sin(x^2)$, we must first differentiate the outermost operation $e^v$ with respect to its whole argument $v$, leaving the inner argument $v = \sin(x^2)$ intact inside $e^{\sin(x^2)}$. Next, we must find $\frac{dv}{dx} = \frac{d}{dx}[\sin(x^2)]$. At this second stage, $\sin(u)$ is the outer operation wrapping $u = x^2$, so we differentiate $\sin(u)$ to get $\cos(x^2)$, and only at the final step do we unwrap and differentiate the innermost core $u = x^2$ to get $2x$:
   $$\frac{d}{dx}\left[e^{\sin(x^2)}\right] = e^{\sin(x^2)} \cdot \frac{d}{dx}\left[\sin(x^2)\right] = e^{\sin(x^2)} \cdot \cos(x^2) \cdot \frac{d}{dx}\left[x^2\right] = e^{\sin(x^2)} \cdot \cos(x^2) \cdot 2x$$

2. **Linear Approximation / Composition of Derivatives**:
   In general, if $f = g_3 \circ g_2 \circ g_1$, the derivative of the composition at $x$ is the composition (product) of the linear maps $Dg_3(v) \circ Dg_2(u) \circ Dg_1(x)$, which naturally writes the outermost derivative $g_3'(v)$ first on the left, followed by the middle derivative $g_2'(u)$, and finally the innermost derivative $g_1'(x)$. (Because multiplication of real numbers is commutative, the final factors can be rearranged in any order once computed, but the **process of peeling off derivatives** must strictly proceed from the outermost layer inward so that each outer derivative is evaluated at the untouched inner layers.)

---

### Step 3: Compute and organize the derivative $f'(x)$

Multiplying the derivatives of the three layers from outside in via the chain rule:
$$f'(x) = \underbrace{e^{\sin(x^2)}}_{\frac{dy}{dv}} \cdot \underbrace{\cos(x^2)}_{\frac{dv}{du}} \cdot \underbrace{(2x)}_{\frac{du}{dx}}$$

Writing the polynomial and trigonometric factors in front of the exponential for clarity gives:
$$f'(x) = 2x\cos(x^2)e^{\sin(x^2)}$$

---

## 4. Verification and Consistency Checks

1. **Logarithmic Differentiation Check**:
   Since $f(x) = e^{\sin(x^2)} > 0$ for all $x \in \mathbb{R}$, we can take the natural logarithm of both sides:
   $$\ln f(x) = \sin(x^2)$$
   Differentiating both sides with respect to $x$ (using Problem 7's result $\frac{d}{dx}[\sin(x^2)] = 2x\cos(x^2)$ on the right):
   $$\frac{f'(x)}{f(x)} = 2x\cos(x^2) \implies f'(x) = 2x\cos(x^2)f(x) = 2x\cos(x^2)e^{\sin(x^2)}$$
   This independently confirms our three-layer chain rule calculation.
2. **Parity and Maclaurin Series Check Near $x = 0$**:
   - $f(x) = e^{\sin(x^2)}$ is an even function, and $f'(x) = 2x\cos(x^2)e^{\sin(x^2)}$ is an odd function with $f'(0) = 0$.
   - Near $x = 0$, $\sin(x^2) = x^2 + O(x^6)$, so $e^{\sin(x^2)} = 1 + x^2 + O(x^4)$. Differentiating gives $f'(x) = 2x + O(x^3)$, which matches $2x\cos(0)e^{\sin(0)} = 2x(1)(1) = 2x$ to leading order.
