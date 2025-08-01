### Constant Bias
- Fixed output offset when there is no actual motion
- Causes linear error growth over time when integrated
### White Noise / Angle Random Walk
- Thermo-mechanical noise appearing as zero-mean white noise
- Integration causes error to grow with the square root of time
### Flicker Noise / Bias Stability
- Low-frequency noise (1/f spectrum)
- Causes slow variations in bias
- Modelled as a bias random walk
### Temperature Effects
- Temperature changes affect sensor readings and bias
- Not accounted for in standard bias stability specs
### Calibration Errors
- Include:
    - Misalignment of sensor axes
    - Scale factor errors  
    - Nonlinear response
- Often observable only during dynamic motion