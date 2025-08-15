## Why frames matter
Measurements depend on the reference frame. To compare or combine data (from different observers/sensors), we must transform between frames.

## Common frames
- **World/Global (GCS/W):** Fixed reference for positions and attitudes.
- **Body (B):** Attached to the vehicle (aligned with roll/pitch/yaw axes).
- **Sensor (S):** Attached to each sensor (origin at sensor COM).
- **Manipulation:** Base and Tool frames (for robots/end-effectors).

## Transformations (concept)
- A 3D pose transform combines **rotation** (3×3 matrix) and **translation** (3×1).
- Rotation representations:
  - **Rotation matrix** \(R\): orthonormal, det=+1.
  - **Cardan/Euler angles**: ordered axis rotations (be mindful of sequence/non-commutativity).
  - **Quaternions** (noted for completeness): robust for 3D composition.

## Practical notes
- Always record **which frame** a vector/pose is expressed in.
- Keep a consistent **axis convention** (match course/industry standard).
- Sequence matters: $\text{rot}(Z)\text{rot}(Y) \neq \text{rot}(Y)\text{rot}(Z)$.

_See also: [Inertial Sensors.md] for body↔navigation use in INS._
