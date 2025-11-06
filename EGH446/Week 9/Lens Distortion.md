#Cameras #Vision #Models

No lens is perfect, especially low-cost lenses. Imperfections result in **geometric distortions**, which displace pixels from their correct locations. This is a major problem for robotic applications.

Geometric distortion has two main components: radial and tangential.

## 1. Radial Distortion
This distortion is caused by the shape of the lens and is more significant than tangential distortion.

* **Barrel Distortion**: Magnification *decreases* with distance from the center (the principal point). This causes straight lines near the edge of the image to curve *outward*.
* **Pincushion Distortion**: Magnification *increases* with distance from the center. This causes straight lines near the edge to curve *inward*.

## 2. Tangential Distortion
* This occurs when the lens and the image sensor are not perfectly parallel.
* It is generally less significant than radial distortion.

**Camera calibration** is the process used to measure and correct for these distortions.