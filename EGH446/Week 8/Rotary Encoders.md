#Sensors #Encoders

## Purpose
A **rotary encoder** is a device that tracks the movement (position and/or speed) of a motor shaft.

## Sensor Types
Encoders can be classified by their sensing technology:
* **Mechanical**: Electrical contacts physically connect and disconnect to create high/low electrical pulses.
* **Photoelectric (Optical)**: These are smaller and can operate much faster. A light (emitter) shines through a disc with transparent and opaque sections. A receiver on the other side reads the light as a pattern of high/low pulses.

## Output Types
Encoders are also classified by their output method:
* **Incremental Encoders**:
    * Provide pulses that indicate *relative* movement (e.g., "moved 5 degrees").
    * They are usually cheaper for the same resolution.
    * They can provide both speed and position information.
    * **Disadvantage**: They must be "homed" (moved to a known zero position) after a power loss to recalibrate their count.
* **Absolute Encoders**:
    * Use a disc with a unique pattern (digital word) for every position.
    * **Advantage**: They are able to provide absolute positional information *at any time*, even immediately on power-up.