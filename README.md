
# Green Avenger 🌳
**AI-ML Framework for High-Resolution Canopy and Species Analysis in Amazonian Ecosystems**

Authors: Catherine Wang, Xintong He, Ziyuan Ma, Ziying Ye

---

## 📌 Project Overview

The Amazon rainforest faces major challenges for ecological monitoring due to limited human access and lack of ground-truth data.  
**Green Avenger** proposes an automatic machine learning framework to:

- Detect tree presence from aerial imagery.
- Identify whether areas contain **single** or **multiple** tree crowns.
- Recognize **palm trees** based on image and textual information.

This project advances scalable, high-precision environmental analysis to aid conservation and ecological research.

---

## 🛠️ Methodology

### 1. Predictive Canopy Mapping
- Resample aerial images at varying resolutions.
- Segment into 1024x1024 pixel tiles using a modified `detectree2` pipeline.
- Predict tree canopy polygons.

### 2. Single vs. Multiple Tree Detection
- Calculate canopy heights (DSM - DEM).
- Apply Gaussian Kernel Density Estimation (KDE) to analyze height distributions.
- Determine modality:
  - **Single peak** → Single tree.
  - **Multiple peaks** (minimum separation >5 meters) → Multiple trees.
- Validate spatial patterns using **Moran’s I**.

### 3. Palm Tree Identification
- **Image Model**: Extract ResNet embeddings, classify using Random Forest.
- **Text Model**: Use Word2Vec embeddings + SVM classifier based on habitat descriptions.
- **Fusion**: Logistic regression integrates image and text outputs for final prediction.

---

## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/green-avenger.git
   cd green-avenger
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Launch the notebook:
   ```bash
   jupyter notebook GA_Tree_Detection_Model.ipynb
   ```

✅ No additional setup is needed — the notebook can run end-to-end.

---

## 📈 Project Workflow

- **Capture** aerial RGB and LiDAR images.
- **Process** images into standardized tiles.
- **Compute** canopy prediction, height analysis, tree type classification.
- **Use** results for ecological management and conservation efforts.

---

## 🔥 Key Contributions

- Built a fully automated, scalable pipeline for rainforest canopy analysis.
- Designed a robust fusion model combining visual and textual data for species detection.
- Developed an accessible tool for researchers and conservationists.

---

## 📃 License

This project is licensed under the [MIT License](LICENSE).

---

## ✨ Acknowledgements

We thank our mentors, teammates, and the open-source community for their support throughout this project.

