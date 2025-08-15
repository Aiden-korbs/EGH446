## Role of Guidance
Takes a path or waypoint list and computes desired states for the controller.

## Common Guidance Laws

### Pure Pursuit
- Selects a “look-ahead” point on the path.
- Steers towards it.
- Simple and robust but can overshoot at high speeds.

### Proportional Navigation (PN)
- Often used in missile guidance.
- Control law based on closing velocity and line-of-sight rate.

### Waypoint Navigation
- Sequentially visit a list of waypoints.
- Requires path smoothing to avoid sharp turns.

### Line-of-Sight Guidance
- Keeps the vehicle on a straight line between waypoints.

## Example Equation (Line-of-Sight)
$$
\psi_{\text{cmd}} = \arctan2(y_{\text{wp}} - y, x_{\text{wp}} - x)
$$
where $(x_{\text{wp}}, y_{\text{wp}})$ is the waypoint position.
