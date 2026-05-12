# Bird’s-Eye View (BEV) Generation from Multi-Camera Images

This project focuses on generating Bird’s-Eye View (BEV) semantic maps from multi-camera surround-view images in an autonomous driving setting.

The model learns to project and fuse information from 4 cameras into a unified top-down representation of the environment.

---

## Task

Given 4 synchronized surround-view camera images, the goal is to predict a BEV occupancy grid representing:
- free space
- occupied regions
- unknown areas

---

## Models and Experiments

Several architectures were implemented and evaluated:

- **Encoder-Decoder baseline** → ~0.40 IoU  
- **Lift-Splat-Shoot (LSS)** → ~0.50 IoU  
- **LSS + Dice Loss** → **~0.54 IoU (best model)**  

The best performance was achieved using the LSS-based architecture combined with Dice Loss, improving spatial segmentation quality in BEV space.

---

## Results

| Model | IoU |
|------|-----|
| Encoder-Decoder baseline | ~0.40 |
| LSS | ~0.50 |
| LSS + Dice Loss | **~0.54** |

---

## Checkpoints

All trained model weights are stored in the `chkp/` directory, including the best-performing LSS + Dice Loss model.

---

## Visualization

The training notebook contains visualization utilities for:
- BEV prediction vs ground truth comparison
- input multi-camera views
- qualitative evaluation of model predictions

These visualizations allow inspection of model behavior directly in BEV space.

---
