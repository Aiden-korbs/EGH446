## GPS Segments
The GPS system consists of three segments:
1.  **Space Segment**: The 30+ satellites in medium Earth orbit.
2.  **Control Segment**: Ground stations that monitor and maintain the satellites.
3.  **User Segment**: The GPS receivers used for navigation.


## Principle of Trilateration
GPS is based on satellite ranging.
* A receiver estimates its distance from a satellite by measuring the time it takes a radio signal to travel from the satellite to the receiver.
* **Distance = Speed of Light × Time**.

The position is found by trilateration:
* **1 Satellite**: Narrows your position to a sphere with a radius equal to your distance from that satellite.
* **2 Satellites**: Narrows your position to the intersection of two spheres, which is a circle.
* **3 Satellites**: Narrows your position to the intersection of three spheres, which results in two possible points. One point is usually impossible (e.g., far off in space), so this can be enough to determine position.
* **4 Satellites**: Four satellites are generally best and necessary. The fourth satellite is used to solve for the receiver's clock error, which is a critical unknown.

## Navigation Message
Each satellite transmits a navigation message (50bps) that contains:
* Time of transmission.
* Clock correction data.
* **Ephemeris & Almanac**: This is the precise orbital information the receiver uses to calculate the satellite's position.
* **Ionospheric Delay Model**: Coefficients to help correct for atmospheric errors.

## Coordinate System
GPS receivers calculate position in **Earth-Centered, Earth-Fixed (ECEF)** coordinates (X, Y, Z). This is then converted by the receiver into Geodetic Latitude, Longitude, and Altitude for practical use.