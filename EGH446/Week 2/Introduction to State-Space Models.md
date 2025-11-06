State-space modelling is an alternative to transfer function methods for describing and analyzing dynamic systems. It is a time-domain approach that uses matrices to represent the relationships between a system's internal states, inputs, and outputs. This method is particularly powerful for multi-input, multi-output (MIMO) systems and forms the basis for modern control theory.

---
## General Form (Continuous-Time)

A linear time-invariant (LTI) system can be represented by two primary equations:

1. **The State Equation:** Describes the evolution of the system's internal state over time.
    
    $$\dot{\mathbf{x}}(t) = A\mathbf{x}(t) + B\mathbf{u}(t)$$
    
    
2. **The Output Equation:** Relates the system's output to its current state and input.
    
    $$\mathbf{y}(t) = C\mathbf{x}(t) + D\mathbf{u}(t)$$
    
    

### Components

- $\mathbf{x}(t)$: The **state vector**, a vector containing the state variables.
    
- $\dot{\mathbf{x}}(t)$: The derivative of the state vector with respect to time.
    
- $\mathbf{u}(t)$: The **input vector** (or control vector).
    
- $\mathbf{y}(t)$: The **output vector**.
    
- $A$: The **system matrix**, which describes the system's internal dynamics.
    
- $B$: The **input matrix**, which shows how the input affects the state.
    
- $C$: The **output matrix**, which shows how the state is converted to an output.
    
- $D$: The **feedforward matrix** (or direct transmission matrix), which represents the direct path from the input to the output.
    

### Key Definitions

- **State Variables:** "The smallest set of linearly independent system variables such that the value of the members of the set at time $t_0$ along with known forcing functions completely determine the value of all the system variables from $t \ge t_0$.
    
- **State Equations:** "A set of n simultaneous, first-order differential equations with n state variables".
    
- **Output Equation:** "The equation that expresses the output variables of a system as linear combinations of the state variables and the inputs".
    

## Examples of System Modelling

### 1. RL Circuit

For a simple series RL circuit, the input variable is the voltage $v(t)$, and the single state variable is the current $i(t)$.

- **Governing Equation (KVL):** $v(t) = Ri(t) + L\frac{di}{dt}$ 
    
- **State Equation:** Rearranging for the derivative of the state variable:
    
    $$ \dot{i}(t) = -\frac{R}{L}i(t) + \frac{1}{L}v(t)$$
    
    
- **Output Equation (if output $y$ is the current):** $y(t) = i(t)$
    
- **State-Space Matrices:**
    
    - $A = [-\frac{R}{L}]$
        
    - $B = [\frac{1}{L}]$
        
    - $C = [1]$
        
    - $D = [0]$
        

### 2. RLC Circuit

This circuit has two state variables, typically the inductor current $i_L(t)$ and the capacitor voltage $v_C(t)$. The input is $v_{in}(t)$.

- **Governing Equations (KVL/KCL):**
    
    1. $v_{in}(t) = Ri_{L}(t) + L\frac{di_{L}(t)}{dt} + v_{C}(t)$ 
        
    2. $i_{L}(t) = C\frac{dv_{C}(t)}{dt}$ 
        
- **State Equations (rearranged):**
    
    1. $\frac{di_{L}(t)}{dt} = -\frac{R}{L}i_{L}(t) - \frac{1}{L}v_{C}(t) + \frac{1}{L}v_{in}(t)$ 
        
    2. $\frac{dv_{C}(t)}{dt} = \frac{1}{C}i_{L}(t) + 0 v_{C}(t) + 0 v_{in}(t)$ 
        
- Matrix Form:
    
    Let the state vector be $\mathbf{x} = \begin{bmatrix} i_L(t) \\ v_C(t) \end{bmatrix}$. If the output $y$ is the capacitor voltage $v_{out}(t) = v_C(t)$
    
    $$ \dot{\mathbf{x}} = \begin{bmatrix} -R/L & -1/L \\ 1/C & 0 \end{bmatrix} \mathbf{x} + \begin{bmatrix} 1/L \\ 0 \end{bmatrix} v_{in}(t)$$
    
    
    $$ y = \begin{bmatrix} 0 & 1 \end{bmatrix} \mathbf{x} + [0] v_{in}(t)$$
    
    

### 3. Mass–Spring–Damper System

For a mechanical system, state variables are typically position and velocity.

- **State Variables:** $x_1 = x(t)$ (position) and $x_2 = v(t)$ (velocity).
    
- **Input:** $u = f(t)$ (external force).
    
- **Governing Equations (Newton's 2nd Law):**
    
    1. $\frac{dx(t)}{dt} = v(t)$ 
        
    2. $f(t) = M\frac{dv(t)}{dt} + Dv(t) + Kx(t)$ 
        
- **State Equations (rearranged):**
    
    1. $\dot{x}_1 = 0x_1 + 1x_2 + 0u$ 
        
    2. $\dot{x}_2 = -\frac{K}{M}x_1 - \frac{D}{M}x_2 + \frac{1}{M}u$ 
        
- Matrix Form:
    
    Let the state vector be $\mathbf{x} = \begin{bmatrix} x_1 \\ x_2 \end{bmatrix}$. If the output $y$ is the position $x(t)$:
    
    $$ \dot{\mathbf{x}} = \begin{bmatrix} 0 & 1 \\ -K/M & -D/M \end{bmatrix} \mathbf{x} + \begin{bmatrix} 0 \\ 1/M \end{bmatrix} u(t)$$
    
    
    $$ y = \begin{bmatrix} 1 & 0 \end{bmatrix} \mathbf{x} + [0] u(t)$$
    
    

## Conversions

### State Space to Transfer Function

To convert from state-space ($A, B, C, D$) to a transfer function $T(s) = \frac{Y(s)}{U(s)}$:

1. Take the Laplace transform of the state and output equations, assuming zero initial conditions.
    
    - $s\mathbf{X}(s) = A\mathbf{X}(s) + B\mathbf{U}(s)$ 
        
    - $\mathbf{Y}(s) = C\mathbf{X}(s) + D\mathbf{U}(s)$ 
        
2. Solve the state equation for $\mathbf{X}(s)$:
    
    - $sI\mathbf{X}(s) - A\mathbf{X}(s) = B\mathbf{U}(s)$ 
        
    - $(sI - A)\mathbf{X}(s) = B\mathbf{U}(s)$ 
        
    - $\mathbf{X}(s) = (sI - A)^{-1}B\mathbf{U}(s)$ 
        
3. Substitute this $\mathbf{X}(s)$ into the output equation:
    
    - $\mathbf{Y}(s) = C\left((sI - A)^{-1}B\mathbf{U}(s)\right) + D\mathbf{U}(s)$ 
        
    - $\mathbf{Y}(s) = \left[C(sI - A)^{-1}B + D\right]\mathbf{U}(s)$ 
        
4. The transfer function is the matrix $T(s)$:
    
    $$T(s) = \frac{\mathbf{Y}(s)}{\mathbf{U}(s)} = C(sI - A)^{-1}B + D$$
    
    

Note: The term $(sI - A)^{-1}$ is $\frac{adj(sI-A)}{det(sI-A)}$. This means the poles of the transfer function are the roots of $det(sI-A) = 0$.

### Transfer Function to State Space (Phase Variable Form)

A transfer function can be converted into state-space form (note: the realization is not unique). For a general $n^{th}$-order system:

$$\frac{Y(s)}{U(s)} = \frac{b_{n-1}s^{n-1} + \dots + b_1 s + b_0}{s^n + a_{n-1}s^{n-1} + \dots + a_1 s + a_0}$$



This can be converted into the **phase variable** (or controllable canonical) form. The state matrices are:

$$A = \begin{bmatrix} 0 & 1 & 0 & \dots & 0 \\ 0 & 0 & 1 & \dots & 0 \\ \vdots & \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & 0 & \dots & 1 \\ -a_0 & -a_1 & -a_2 & \dots & -a_{n-1} \end{bmatrix} \quad B = \begin{bmatrix} 0 \\ 0 \\ \vdots \\ 0 \\ 1 \end{bmatrix}$$



$$C = \begin{bmatrix} b_0 & b_1 & b_2 & \dots & b_{n-1} \end{bmatrix} \quad D = [0]$$



(Note: $D$ is non-zero only if the order of the numerator and denominator are equal).

Example:

For the transfer function $\frac{Y(s)}{U(s)} = \frac{s+3}{s^2+10s+24}$:

- $a_0 = 24$, $a_1 = 10$
    
- $b_0 = 3$, $b_1 = 1$
    
    The state-space matrices are:
    
    $A = \begin{bmatrix} 0 & 1 \\ -24 & -10 \end{bmatrix}$, $B = \begin{bmatrix} 0 \\ 1 \end{bmatrix}$, $C = \begin{bmatrix} 3 & 1 \end{bmatrix}$, $D = 0$.
    

## Key Concepts

### Choosing State Variables

There are several guidelines for choosing state variables:

1. They should appear as derivatives in the system's differential equations.
    
2. The number of state variables is typically equal to the order of the system's overall differential equation.
    
3. The number of state variables is equal to the number of independent energy storage elements in the system.
    
    - **Electrical:** Current in an inductor ($I_L$) , Voltage across a capacitor ($V_C$).
        
    - **Mechanical:** Positions and velocities.
        

### Stability

- The poles of a system are the roots of the characteristic equation $det(sI - A) = 0$.
    
- These roots are also the **eigenvalues** of the system matrix $A$.
    
- Therefore, the stability of a continuous-time LTI system can be determined by inspecting the eigenvalues of $A$. The system is stable if all eigenvalues have a negative real part.
    

### Discrete-Time State Space

The state-space representation can also be formulated for discrete-time systems, which is useful for digital control.

- **State Equation:** $\mathbf{x}_{k+1} = \Phi \mathbf{x}_k + \Gamma \mathbf{u}_k$ 
    
- **Output Equation:** $\mathbf{y}_k = C \mathbf{x}_k + D \mathbf{u}_k$ 
    

Where:

- $k$ is the discrete time step.
    
- $\mathbf{x}_{k+1}$ is the next state.
    
- $\Phi$ is the **state transition matrix**(related to $A$ by $\Phi = e^{A\Delta T}$).
    
- $\Gamma$ is the **input distribution matrix**.
    

### Simulation in MATLAB

MATLAB provides tools to create, convert, and simulate state-space models.

- `sys = ss(A, B, C, D)`: Creates a continuous-time state-space model object.
    
- `step(sys)`: Plots the step response of the system.
    
- `lsim(sys, u, t)`: Simulates the system's response to a general input vector `u` over a time vector `t`.
    
- `sys_d = c2d(sys, Ts)`: Converts a continuous-time model `sys` to a discrete-time model `sys_d` with sample time `Ts`.
    
- `sys_tf = tf(sys)`: Converts a state-space model `sys` into an equivalent transfer function model82.