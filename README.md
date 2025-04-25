# 🦾 PRM Path Planning for 3-Wheel Holonomic Robot | MATLAB

![PRM Navigation Demo](images/demo_optimized.gif)  
*Real-time obstacle avoidance with Euclidean cost optimization*

**Developer**: Anshul Kundu | **M.Tech V.L.S.I. Design Engineering**  
**Institution**: Indian Institute of Technology Jammu  
**GitHub**: Anshul-kundu76(https://github.com/Anshul-kundu76)  

---

## 📌 Table of Contents
1. [Project Overview](#-project-overview)
2. [Mathematical Model](#-mathematical-model)
3. [Algorithm Implementation](#-algorithm-implementation)
4. [Installation](#-installation)
5. [Results](#-results)
6. [Future Work](#-future-work)
7. [License](#-license)

---

## 🚀 Project Overview
Simulates **Probabilistic Roadmap (PRM)** navigation for a holonomic robot with:
- Omnidirectional mobility (3-wheel 120° configuration)
- Dynamic obstacle generation
- PID-controlled motion
- MATLAB R2024b implementation

---

## 📐 Mathematical Model

### Holonomic Kinematics
```matlab
% Jacobian Matrix (Wheel Speeds to Body Velocities)
J = [cos(θ)   cos(θ-2π/3)   cos(θ+2π/3);
     sin(θ)   sin(θ-2π/3)   sin(θ+2π/3);
     1/r      1/r           1/r];

% Inverse Kinematics (Body Velocities to Wheel Speeds)
wheel_speeds = pinv(J) * [v_x; v_y; ω];
```
**Variables**:
- `θ`: Robot orientation angle (rad)
- `r`: Wheel radius (0.05m)
- `v_x, v_y`: Linear velocities (m/s)
- `ω`: Angular velocity (rad/s)

### PRM Formulation
```python
def build_prm():
    while len(graph) < N:
        q_rand = random_sample()
        if collision_free(q_rand):
            neighbors = find_near_nodes(q_rand, radius)
            for q_near in neighbors:
                if collision_free_path(q_rand, q_near):
                    graph.add_edge(q_rand, q_near)
```

---

## ⚙️ Algorithm Implementation
### Key MATLAB Functions
1. **PRM Construction**:
   ```matlab
   prm = mobileRobotPRM(map, 500);
   prm.ConnectionDistance = 15;  % Max edge length
   ```

2. **Path Smoothing**:
   ```matlab
   smooth_path = reduce_path_points(path, tolerance=0.1);
   ```

3. **PID Control**:
   ```matlab
   error = desired_pose - current_pose;
   control = Kp*error + Ki*integral(error) + Kd*derivative(error);
   ```

---

## 💻 Installation
```bash
git clone https://github.com/yourusername/holonomic-prm.git
cd holonomic-prm/src
matlab -r "run('main.m')"
```

**Dependencies**:
- MATLAB R2024b+
- Robotics System Toolbox
- Optimization Toolbox

---

## 📊 Results
| Metric               | Value       |
|----------------------|-------------|
| Average Path Length  | 142.3 ± 5.2 units |
| Computation Time     | 2.8 ± 0.3 sec |
| Success Rate         | 92% (100 trials) |

![Path Cost Analysis](images/cost_plot.png)  
*Euclidean vs. Manhattan distance trade-off*

---

## 🔮 Future Work
1. **Hardware Integration**
2. **Multi-Robot Coordination**  
3. **ML-Based Sampling**  

---

## 📜 License
MIT License. See [LICENSE](LICENSE).

---

## 🙏 Acknowledgments
- **Advisor**: Dr. Nalin Kumar Sharma (IIT Jammu)  
- **MATLAB Robotics Toolbox**  
- **V. Sreeraj, G. N. Pillai, and A. J. Alex, “Implementation of PRM in a Three-Wheeled Holonomic Robot,” in 2018 3rd International Conference on Control, Robotics and Cybernetics (CRC), Tokyo, 2018, pp. 70–74. DOI: 10.1109/CRC.2018.00020
![image](https://github.com/user-attachments/assets/79b2f0f3-5611-40ff-a39f-a6345284f9e2)
  
