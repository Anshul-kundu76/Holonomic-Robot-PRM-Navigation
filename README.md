# Holonomic-Robot-PRM-Navigation
MATLAB simulation of PRM path planning for a 3-wheeled holonomic robot

# 🌟 Autonomous Navigation for Holonomic Robots: PRM Path Planning in MATLAB

![Demo Animation](images/demo_optimized.gif)  
*Real-time path planning with obstacle avoidance (Click GIF to view full video)*

**Developer**: Anshul Kundu | **M.Tech in Electrical Engineering (V.L.S.I. Design)**  
**Institution**: Indian Institute of Technology (IIT) Jammu  
**GitHub**: [@yourusername](https://github.com/Anshul-kundu76) |   
**Research Areas**: Robotics, Embedded Systems, Autonomous Navigation  

---

## 📌 Table of Contents
1. [Project Overview](#-project-overview)
2. [Technical Specifications](#-technical-specifications)
3. [Mathematical Foundations](#-mathematical-foundations)
4. [Repository Structure](#-repository-structure)
5. [Installation & Usage](#-installation--usage)
6. [Results & Visualizations](#-results--visualizations)
7. [Academic Applications](#-academic-applications)
8. [Future Extensions](#-future-extensions)
9. [License](#-license)
10. [Acknowledgments](#-acknowledgments)

---

## 🔍 Project Overview
This project implements **Probabilistic Roadmap (PRM)** algorithm for autonomous path planning of a 3-wheel holonomic robot in MATLAB. Key features:

- **Omnidirectional Mobility**: True holonomic movement with independent control of translation/rotation
- **Dynamic Obstacle Handling**: Randomized obstacle generation with configurable density
- **Optimized Path Planning**: Euclidean distance-based cost minimization
- **VLSI-Ready**: Modular architecture for potential hardware integration (FPGA/ASIC)

*Developed during my Master's research at IIT Jammu, combining principles from:*  
✅ Robotics & Control Theory  
✅ Algorithm Optimization  
✅ Embedded Systems (VLSI perspective)  

---

## 🛠️ Technical Specifications

### Core Components
| **Component**       | **Implementation Details**               |
|----------------------|------------------------------------------|
| **Path Planning**    | PRM with 500+ node sampling              |
| **Kinematics**       | 3-wheel Jacobian matrix implementation   |
| **Control System**   | PID with tunable parameters (Kp=0.8, Ki=0.1, Kd=0.05) |
| **Visualization**    | MATLAB Robotics Toolbox + Custom Animations |

### System Requirements
```matlab
MATLAB >= R2024b
Toolboxes: Robotics System, Statistics and Machine Learning
Minimum RAM: 8GB (for large obstacle maps)
