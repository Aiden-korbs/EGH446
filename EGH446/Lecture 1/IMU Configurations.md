### Stable Platform Configuration
- IMU sensors mounted on a gimballed platform
- Platform remains aligned with navigation frame
- Mechanically isolates sensors from body rotation
- Less common today due to size, weight, and complexity

### Strapdown Configuration
- Sensors rigidly attached to the moving body
- Measurements in body frame
- Orientation computed via integration of gyroscope data
- Accelerometer data transformed using computed orientation
- Most modern systems use strapdown configurations