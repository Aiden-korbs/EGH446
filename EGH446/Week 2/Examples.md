$$\ddot{y}(t) + 5\dot{y}(t) + 6y(t) = u(t)$$
### Step 1: Identify the Order

This is a **2nd-order** ODE (indicated by the $\ddot{y}(t)$ term). Therefore, we will need **2** state variables.
### Step 2: Choose the State Variables

We will use the "phase variable" form, where the state variables are the output and its derivatives, up to the $(n-1)^{th}$ derivative1.

- Let $x_1(t) = y(t)$ (the output)
    
- Let $x_2(t) = \dot{y}(t)$ (the first derivative of the output)

Our state vector is $\mathbf{x} = \begin{bmatrix} x_1 \\ x_2 \end{bmatrix}$. The input is $u(t)$.

### Step 3: Form the State Equations ($\dot{\mathbf{x}} = A\mathbf{x} + B\mathbf{u}$)

We need to find the equations for $\dot{x}_1$ and $\dot{x}_2$.

Equation for $\dot{x}_1$:

The derivative of $x_1$ is $\dot{x}_1 = \frac{d}{dt}(y(t)) = \dot{y}(t)$.

By our definition in Step 2, $\dot{y}(t) = x_2$.

- Therefore: **$\dot{x}_1 = x_2$**
    
Equation for $\dot{x}_2$:

The derivative of $x_2$ is $\dot{x}_2 = \frac{d}{dt}(\dot{y}(t)) = \ddot{y}(t)$.

We find $\ddot{y}(t)$ by rearranging the original ODE:

1. **Original ODE:** $\ddot{y}(t) + 5\dot{y}(t) + 6y(t) = u(t)$
    
2. **Solve for $\ddot{y}(t)$:** $\ddot{y}(t) = -6y(t) - 5\dot{y}(t) + u(t)$
    
3. **Substitute state variables:** Replace $y(t)$ with $x_1$ and $\dot{y}(t)$ with $x_2$.
    

- Therefore: **$\dot{x}_2 = -6x_1 - 5x_2 + u(t)$**
    

### Step 4: Define the Output Equation ($\mathbf{y} = C\mathbf{x} + D\mathbf{u}$)

The output $y(t)$ is what we are interested in.

1. **Define output:** $y(t)$
    
2. **Substitute state variables:** From Step 2, we defined $y(t) = x_1$.
    
3. **Write in full form:** $y(t) = (1 \cdot x_1 + 0 \cdot x_2) + (0 \cdot u(t))$
    

### Step 5: Assemble the State-Space Matrices

Now we assemble the equations from Steps 3 and 4 into the four state-space matrices ($A, B, C, D$).

**From the State Equations (Step 3):**

$$\begin{aligned} \dot{x}_1 &= 0x_1 + 1x_2 + 0u(t) \\ \dot{x}_2 &= -6x_1 - 5x_2 + 1u(t) \end{aligned}$$

$$\implies \begin{bmatrix} \dot{x}_1 \\ \dot{x}_2 \end{bmatrix} = \begin{bmatrix} 0 & 1 \\ -6 & -5 \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \end{bmatrix} + \begin{bmatrix} 0 \\ 1 \end{bmatrix} u(t)$$

This gives us:

- $A = \begin{bmatrix} 0 & 1 \\ -6 & -5 \end{bmatrix}$
    
- $B = \begin{bmatrix} 0 \\ 1 \end{bmatrix}$
    

**From the Output Equation (Step 4):**

$$y(t) = \begin{bmatrix} 1 & 0 \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \end{bmatrix} + [0] u(t)$$

This gives us:

- $C = \begin{bmatrix} 1 & 0 \end{bmatrix}$
    
- $D = 0$


---
## Example 2: SISO State-Space to Transfer Function
convert this state-space model into a transfer function, 
![[Pasted image 20251104140353.png|300]]
$$G(s) = C(sI - A)^{-1}B + D$$

First, let's identify your matrices from the image:

- $A = \begin{bmatrix} -4 & -1 \\ 3 & -1 \end{bmatrix}$
    
- $B = \begin{bmatrix} 1 \\ 1 \end{bmatrix}$
    
- $C = \begin{bmatrix} 1 & 0 \end{bmatrix}$
    
- $D = 0$ (The output equation $y=Cx$ has no $Du$ term)
    

---

### Step 1: Calculate $(sI - A)$

$sI - A = s\begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix} - \begin{bmatrix} -4 & -1 \\ 3 & -1 \end{bmatrix}$

$sI - A = \begin{bmatrix} s & 0 \\ 0 & s \end{bmatrix} - \begin{bmatrix} -4 & -1 \\ 3 & -1 \end{ReadMe>
$sI - A = \begin{bmatrix} s+4 & 1 \\ -3 & s+1 \end{bmatrix}$

---

### Step 2: Find the inverse, $(sI - A)^{-1}$

The inverse of a 2x2 matrix $\begin{bmatrix} a & b \\ c & d \end{bmatrix}$ is $\frac{1}{ad-bc} \begin{bmatrix} d & -b \\ -c & a \end{bmatrix}$.

- Determinant: $det(sI - A)$
    
    $det = (s+4)(s+1) - (1)(-3)$
    
    $det = (s^2 + 5s + 4) + 3$
    
    $det = s^2 + 5s + 7$
    
- Inverse:
    
    $(sI - A)^{-1} = \frac{1}{s^2 + 5s + 7} \begin{bmatrix} s+1 & -1 \\ 3 & s+4 \end{bmatrix}$
    

---

### Step 3: Calculate $G(s) = C \cdot (sI - A)^{-1} \cdot B$

We can group the multiplication as $C \cdot [(sI - A)^{-1} \cdot B]$. Let's do the part in the brackets first.

- $(sI - A)^{-1} \cdot B$:
    
    $\frac{1}{s^2 + 5s + 7} \begin{bmatrix} s+1 & -1 \\ 3 & s+4 \end{bmatrix} \begin{bmatrix} 1 \\ 1 \end{bmatrix} = \frac{1}{s^2 + 5s + 7} \begin{bmatrix} (s+1)(1) + (-1)(1) \\ (3)(1) + (s+4)(1) \end{bmatrix}$
    
    $= \frac{1}{s^2 + 5s + 7} \begin{bmatrix} s+1-1 \\ 3+s+4 \end{bmatrix} = \frac{1}{s^2 + 5s + 7} \begin{bmatrix} s \\ s+7 \end{bmatrix}$
    
- $C \cdot [ (sI - A)^{-1} B ]$:
    
    $G(s) = \begin{bmatrix} 1 & 0 \end{bmatrix} \left( \frac{1}{s^2 + 5s + 7} \begin{bmatrix} s \\ s+7 \end{bmatrix} \right)$
    
    $G(s) = \frac{1}{s^2 + 5s + 7} \left( \begin{bmatrix} 1 & 0 \end{bmatrix} \begin{bmatrix} s \\ s+7 \end{bmatrix} \right)$
    
    $G(s) = \frac{1}{s^2 + 5s + 7} \left( (1)(s) + (0)(s+7) \right)$
    
    $G(s) = \frac{s}{s^2 + 5s + 7}$
    

---

### Step 4: Add $D$

$G(s) = G(s) + D$

$G(s) = \frac{s}{s^2 + 5s + 7} + 0$

### Final Answer

The transfer function $G(s)$ is:

$$G(s) = \frac{s}{s^2 + 5s + 7}$$

---
## Example 3: MIMO State-Space to Transfer Function Matrix

This converts a Multi-Input, Multi-Output (MIMO) system into its equivalent transfer function matrix.

The formula is the same, but the matrices have different dimensions:
$$
H(s) = C(sI - A)^{-1}B + D
$$

### Step 1: Identify $A, B, C, D$ Matrices

- $A = \begin{bmatrix} -1 & -1 \\ 6.5 & 0 \end{bmatrix}$
- $B = \begin{bmatrix} 1 & 1 \\ 1 & 0 \end{bmatrix}$
- $C = \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}$
- $D = \begin{bmatrix} 0 & 0 \\ 0 & 0 \end{bmatrix}$

---

### Step 2: Calculate $(sI - A)$

$sI - A = s\begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix} - \begin{bmatrix} -1 & -1 \\ 6.5 & 0 \end{bmatrix}$
$sI - A = \begin{bmatrix} s+1 & 1 \\ -6.5 & s \end{bmatrix}$

---

### Step 3: Find the inverse, $(sI - A)^{-1}$

1.  **Determinant:**
    $det(sI - A) = (s+1)(s) - (1)(-6.5) = s^2 + s + 6.5$

2.  **Inverse:**
    $(sI - A)^{-1} = \frac{1}{s^2 + s + 6.5} \begin{bmatrix} s & -1 \\ 6.5 & s+1 \end{bmatrix}$

---

### Step 4: Calculate $H(s) = C \cdot (sI - A)^{-1} \cdot B$

We will multiply $C \cdot [(sI - A)^{-1} \cdot B]$.

**4.1: $(sI - A)^{-1} \cdot B$**
$\left( \frac{1}{s^2 + s + 6.5} \begin{bmatrix} s & -1 \\ 6.5 & s+1 \end{bmatrix} \right) \cdot \begin{bmatrix} 1 & 1 \\ 1 & 0 \end{bmatrix}$
$= \frac{1}{s^2 + s + 6.5} \begin{bmatrix} (s)(1) + (-1)(1) & (s)(1) + (-1)(0) \\ (6.5)(1) + (s+1)(1) & (6.5)(1) + (s+1)(0) \end{bmatrix}$
$= \frac{1}{s^2 + s + 6.5} \begin{bmatrix} s-1 & s \\ s+7.5 & 6.5 \end{bmatrix}$

**4.2: $C \cdot [\text{result from 4.1}]$**
$H(s) = \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix} \cdot \left( \frac{1}{s^2 + s + 6.5} \begin{bmatrix} s-1 & s \\ s+7.5 & 6.5 \end{bmatrix} \right)$
Since $C$ is the identity matrix, the result is unchanged:
$H(s) = \frac{1}{s^2 + s + 6.5} \begin{bmatrix} s-1 & s \\ s+7.5 & 6.5 \end{bmatrix}$

---

### Final Answer

The transfer function matrix $H(s) = \begin{bmatrix} H_{11}(s) & H_{12}(s) \\ H_{21}(s) & H_{22}(s) \end{bmatrix}$ is:
$$
H(s) = \begin{bmatrix}
\frac{s-1}{s^2 + s + 6.5} & \frac{s}{s^2 + s + 6.5} \\
\frac{s+7.5}{s^2 + s + 6.5} & \frac{6.5}{s^2 + s + 6.5}
\end{bmatrix}
$$
Where:
- $H_{11}(s) = \frac{s-1}{s^2 + s + 6.5}$
- $H_{12}(s) = \frac{s}{s^2 + s + 6.5}$
- $H_{21}(s) = \frac{s+7.5}{s^2 + s + 6.5}$
- $H_{22}(s) = \frac{6.5}{s^2 + s + 6.5}$
