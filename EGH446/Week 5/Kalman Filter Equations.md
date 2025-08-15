## State-Space Model
**State equation**:
$$
x_{k+1} = A_k x_k + v_k
$$

**Measurement equation**:
$$
y_k = H_k x_k + w_k
$$

Where:
- $v_k \sim \mathcal{N}(0, Q_k)$ (process noise)
- $w_k \sim \mathcal{N}(0, R_k)$ (measurement noise)

---

## Estimation Problem
Given $\bar{x}_0$, estimate $x_k$ using $y_0, \dots, y_k$.

---

## Two-Step Process

### 1. Time Update (Prediction)
$$
\hat{x}^-_k = A_{k-1} \hat{x}_{k-1}
$$
$$
P^-_k = A_{k-1} P_{k-1} A_{k-1}^\top + Q_{k-1}
$$

### 2. Measurement Update (Correction)
$$
K_k = P^-_k H_k^\top \left( H_k P^-_k H_k^\top + R_k \right)^{-1}
$$
$$
\hat{x}_k = \hat{x}^-_k + K_k \left( y_k - H_k \hat{x}^-_k \right)
$$
$$
P_k = \left( I - K_k H_k \right) P^-_k
$$
