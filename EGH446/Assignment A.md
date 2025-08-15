## **EGH446 – Part A Cheat Sheet**

### **Core Goal**

- Design a **guidance subsystem** for an autonomous vehicle (quad rotor or ground robot) to:
    
    1. Follow an **optimal** ordered sequence of **10 random waypoints** (x, y ∈ [−500, 500] m).
        
    2. Use **state estimation/filtering** to handle noisy position & heading.
        
    3. Tune controllers for **minimum mission time** and accurate tracking.
        

---

## **Required Subsystems**

1. **Waypoint Generation & Optimisation**
    
    - Generate random waypoints with `randi([-500 500], 10, 2)`.
        
    - Store as struct:
        
        ```matlab
        waypoints.x = ...
        waypoints.y = ...
        ```
        
    - Apply ordering algorithm (e.g., nearest neighbour, TSP solver).
        
    - Optimise to minimise travel distance.
        
2. **Guidance & Control**
    
    - **Heading to waypoint approach**:
        
        - Compute target heading `α` between current position & waypoint.
            
        - Error: `e = k * (α - ψ)` (wrap angles properly).
            
        - Use this error as turn-rate command.
            
    - Switch to next waypoint when within capture radius.
        
    - Stop after last waypoint (trigger stop block).
        
3. **State Estimation / Filtering**
    
    - Handle:
        
        - Position noise: σ²ₓ = σ²ᵧ = 0.1 m.
            
        - Heading noise: σ²_θ = 2°.
            
    - Use **Kalman Filter** or similar to smooth state estimates.
        

---

## **Performance Metrics**

- **Total Mission Time** (seconds) – aim to minimise.
    
- **Average Waypoint Capture Error** (m) – distance between vehicle at capture and waypoint.
    
- **RMS Cross-Track Error** – deviation from path.
    

---

## **Controller Tuning**

- Use **PID** for heading & speed control:
    
    - **P** → reduces steady-state error.
        
    - **I** → removes residual bias.
        
    - **D** → dampens oscillations.
        
- Empirical tuning process:
    
    1. Increase P until oscillations start.
        
    2. Add D to smooth.
        
    3. Add I to remove steady error.
        

---

## **MATLAB / Simulink Steps**

1. **Select Vehicle**: Quadrotor or ground robot.
    
2. **Access Vehicle State**:
    
    ```matlab
    x, y, ψ  % ground
    x, y, yaw (ψ)  % quad
    ```
    
3. **Calculate Target Heading**:
    
    ```matlab
    dx = wpt.x - pos.x;
    dy = wpt.y - pos.y;
    α = atan2(dy, dx);
    ```
    
4. **Angle Wrapping**:
    
    - Keep in range [−π, π] or [−180°, 180°].
        
    - Prevent large unnecessary turns.
        
5. **Simulink Functions**:
    
    - Use MATLAB Function blocks.
        
    - Store waypoint index as `persistent` variable.
        
6. **Stop Simulation**:
    
    - Output `1` to stop block at final waypoint.
        

---

## **Report Checklist (Individual)**

- **Subsystem Block Diagram** – Inputs, outputs, signals.
    
- **Guidance & Control Description** – Controller type, gains, logic flow.
    
- **Performance Results** – Time, capture error, RMS cross-track error.
    
- **Waypoint Optimisation Method** – Algorithm, criteria.
    
- **State Estimation Method** – Filter type, parameters.
    

---

## **Extra Tips**

- Keep speed constant if time minimisation is key, but balance with turning performance.
    
- Tight capture radius = better accuracy, longer time.
    
- Wide capture radius = faster time, less accuracy.
    
- Debug using Simulink Diagnostic Viewer.
    
- Always check angle wrapping — it’s the #1 cause of endless spinning.
    

---

If you want, I can also make a **one-page visual flowchart** of this so you can literally follow it step-by-step when implementing. That would make it even easier to use mid-coding.  
Do you want me to prepare that?