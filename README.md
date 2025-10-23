# Pathfinder: Evaluating Visual Robustness of Object Detectors under Sensor Degradation

_(Repository: `pathfinder-vision-robustness`)_

> _A research-style Computer Vision project for Emory University and Georgia Tech Robotics + CV + RL labs._

---

### 🧭 Overview

Real-world robotic vision often suffers from imperfect sensors—blur, fog, low light, or noise.  
**Pathfinder** examines how modern object detectors (YOLOv8, DETR, SAM) perform under such degradation and explores lightweight methods to restore robustness.

**Keywords:** Computer Vision • Robotics • Sensor Degradation • Robust Perception

---

### ⚙️ Setup

```bash
git clone https://github.com/ethansjpark/pathfinder-vision-robustness.git
cd pathfinder-vision-robustness
pip install -r requirements.txt
```

---

### Repo Layout

```bash
src/ → core code (training, evaluation, inference)
configs/ → YAML experiment configs
experiments/ → results & logs
notebooks/ → analysis notebooks
paper/ → CVPR-style LaTeX paper
proposal/ → research proposal + GT alignment
```
