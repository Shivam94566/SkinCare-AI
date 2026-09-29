# SkinCare-AI

## AI-Powered Rural Healthcare Assistant for Preliminary Skin Disease Screening

SkinCare AI is an AI-assisted healthcare platform designed for rural communities and health camps where access to dermatologists and specialized healthcare facilities is limited.

The system analyzes a patient's skin image along with reported symptoms to provide a preliminary screening result, risk level, and recommendation for further medical attention.

> ⚠️ SkinCare AI is an assistance and screening tool. It does not replace qualified doctors or provide a definitive medical diagnosis.

---

## 🎯 Problem Statement

Rural communities often face limited access to dermatologists and specialized healthcare facilities. Skin diseases may be ignored because of low awareness, lack of nearby specialists, and delayed medical consultation.

### Key Challenges

- Limited access to dermatologists in rural areas
- Delayed diagnosis and treatment
- Low awareness about skin diseases
- Lack of organized patient history
- Difficulty finding nearby healthcare facilities
- High workload for healthcare workers during health camps

---

## 💡 Our Solution

SkinCare AI provides an end-to-end preliminary screening system that combines:

**Skin Image + Patient Symptoms + Basic Patient Information**

The platform helps healthcare workers perform faster preliminary screening and identify cases that may require professional medical attention.

### Core Features

- 🔬 AI-assisted skin disease screening
- 📷 Skin image upload and analysis
- 📝 Symptom-based analysis
- ⚠️ Risk-level assessment
- 🤖 AI healthcare chatbot
- 🏥 Nearby hospital/health-center finder
- 🗺️ Community disease heatmap
- 📋 Patient history management
- 🌐 Multi-language support
- 💊 Medicine reminder support
- 📊 Community healthcare analytics

---

# ⚙️ Technical Workflow

```text
Patient Registration
        ↓
Skin Image Upload
        ↓
Image Preprocessing
        ↓
Symptom Collection
        ↓
AI Image Analysis
        ↓
Symptom Analysis
        ↓
Screening Engine
        ↓
Possible Condition + Risk Level
        ↓
 ┌───────────────┬────────────────┐
 ↓               ↓                ↓
AI Chatbot   Hospital Finder   Patient History
                                      ↓
                              Community Analytics
                                      ↓
                              Disease Heatmap


# SkinCare-AI

## AI-Powered Rural Healthcare Assistant for Preliminary Skin Disease Screening

SkinCare AI is an AI-assisted healthcare platform designed for rural communities and health camps where access to dermatologists and specialized healthcare facilities is limited.

The system analyzes a patient's skin image to provide a preliminary screening result, a confidence score, and a recommendation for further medical attention. The long-term vision is to combine the image with reported symptoms and patient information (see [Roadmap](#-roadmap--future-scope)).

> ⚠️ SkinCare AI is an assistance and screening tool. It does not replace qualified doctors or provide a definitive medical diagnosis.

---

## 🎯 Problem Statement

Rural communities often face limited access to dermatologists and specialized healthcare facilities. Skin diseases may be ignored because of low awareness, lack of nearby specialists, and delayed medical consultation.

### Key Challenges

- Limited access to dermatologists in rural areas
- Delayed diagnosis and treatment
- Low awareness about skin diseases
- Lack of organized patient history
- Difficulty finding nearby healthcare facilities
- High workload for healthcare workers during health camps

---

## 💡 Our Solution

SkinCare AI provides a preliminary screening system that helps healthcare workers perform faster screening and identify cases that may require professional medical attention.

### ✅ Currently Implemented (v1)

- 🔬 AI-assisted skin disease screening (9 skin conditions)
- 📷 Skin image upload and analysis (JPG / JPEG / PNG)
- 📊 Confidence score and Top-3 predictions
- ⚠️ Risk flag: serious categories (Melanoma, Squamous cell carcinoma, Actinic keratosis) show a "consult a dermatologist" warning
- 🔻 Low-confidence warning (below 40%) for unclear or non-skin images
- 🌐 Web interface built with Streamlit

### 🛠️ Planned (Roadmap)

- 📝 Symptom-based analysis
- 🤖 AI healthcare chatbot
- 🏥 Nearby hospital / health-center finder
- 🗺️ Community disease heatmap
- 📋 Patient history management
- 🌐 Multi-language support (Hindi / English)
- 💊 Medicine reminder support
- 📊 Community healthcare analytics

---

## 🗂️ Dataset

| Property | Details |
|---|---|
| **Name** | Skin Disease Classification Dataset |
| **Source** | Mendeley Data |
| **Link** | https://data.mendeley.com/datasets/schhndjbjp/1 |
| **Classes** | 9 |
| **Version used** | `Split_smol` (pre-split into train / val) |
| **Train images** | 697 |
| **Validation images** | 181 |

> Please check the dataset page for its license and citation requirements before reuse or redistribution.

### Classes

| # | Class |
|---|---|
| 0 | Actinic keratosis |
| 1 | Atopic Dermatitis |
| 2 | Benign keratosis |
| 3 | Dermatofibroma |
| 4 | Melanocytic nevus |
| 5 | Melanoma |
| 6 | Squamous cell carcinoma |
| 7 | Tinea Ringworm Candidiasis |
| 8 | Vascular lesion |

### Images per class

| Class | Train | Validation |
|---|---|---|
| Actinic keratosis | 80 | 20 |
| Atopic Dermatitis | 81 | 21 |
| Benign keratosis | 80 | 20 |
| Dermatofibroma | 80 | 20 |
| Melanocytic nevus | 80 | 20 |
| Melanoma | 80 | 20 |
| Squamous cell carcinoma | 80 | 20 |
| Tinea Ringworm Candidiasis | 56 | 20 |
| Vascular lesion | 80 | 20 |

---

## 📁 Folder Structure

### Google Drive (project storage)

```text
MyDrive/
└── Skin_Disease_Project/
    ├── dataset/
    │   └── archive.zip                     ← downloaded from Mendeley (do not extract)
    ├── skin_disease_mobilenetv2.keras      ← trained model (created by notebook)
    ├── class_names.json                    ← class labels (created by notebook)
    └── app.py                              ← Streamlit app (created by notebook)
```

### Dataset structure (after unzip in Colab)

```text
/content/data/Split_smol/
├── classes.csv
├── train.csv
├── val.csv
├── train/
│   ├── Actinic keratosis/
│   ├── Atopic Dermatitis/
│   ├── Benign keratosis/
│   ├── Dermatofibroma/
│   ├── Melanocytic nevus/
│   ├── Melanoma/
│   ├── Squamous cell carcinoma/
│   ├── Tinea Ringworm Candidiasis/
│   └── Vascular lesion/
└── val/
    └── (same 9 class folders)
```

### Repository

```text
SkinCare-AI/
├── README.md
├── Skin_Disease_Detection_v2.ipynb         ← full training + app notebook
├── app.py                                  ← Streamlit UI (optional copy)
└── class_names.json                        ← class labels
```

---

## ⚙️ Technical Workflow

### Current pipeline (implemented)

```text
Skin Image Upload
        ↓
Resize to 224 × 224
        ↓
MobileNetV2 (Transfer Learning) feature extraction
        ↓
Dense + Softmax classifier
        ↓
Possible Condition + Confidence (Top-3)
        ↓
Risk flag / low-confidence warning
        ↓
Result shown in Streamlit UI
```

### Vision (planned)

```text
Patient Registration
        ↓
Skin Image Upload  →  Image Preprocessing
        ↓
Symptom Collection
        ↓
AI Image Analysis + Symptom Analysis
        ↓
Screening Engine
        ↓
Possible Condition + Risk Level
        ↓
 ┌───────────────┬────────────────┬────────────────┐
 ↓               ↓                ↓
AI Chatbot   Hospital Finder   Patient History
                                      ↓
                              Community Analytics
                                      ↓
                              Disease Heatmap
```

---

## 🧠 Model Details

| Item | Details |
|---|---|
| **Task** | Multi-class image classification (9 classes) |
| **Base model** | MobileNetV2 (pre-trained on ImageNet) |
| **Input size** | 224 × 224 × 3 |
| **Head** | GlobalAveragePooling → Dropout(0.4) → Dense(9, softmax) |
| **Training** | Phase 1: frozen base, Phase 2: fine-tune last 30 layers (LR 1e-5) |
| **Regularization** | Data augmentation, Dropout, Early Stopping, Class weights |
| **Loss / Optimizer** | Sparse categorical crossentropy / Adam |

### Techniques used

Transfer Learning · Fine-tuning · Data Augmentation (flip, rotation, zoom, contrast) · Dropout · Class weights · Early Stopping · Confusion Matrix · Precision / Recall / F1

### Results (validation set)

| Model | Validation Accuracy |
|---|---|
| Basic CNN (from scratch) | 54.14% |
| MobileNetV2 (transfer learning) | 68.51% |

> These figures are from the initial run. Results may vary slightly between runs. Update this table with your final numbers after running the v2 notebook.

**Observations:** The model performs well on Atopic Dermatitis and Benign keratosis, but is weaker on Melanoma and Squamous cell carcinoma, which are visually similar to other classes and have limited training data.

---

## 🛠️ Tech Stack

| Area | Tools |
|---|---|
| Language | Python 3 |
| Deep learning | TensorFlow / Keras |
| Evaluation | scikit-learn, matplotlib, seaborn |
| Web UI | Streamlit |
| Environment | Google Colab (T4 GPU), Google Drive |
| Public link | Cloudflare Tunnel / Localtunnel |

---

## 🚀 How to Run (Google Colab)

1. **Download the dataset** from https://data.mendeley.com/datasets/schhndjbjp/1 (keep it as `archive.zip`).
2. **Create folders in Google Drive:** `MyDrive/Skin_Disease_Project/dataset/` and upload `archive.zip` inside.
3. **Open Colab** → *File → Upload notebook* → select `Skin_Disease_Detection_v2.ipynb`.
4. **Enable GPU:** *Runtime → Change runtime type → T4 GPU*.
5. **Run cells top to bottom:**
   - Install → Drive mount → Unzip → Load data → Build model → Train → Fine-tune → Evaluate → Save model → Create `app.py`
6. **Launch the app** with the last cell and open the printed public link.
7. **Upload a skin image** and click **Analyze Skin**.

### Running the app locally (without training)

Keep `skin_disease_mobilenetv2.keras`, `class_names.json` and `app.py` in the same folder, and change the two paths in `app.py`:

```python
MODEL_PATH = "skin_disease_mobilenetv2.keras"
CLASS_PATH = "class_names.json"
```

Then run:

```bash
pip install streamlit tensorflow pillow numpy
streamlit run app.py
```

---

## ⚠️ Limitations

- Trained on a small dataset (~80 images per class); overall accuracy is limited
- Recognizes only 9 conditions; other conditions may be mislabelled
- Cannot reliably detect non-skin images
- Lower accuracy on serious classes such as Melanoma and Squamous cell carcinoma
- Performance depends on image quality, lighting, and angle
- Not clinically validated
- Educational screening tool, **not a medical diagnosis**

---

## 🔮 Roadmap / Future Scope

- Larger datasets (e.g. HAM10000 / ISIC) to improve accuracy
- Compare other architectures (EfficientNet, ResNet50, DenseNet)
- Grad-CAM to visualize which image regions influenced the prediction
- Skin / non-skin image check before prediction
- More disease classes (psoriasis, acne, vitiligo, etc.)
- Symptom-based analysis combined with image analysis
- AI chatbot, hospital finder, patient history, and community disease heatmap
- Hindi / English multi-language support
- Permanent deployment (Hugging Face Spaces / cloud) and mobile app (TensorFlow Lite)
- Validation with dermatologists

---

## ⚖️ Disclaimer

SkinCare AI is an educational project and screening aid. Predictions can be incorrect. It must not be used as a substitute for professional medical advice, diagnosis, or treatment. Always consult a qualified healthcare professional.
