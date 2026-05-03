# Diffusion-Transformer-Medical-Image-Fusion

A lightweight and effective deep learning framework for **medical image fusion**, combining **diffusion models** and **transformer-based cross-modal attention** to generate high-quality fused CT-MR images.

---

## 🚀 Motivation & Real-World Impact

Medical imaging often requires analyzing multiple modalities:
- **CT (Computed Tomography)** → captures bone structure
- **MRI (Magnetic Resonance Imaging)** → captures soft tissues

Doctors must manually compare both, which is time-consuming, cognitively demanding, and prone to missed details.

### 🎯 Why Fusion?

Image fusion creates a **single image containing both CT and MR information**, enabling:
✅ Better diagnosis  
✅ Improved tumor localization  
✅ Reduced analysis time  
✅ Enhanced clinical decision-making  

---

## ❗ Problem with Existing Methods

Traditional and deep learning methods suffer from:
- ❌ Loss of structural details  
- ❌ Blurred edges  
- ❌ Poor cross-modal understanding  
- ❌ Heavy models (not practical in hospitals)  

---

## 💡 Our Solution

**DiffTransFuse** introduces:
- **Diffusion-based Feature Learning (Stage 1)**: Learns robust representations using noisy inputs.
- **Transformer-based Fusion (Stage 2)**: Uses **cross-attention** for intelligent fusion.
- **Lightweight Design**: Efficient and deployable in real-world clinical systems.

---

## 🧠 Architecture Overview

### 📌 Stage 1: Diffusion Feature Learning

![Stage 1](assets/stage1.png)
- Adds noise to CT and MR images
- Uses **Diffusion UNet**
- Learns multi-scale feature representations
- Outputs feature maps at multiple timesteps

### 📌 Stage 2: Transformer Fusion Pipeline

![Stage 2](assets/stage2.png)

---

## 🧪 Sample Results

### 🔹 Input (CT & MR)
| CT | MR |
|----|----|
| ![CT](assets/ct.png) | ![MR](assets/mr.png) |

### 🔹 Fused Output
| Fused Image |
|-------------|
| ![Fused Output](assets/fused.png) |

---

## 📊 Advantages

- ✔ Preserves edges and textures  
- ✔ Maintains structural integrity  
- ✔ Intelligent modality interaction  
- ✔ Lightweight & fast  
- ✔ High-quality fusion output  

---

## 📁 Project Structure

```text
DiffTransFuse/
├── DATASET/
├── CT-MRI/
├── Results/
├── config/
│   └── fusion_train.json
├── data/
│   └── paired_ct_mr_dataset.py
├── models/
│   ├── losses/
│   ├── stage1/
│   └── stage2/
├── trained_models/
├── utils/
│   └── project_paths.py
├── train_stage1.py
├── train_stage2.py
├── test.py
├── ct_mri_fusion_inference.py
├── fuse_user_data.py
└── evaluation_metrics.py
```

---

## 📥 Dataset

We use the Harvard CT-MR dataset:
👉 Download here: https://zenodo.org/records/7260705

### 📌 Setup

1. Download dataset  
2. Extract into `DiffTransFuse/DATASET/`

---

## ⚙️ Installation

```bash
git clone <your-repo-link>
cd DiffTransFuse
pip install -r requirements.txt
```

---

## 🏋️ Training

### 🔹 Stage 1 (Train Encoders)
Train the CT and MR diffusion models:
```bash
python train_stage1.py --modality both
```

### 🔹 Stage 2 (Train Fusion Head)
Train the cross-modal fusion network:
```bash
python train_stage2.py
```

---

## 🔍 Inference

### Patient-wise dataset structure:
```bash
python test.py
```

### Flat CT/MR folder structure:
```bash
python fuse_user_data.py
```

---

## 📈 Evaluation

Compute metrics like SSIM, PSNR, VIF, SCD, MS-SSIM, etc.
```bash
python test.py --compute-metrics
```
Or for existing outputs:
```bash
python evaluation_metrics.py
```

---

## 🧠 Key Idea

> Instead of directly fusing images, we first learn **robust representations using diffusion**, then fuse them using **cross-modal attention**.

---

## 🔮 Future Work

- Extend to PET/SPECT fusion
- Real-time deployment in hospitals
- Integration with diagnostic AI systems

---

## 👨‍⚕️ Clinical Impact

This system helps doctors by:
- Reducing interpretation time
- Providing clearer visual information
- Improving diagnostic accuracy

---

## 📜 License
MIT License

---

## 🤝 Acknowledgements
- Harvard Medical Dataset
- Diffusion Models
- Transformer Architecture

---
⭐ **If you find this useful, give a star!**
