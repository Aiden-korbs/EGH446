### IMU (Inertial Measurement Unit)

- Combines:
    - 3-axis accelerometers
    - 3-axis gyroscopes
    - Optionally 3-axis magnetometers
- Provides measurements in the **body frame**
- Reports linear acceleration and angular velocity

### INS (Inertial Navigation System)
- Utilises IMU measurements to estimate:
    - Position
    - Velocity
    - Orientation
- Uses numerical integration (dead reckoning)
- Requires initial position and heading
- Susceptible to cumulative errors (drift)
### Limitations
- Drift increases over time due to integration of noise and bias
- Commonly integrated with GPS or other absolute references