#Sensors #Lidar #Laser

## What is a Laser Scanner?
* **LASER** stands for **Light Amplification by the Stimulated Emission of Radiation**.
* A laser rangefinder emits a narrow laser beam to determine the distance to an object.
* It creates an extremely dense and accurate point cloud model of a surface.
* Like Lidar, each point in the cloud has X, Y, Z, and Intensity (I) measurements.

## Measurement Types
1.  **Pulsed Time of Flight (ToF)**
    * This is the most common method.
    * It sends a short laser pulse and measures the **round-trip time** `t` for the pulse to reflect off the target and return.
    * The distance is calculated as: **`range = (c × t) / 2`**, where `c` is the speed of light.
    

2.  **Phase-Shift**
    * This method transmits a continuous wave and measures the **phase difference** between the transmitted signal and the received signal.
    * This phase shift is proportional to the time of flight `tL`.
    

## Scanners for Robotics
* Smaller, 2D or 3D scanners are common on mobile or aerial robots (e.g., Hokuyo URG).
* These can provide a 240° arc of range data at high speed.
* **Typical Considerations**:
    * **Size, Weight, Power (SWaP)**.
    * **Interfaces**: How easy is it to read the data (e.g., USB, RS-232)?.
    * **Data Amount**: How much data is produced (storage and processing).
    * **Sampling Time**: How fast does it produce information?.
    * **Resolution vs. Noise**: The trade-off between data quality and data storage/processing.