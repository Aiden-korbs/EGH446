#GPS #Sensors #Error

Several factors degrade the accuracy of a GPS position:

* **Receiver and satellite clock errors**.
* **Atmospheric delays** (Ionosphere and Troposphere).
* **Multipath** (signal reflections).
* **Receiver noise**.
* **Elevation mask** (affects which satellites are used).

## Atmospheric Errors
* **Ionosphere**: A region of ionized particles (50-1000 km) that causes signal degradation, group delay (range error), and carrier phase advance. Dual-frequency (L1/L2) receivers can measure and correct for this.
* **Troposphere**: The "dry atmosphere" and water vapor (0-50 km) cause signal refraction. This delay is mitigated using models or differential positioning.

## Multipath Error
* This occurs when the signal reaches the antenna via two or more paths, typically by reflecting off surfaces.
* The reflected path is longer, which confuses the receiver's time calculation.
* The primary defense is to locate the antenna away from reflectors.


## Elevation Mask
* Satellites at low elevations (close to the horizon) are less reliable.
* Their signals travel through more atmosphere and are more prone to multipath.
* Receivers use a software "mask" to omit satellites below a certain angle (e.g., 5-15 degrees) from the solution.

## Dilution of Precision (DOP)
* **DOP** is a confidence factor in the accuracy of the position fix.
* It depends purely on the **geometry** of the satellites in view.
* **Good DOP (Low value)**: Satellites are widely spaced across the sky. The intersection of the spheres is small and precise.
* **Poor DOP (High value > 6)**: Satellites are clustered close together. The intersection is large and uncertain.
* Common DOP values include HDOP (Horizontal), VDOP (Vertical), and PDOP (Position).