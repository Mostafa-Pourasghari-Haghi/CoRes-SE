# CoRes-SE

**CoRes-SE** is a CNN-based fusion model for robust Facial Expression Recognition (FER) in the wild. The model combines ResNet50 and ConvNeXt-Tiny architectures through an SE (Squeeze-and-Excitation) attention mechanism, and leverages training techniques like Mixup and Stochastic Weight Averaging (SWA) for better generalization and robustness.

---

## 🔍 Key Features

* **Fusion of ResNet50 and ConvNeXt-Tiny** for spatial and semantic richness
* **SE Attention Module** to emphasize meaningful feature dimensions
* **Mixup Augmentation** to reduce overfitting and improve generalization
* **SWA** to stabilize training and enhance model robustness
* **Tested on RAF-DB and AffectNet**, two large-scale facial expression datasets

---

## 🗂 Dataset

1. **RAF-DB**: Real-world Affective Faces Database

   * [Download Link](https://www.kaggle.com/datasets/shuvoalok/raf-db-dataset)
   * Organize as:

     ```
     /raf-db-dataset/
         └── DATASET/
             ├── train/
             └── test/
     ```

2. **AffectNet**: Large-scale dataset for affective facial expression recognition

   * [Download Link](https://www.kaggle.com/datasets/mstjebashazida/affectnet)

Update paths in the code accordingly if your folder structure differs.

---

## ⚙️ Setup

### Install Required Libraries

```bash
pip install timm albumentations
```

---

## 🚀 How to Train

1. Upload the dataset to your preferred location (e.g., Google Drive).
2. Mount Drive in Colab:

   ```python
   from google.colab import drive
   drive.mount('/content/drive')
   ```
3. Modify the following paths in the code if needed:

```python
train_dir = "/content/raf-db-dataset/DATASET/train"
test_dir = "/content/raf-db-dataset/DATASET/test"
```

4. Run the notebook cells sequentially. Training will begin from scratch or resume from a saved checkpoint.
5. Final SWA model is saved as:

```bash
/content/drive/MyDrive/checkpoints/model_swa_final.pth
```

---

## 📊 Results on RAF-DB

* **Max Validation Accuracy**: 89.11%
* **Final SWA Accuracy**: 89.02%

### 📉 Confusion Matrix

Confusion matrix and classification report are generated at the end of the notebook.

---

## 📦 Model Architecture Summary

* **Backbones**: ResNet50 (ImageNet) + ConvNeXt-Tiny (ImageNet)
* **Feature Fusion**: Concatenation → SE Attention → Classifier
* **Classifier Head**: Linear → ReLU → Dropout → Linear (7 classes)

---

## 📂 File Structure

```
CoRes-SE/
├── CoRes-SE.ipynb      # Main training + evaluation notebook
├── checkpoints/         # Saved models (.pth)
├── README.md            # Project documentation
└── utils/ (optional)    # Helper modules if split
```

---

## 📌 Recommendations for Future Work

* Developing lighter and more optimized versions of the proposed model R
* Integrating the CoRes-SE model with advanced noise-robust learning techniques and adaptive reweighting strategies 
* Implementing advanced and complementary data augmentation strategies
* Addressing low-distinctiveness classes and visually similar emotional expressions

---

## 📚 Citation

If you use CoRes-SE in your research, please cite this repository:

```
@misc{cores-se2025,
  title={CoRes-SE: A CNN-Based Fusion with Attention and Mixup-SWA for Robust Facial Expression Recognition in the Wild},
  author={Mostafa Pourasghari Haghi},
  year={2025},
  url={https://github.com/Mostafa-Pourasghari-Haghi/CoRes-SE}
}
```

---


