# AG-USegNet: Attention-Guided Hybrid Network for Ultrasound Nerve Segmentation

A deep learning framework for **Brachial Plexus nerve segmentation** from ultrasound images using a hybrid **U-Net + SegNet** architecture with **attention-gated skip connections**. The project focuses on improving segmentation accuracy while maintaining computational efficiency for near real-time clinical deployment.

---

## Key Highlights

- Hybrid **U-Net + SegNet** architecture
- Attention-gated skip connections
- Lightweight and computationally efficient
- TensorFlow implementation
- ONNX export with C++ inference pipeline
- Evaluated against state-of-the-art segmentation models

---

## Project Evolution

This work evolved from our initial lightweight segmentation model **LAG-Net**.

### LAG-Net
- Lightweight residual encoder
- Channel-spatial attention
- Computationally efficient segmentation

### AG-USegNet (Final Model)
- Hybrid U-Net + SegNet architecture
- Attention-guided skip connections
- Improved feature fusion
- ONNX deployment
- C++ inference support
- Higher segmentation performance

---

# Problem Statement

Ultrasound nerve segmentation is challenging because:

- Low image contrast
- Speckle noise
- Small nerve structures
- Anatomical variations
- Difficult boundary localization

AG-USegNet addresses these challenges by combining the localization capability of **U-Net**, the efficient decoder of **SegNet**, and an attention mechanism that focuses on nerve-specific regions.

---

# Clinical Importance

Accurate brachial plexus segmentation assists in:

- Regional anesthesia
- Surgical planning
- Computer-assisted diagnosis
- Medical education
- Image-guided interventions

---

# Model Architecture

AG-USegNet consists of:

## Encoder (U-Net)

- Multi-scale feature extraction
- Skip connections
- Rich spatial representation

## Bottleneck

- Deep semantic feature learning

## Decoder (SegNet)

- Pooling-index based upsampling
- Efficient feature reconstruction
- Sharp segmentation masks

## Attention Gates

- Suppress background noise
- Highlight nerve structures
- Improve boundary localization

---

# Dataset

**Dataset**

Kaggle Ultrasound Nerve Segmentation Dataset

- 5,635 ultrasound images
- 47 subjects
- Ground-truth segmentation masks

---

# Methodology

## Data Preprocessing

- Image normalization
- CLAHE contrast enhancement
- Data augmentation
  - Rotation
  - Horizontal flipping
  - Scaling

## Training

- TensorFlow
- Adam Optimizer
- Binary Cross Entropy + Dice Loss
- Early Stopping

---

# Evaluation Metrics

- Dice Coefficient
- F1-Score
- IoU
- Precision
- Recall
- Boundary Accuracy

---

# Performance

| Model | Dice | IoU |
|--------|------:|------:|
| LAG-Net | 80.36% | 67.17% |
| **AG-USegNet** | **84.50%** | **79.47%** |

### Final Performance

| Metric | Score |
|---------|------:|
| Dice Coefficient | **0.8450** |
| F1-Score | **0.8856** |
| IoU | **0.7947** |

AG-USegNet achieved superior segmentation performance while maintaining computational efficiency suitable for near real-time inference.

---

# Comparison with Existing Models

The proposed model was evaluated against:

- Attention U-Net
- DeepLabV3+
- TransUNet
- SwinSeg

AG-USegNet demonstrated improved segmentation quality and better boundary localization.

---

# Ablation Study

The contribution of the attention module was evaluated through an ablation study.

**Without Attention**
- Lower Dice Score
- Poor boundary localization

**With Attention**
- Higher segmentation accuracy
- Better nerve localization
- Reduced background noise

<p align="center">
<img src="ablation study.png" width="500">
</p>

---

# Sample Results

<p align="center">
<img src="results.png" width="650">
</p>

Example predictions showing improved nerve boundary localization.

---

# Deployment

The trained TensorFlow model was exported to **ONNX** and integrated with a **C++ inference pipeline** for near real-time deployment.

Pipeline:

TensorFlow → ONNX → C++ Inference

---

# Repository Structure

```
AG-USegNet
│
├── app/
├── hybrid.py
├── unet.py
├── Segnet.py
├── main.cpp
├── results.png
├── overall.png
├── ablation study.png
├── README.md
```

---

# Installation

```bash
git clone https://github.com/Sab0507G/AG-USegNet-Ultrasound-Segmentation.git

cd AG-USegNet-Ultrasound-Segmentation

pip install -r requirements.txt
```

---

# Running the Project

Training

```bash
python train.py
```

Inference

```bash
python predict.py
```

---

# Future Work

- Real-time deployment optimization
- Multi-class medical image segmentation
- Transformer-based attention modules
- Edge-device optimization
- Clinical validation

---

# Author

**Sabhyata Sinha**

B.Tech Computer Science (AI & ML)

Manipal University Jaipur

---

## Citation

```bibtex
@article{agussegnet2026,
  title={AG-USegNet: Attention-Guided Hybrid Network for Ultrasound Nerve Segmentation},
  author={Sabhyata Sinha},
  year={2026}
}
```

---

## License

This repository is intended for research and educational purposes.
