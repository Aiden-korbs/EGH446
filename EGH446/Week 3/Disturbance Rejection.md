## What is a disturbance?
An unwanted input that pushes the system away from its desired behavior.

Examples:
- Wind gusts on a UAV  
- Load torque changes on a motor  
- Waves hitting a boat  

## Strategies
1. **Estimate & Cancel** – Model or measure the disturbance and subtract it from the control input.  
2. **Robust Design** – Design the controller so that the disturbance has minimal effect on the output.

## Cascade Control
- Uses **two loops**:
  - Inner loop (fast) for quick disturbance rejection.
  - Outer loop (slower) for overall performance.
- Rule of thumb: inner loop bandwidth ≥ 5× outer loop.

## Example
Water tank with inlet pressure disturbances:
- Inner loop maintains inlet flow.
- Outer loop maintains water level.

## Feedforward Control
If the disturbance is measurable, we can add a feedforward term:
$$
u = u_{\text{feedback}} + u_{\text{feedforward}}
$$
This can cancel the disturbance before it affects the system.
