# SO-100 Robot Arm: Sim2Real Deployment

This project focuses on training Reinforcement Learning policies in NVIDIA Isaac Sim/Isaac Lab and deploying them to a physical 6-DOF SO-100 robot arm using the official Hugging Face LeRobot framework.

## Project Structure
- `lerobot/`: Official LeRobot repository for low-level motor control and hardware interfacing.
- `isaac_so_arm101/`: Main simulation project containing URDFs, task configs, and trained policies.
- `isaac_so_arm101/deploy/`: Sim2Real bridge scripts and hardware diagnostic tools.

## Quick Start (Deployment)
To run the trained RL policy on the physical robot:

1. **Activate the environment:**
   ```bash
   conda activate lerobot
   ```

2. **Run the Sim2Real bridge:**
   ```bash
   PYTHONPATH=lerobot:deploy python isaac_so_arm101/deploy/sim2real.py
   ```

## 🔧 Troubleshooting & Calibration
- **Motor Diagnosis**: Use `isaac_so_arm101/deploy/diagnose_motors.py` to scan the bus and check motor health.
- **Port Permissions**: Run `sudo chmod 666 /dev/ttyACM0` if the robot connection fails.
- **Hardware Feedback**: The bridge includes Safe-Start interpolation and Overload protection for the motors.

---
*Developed for Advanced Agentic Coding - SO-100 Series* 
