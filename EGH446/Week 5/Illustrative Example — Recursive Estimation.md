## Simplest Case
- Estimating a constant: $x_k = c$
- Measurement: $y_k = x_k + w_k$

Recursive estimator:
$$
\hat{x}_k = \hat{x}_{k-1} + \frac{1}{k} \left( y_k - \hat{x}_{k-1} \right)
$$

Equivalent to a special case of KF with:
$$
A_k = 1, \quad H_k = 1
$$
