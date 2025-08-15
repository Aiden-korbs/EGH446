## General Form
$$
\dot{\mathbf{x}} = A\mathbf{x} + B\mathbf{u}, \quad \mathbf{y} = C\mathbf{x} + D\mathbf{u}
$$

- $\mathbf{x}$: state vector  
- $\mathbf{u}$: input vector  
- $\mathbf{y}$: output vector  

## Transfer Function ↔ State Space
From transfer function:
$$
G(s) = \frac{Y(s)}{U(s)} = \frac{b_m s^m + \dots + b_1 s + b_0}{s^n + a_{n-1} s^{n-1} + \dots + a_1 s + a_0}
$$

We can rewrite in **state-space form** using canonical realizations (controllable/observable forms).

## Examples

### RL Circuit
$$
\frac{di}{dt} = \frac{1}{L}(v - Ri)
$$

State-space:
$$
\dot{i} = -\frac{R}{L}i + \frac{1}{L}v, \quad y = i
$$

### RLC Circuit
$$
\begin{aligned}
\dot{i}_L &= \frac{1}{L}(v_{in} - Ri_L - v_C) \\
\dot{v}_C &= \frac{1}{C} i_L
\end{aligned}
$$

### Mass–Spring–Damper
$$
\dot{x} = v, \quad
\dot{v} = \frac{1}{M}(f - Dv - Kx)
$$

State vector:  
$$
\mathbf{x} = \begin{bmatrix} x \\ v \end{bmatrix}
$$

Input: $f$  
Output: $x$ or $v$

## Key Points
- **State variables** represent the minimal set of variables to describe the system.  
- **Linear time-invariant** (LTI) systems have constant $A,B,C,D$ matrices.  
- Useful for simulation, control design, and estimation.
