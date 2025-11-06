## IMU vs INS
- **IMU:** accelerometers + gyroscopes (sometimes magnetometers); measures specific force and angular rate.
- **INS:** IMU + mechanisation; integrates rates/accelerations to estimate orientation, velocity, and position (drifts over time).

## Configurations
- **Stable platform:** sensors isolated from vehicle rotation (aligned with navigation frame).
- **Strapdown (common):** sensors fixed to body; integrate gyro rates to track attitude; rotate accelerations into navigation frame; integrate to velocity/position.

## Sensors
- **Gyroscopes:** measure angular rate (deg/s, rad/s); types: mechanical, optical, MEMS.
- **Accelerometers:** measure specific force; integrate (w/ gravity handling) to get acceleration in nav frame.

## Error sources (typical)
- **Bias / Bias stability (flicker noise):** creates drift after integration.
- **Angle random walk / white noise:** noisy outputs, accumulate with integration.
- **Temperature effects:** bias and scale factor vary with temperature.
- **Alignment and scale-factor errors:** miscalibration across axes.

## Key implications
- INS alone **drifts**; combine with exteroceptive sensors (e.g., GNSS, vision) via estimation (e.g., Kalman filters).
- Maintain accurate frame definitions (body↔nav) and temperature compensation.

_See also: [[Coordinate Systems]] for frames used in INS._
