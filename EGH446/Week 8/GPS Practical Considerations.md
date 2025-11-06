#GPS #Sensors #Hardware

## Antenna Type and Placement
* **Antenna Type**:
    * **Patch Antenna**: Most common, small, low power, but has poor multipath rejection.
    * **Choke Ring Antenna**: Large, heavy, high power, but has excellent multipath rejection and accuracy. Used for surveying.
* **Placement**:
    * Must be mounted upright with an **unobstructed view of the sky**.
    * Place away from other electronics to avoid **Electro-Magnetic Interference (EMI)**.
    * A **ground plane** is often used to block signals reflected from below.

## Performance and Accuracy
* **Update Rate**: 1 Hz to 10 Hz is common, but can be 100 Hz+.
* **Lag**: GPS position/velocity is always **delayed/lagged**. It measures where you *were*, not where you are.
* **Standard Accuracy**: 1-10 m horizontally, 3-30 m vertically.
* **Vertical Accuracy**: is ~3 times worse than horizontal due to satellite geometry (all satellites are *above* the receiver). This is why aircraft typically use barometric altimeters for altitude.

## Signal Lock
* **Time to First Fix (TTFF)**: On a fresh startup ("cold start"), a GPS receiver needs time (seconds to minutes) to find the satellites and download the almanac.
* **Signal Fluctuation**: Satellites can be dropped, causing the position estimate to "jump".
* **Visibility**: Signals are poor under trees, in heavy rain/cloud cover, or indoors.

## Output Formats
* **NMEA**: A standard ASCII format for real-time positioning, used to send data from the receiver to another device (like a computer).
* **RINEX**: (Receiver Independent Exchange Format) An ASCII format used for saving raw data for static post-processing and high-accuracy surveying.
* **RTCM**: A binary format used to transmit real-time corrections (DGPS/RTK) from a base station to a rover.