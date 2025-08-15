
## What is PGNC?
PGNC = **Planning**, **Guidance**, **Navigation**, **Control**.

### Planning
- Long-term, high-level task generation.
- Produces waypoints, trajectories, or task sequences.

### Guidance
- Converts waypoints or paths into desired states (position, velocity, heading) for the controller.

### Navigation
- Estimates the vehicle’s current state using sensors (IMU, GPS, vision).

### Control
- Applies actuator commands to make the vehicle follow the desired states.

## Levels of Abstraction
- **Mission Level** – What tasks to achieve.
- **Path Level** – Where to go.
- **Control Level** – How to move actuators to achieve the path.

_See also: [[Guidance]], [[Route Planning]]_
