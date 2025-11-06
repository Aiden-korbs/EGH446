# The Role of the C Matrix as a "Selector"

A key concept in state-space is understanding what the **C matrix** (the output matrix) does.

The output equation is:
$$
\mathbf{y} = C\mathbf{x} + D\mathbf{u}
$$
Think of the $C$ matrix as a **"selector"** or **"mixer"** that defines what you *see* as the final output. The state vector $\mathbf{x}$ contains all the internal states of the system (e.g., position, velocity, current, voltage), but you may only be interested in *one* of them as your output.

### Case 1: SISO System (like Example 2)

In our second example, we had a $2 \times 1$ state vector $\mathbf{x} = \begin{bmatrix} x_1 \\ x_2 \end{bmatrix}$ but a $1 \times 1$ output $y$.

* **$C = \begin{bmatrix} 1 & 0 \end{bmatrix}$**
* **Output Equation:** $y = \begin{bmatrix} 1 & 0 \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \end{bmatrix} = (1 \cdot x_1) + (0 \cdot x_2) = x_1$
* **Meaning:** This $C$ matrix *selects* only the first state $x_1$ as the output and *ignores* (multiplies by zero) the second state $x_2$. This is why the final transfer function calculation "cancelled" or ignored the bottom row of the $(sI-A)^{-1}B$ vector.

### Case 2: MIMO System (like Example 3)

In our third example, we had a $2 \times 1$ state vector $\mathbf{x} = \begin{bmatrix} x_1 \\ x_2 \end{bmatrix}$ and a $2 \times 1$ output vector $\mathbf{y} = \begin{bmatrix} y_1 \\ y_2 \end{bmatrix}$.

* **$C = \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}$** (The Identity Matrix)
* **Output Equation:** $\begin{bmatrix} y_1 \\ y_2 \end{bmatrix} = \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix} \begin{bmatrix} x_1 \\ x_2 \end{bmatrix} = \begin{bmatrix} (1x_1 + 0x_2) \\ (0x_1 + 1x_2) \end{bmatrix} = \begin{bmatrix} x_1 \\ x_2 \end{bmatrix}$
* **Meaning:** This $C$ matrix defines two outputs:
    1.  $y_1$ is *selected* to be state $x_1$.
    2.  $y_2$ is *selected* to be state $x_2$.
* Since $C$ was the identity matrix, it *selected everything* and nothing was "cancelled" or ignored. The full $2 \times 2$ matrix from $(sI-A)^{-1}B$ was passed through to the final answer.

**Conclusion:** The mathematics for SISO and MIMO conversions are identical. The only difference is the *dimensions* of the matrices. The $C$ matrix determines which states (or combinations of states) are passed to the output.