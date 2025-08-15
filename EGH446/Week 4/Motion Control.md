## Purpose
Motion control ensures that a vehicle or robotic system moves according to a desired trajectory, path, or state.

Key objectives:
- Accuracy in tracking position, velocity, and acceleration.
- Stability under varying conditions.
- Robustness to disturbances and model uncertainties.

---

## Categories of Motion Control

### 1. Position Control
- Maintains or moves to a target position.
- Common in robotic arms, CNC machines, and pan–tilt cameras.

Equation form:
$$
e(t) = x_{\text{desired}}(t) - x(t)
$$
where $e(t)$ is the position error.

---

### 2. Velocity Control
- Regulates speed rather than position.
- Useful for conveyor belts, wheel speed control, and cruise control.

---

### 3. Acceleration Control
- Direct control of acceleration for smoothness and responsiveness.
- Often implemented in higher-performance robotic and aerospace systems.

---

## Control Strategies

### Proportional–Integral–Derivative (PID)
Most common feedback controller:
$$
u(t) = K_P e(t) + K_I \int e(t) \, dt + K_D \frac{de(t)}{dt}
$$
- $K_P$: proportional gain – corrects present error.
- $K_I$: integral gain – removes steady-state error.
- $K_D$: derivative gain – anticipates future error.

---

### Feedforward Control
- Uses a model of the system to compute the control input directly from the desired trajectory.
- Often combined with feedback for better performance.

---

### Model Predictive Control (MPC)
- Uses an internal model to predict future states.
- Optimizes control input over a prediction horizon.
- Handles constraints on inputs and states.

---

## Tracking in Different Frames
- **Inertial frame** – fixed reference.
- **Body frame** – attached to the moving vehicle.
- Controllers may need coordinate transformations between frames.

---

## Path Following vs. Trajectory Tracking
- **Path following**: Stay on a geometric path without strict timing.
- **Trajectory tracking**: Follow both path and timing profile.

---

## Applications
- Autonomous ground vehicles
- UAV flight control
- Robotic manipulators
- Industrial automation

---

_See also: [[Guidance]], [[PGNC Overview]]_
