### Objective

Convert raw IMU measurements into navigation-frame position and orientation estimates.
### Step 1: **Attitude Update**

Update the orientation matrix using angular velocity:
$$
C^n_b(t) = \text{Update}(C^n_b(t-1), \vec{\omega}_b)
$$
Where:
$$C^n_b = \text{rotation matrix from body to navigation frame} $$
$$\vec{\omega}_b = \text{angular velocity in body frame}$$  
- Integration method depends on representation (DCM, Euler, quaternions)

---

### Step 2: **Transform Specific Forces**

Convert accelerometer measurements to navigation frame:

$$
\vec{f}_n = C^n_b \cdot \vec{f}_b + \vec{g}_n
$$


---

### Step 2: **Transform Specific Forces**

Convert accelerometer data from body frame to navigation frame:

- Transform specific force:     $$vec{f}_n = C^n_b \cdot \vec{f}_b + \vec{g}_n$$  Where:   $$ \vec{f}_b = \text{measured specific force in body frame}$$   $$ C^n_b = \text{rotation matrix from body to navigation frame}$$   $$vec{g}_n = \text{gravity vector in navigation frame}$$

---

### Step 3: **Velocity Update**

Integrate acceleration to obtain velocity:

- Velocity update:     $$\vec{v}_k = \vec{v}_{k-1} + \vec{a}_k \cdot \Delta t $$

---

### Step 4: **Position Update**

Integrate velocity to obtain position:

- Position update:     $$\vec{P}_k = \vec{P}_{k-1} + \vec{v}_k \cdot \Delta t $$