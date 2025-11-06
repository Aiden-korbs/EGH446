## PGNC Subsystems
The PGNC (Planning, Guidance, Navigation, Control) approach breaks an automation platform into four key subsystems:
* **Navigation**: "Where am I?"
* **Route and Path Planning**: "What route and path should I travel?"
* **Guidance**: "What trajectory should I travel to achieve the desired path?"
* **Control**: "What actuations stabilize the platform whilst achieving this trajectory?"



This system relies on **time scale separation**, meaning the time constants between successive cascade systems (like control and guidance) should differ by a factor of ~5.

### Planning Abstraction
Planning itself can be split into two phases:

1.  **Pre Planning (Offline)**: Assumes an idealized platform. This includes (1) Route planning (sequence of waypoints) and (2) Path planning (path between waypoints).
2.  **Dynamic Planning (Online)**: Updates the path based on current location, but the overall route plan is typically not changed.