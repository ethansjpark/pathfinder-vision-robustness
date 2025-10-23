# Pathfinder: Evaluating Visual Robustness of Object Detectors under Sensor Degradation

## Abstract

Real-world robotic vision systems must operate in environments where cameras encounter blur, low light, fog, or sensor noise. These degradations can sharply reduce detection accuracy and stability, posing safety risks for autonomous systems. **Pathfinder** investigates how state-of-the-art object detectors—YOLOv8, DETR, and SAM—perform under such adverse sensing conditions. We simulate a variety of visual degradations, evaluate performance loss, and explore lightweight mitigation via data augmentation, preprocessing, and fine-tuning. The project aims to provide practical insights and reproducible benchmarks for improving perception robustness in robotic applications.

---

## 1. Problem Statement

Deep learning models achieve near-human accuracy under ideal conditions but degrade severely when visual input quality deteriorates. For robots that rely primarily on cameras, this fragility can cause failures in navigation and manipulation tasks. The objective of **Pathfinder** is to systematically quantify performance degradation and identify efficient countermeasures suitable for real-time robotic vision.

Specific goals:

1. Apply synthetic visual corruptions to standard datasets.
2. Evaluate how each degradation type affects detector performance.
3. Propose and test lightweight mitigation strategies such as fine-tuning and preprocessing.

---

## 2. Related Work

Prior research—including **RobustDet** (CVPR 2021), **DegradationBench** (CVPR 2023), and **YOLOv8 Robustness Studies** (2024)—shows that vision models remain vulnerable to blur and noise. Works on **domain adaptation** and **data augmentation** (MixUp, CutOut) suggest partial remedies, while restoration networks such as **DeblurGANv2** and **Restormer** improve image quality before inference. **Pathfinder** extends this line of inquiry by directly comparing modern detectors under controlled synthetic degradations and assessing both quantitative and qualitative robustness.

---

## 3. Methodology

### 3.1 Dataset

- **COCO 2017** (subset) for general object detection.
- **BDD100K** or **Cityscapes** (optional, driving-scene realism).
- Synthetic degradations generated using **Albumentations**:
  - Gaussian blur, motion blur
  - Fog, brightness reduction
  - Gaussian noise, JPEG compression

### 3.2 Models

- **YOLOv8 (Ultralytics)** — real-time baseline.
- **DETR (Facebook)** — transformer-based detector.
- **SAM (Meta)** — segmentation robustness reference.

### 3.3 Experiment Pipeline

1. Evaluate pretrained models on clean vs. degraded images.
2. Measure mAP@50, precision, and recall.
3. Fine-tune with mixed clean + corrupted data or apply restoration preprocessing.
4. Analyze results and visualize degradation–performance relationships.

---

## 4. Expected Results

We anticipate significant performance drops under motion blur, fog, and low-light conditions, with partial recovery after fine-tuning or preprocessing. Results will include quantitative tables and qualitative side-by-side comparisons illustrating detection failures and recoveries.

---

## 5. Deliverables

- 📂 **GitHub repository:** [`ethansjpark/pathfinder-vision-robustness`](https://github.com/ethansjpark/pathfinder-vision-robustness)
- 📄 CVPR-format paper (in `/paper/`)
- 🖥️ Presentation slides demonstrating experiments and results
- (Optional) 🤗 Hugging Face model card or demo visualizing degraded vs. restored detections

---

## 6. Alignment with Georgia Tech Labs

**Pathfinder** aligns with Georgia Tech’s leading research in robust perception and embodied AI:

- **Prof. Judy Hoffman** — domain adaptation & robust vision.
- **Prof. Sehoon Ha** — perception for legged and humanoid robots.
- **Prof. Zsolt Kira** — multimodal representation learning for robotics.

By quantifying sensor-level robustness and exploring efficient adaptation, the project contributes foundational insights applicable to embodied and reinforcement-learning systems.

---

## 7. Timeline (4 Weeks)

| Week | Focus                                        | Deliverable                     |
| ---- | -------------------------------------------- | ------------------------------- |
| 1    | Literature review + dataset + baseline setup | Initial repo & preliminary runs |
| 2    | Baseline evaluations on clean vs degraded    | Quantitative metrics            |
| 3    | Fine-tuning + preprocessing experiments      | Improved robustness results     |
| 4    | Analysis + CVPR-style paper + presentation   | Final deliverables              |

---

## 8. References

1. Tang et al., _“RobustDet: Towards Robust Object Detection,”_ CVPR 2021.
2. Hong et al., _“DegradationBench: Benchmarking Image Restoration under Real-World Degradations,”_ CVPR 2023.
3. Carion et al., _“DETR: End-to-End Object Detection with Transformers,”_ ECCV 2020.
4. Redmon et al., _“YOLOv3: Real-Time Object Detection,”_ arXiv 2018.
5. Kirillov et al., _“Segment Anything,”_ arXiv 2023.

---

**Author:** Ethan Park  
**Institution:** Emory University  
**Semester:** Fall 2025 — _Computer Vision Research Project_
