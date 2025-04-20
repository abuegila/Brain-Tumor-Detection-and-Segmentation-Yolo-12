# 🧠 Brain Tumor MRI Dataset - YOLOv12 Segmentation (v2)

Welcome to **Brain Tumor Detection and Segmentation (Yolo 12)**, a custom-curated brain tumor dataset designed for segmentation using the latest **YOLOv12** architecture. This repository provides everything you need to train, evaluate, and perform inference with a state-of-the-art segmentation model on real-world medical imaging data.

---

## 📂 Dataset Overview

- **Total Images**: 4,351  
- **Annotation Format**: YOLOv12 (segmentation)  
- **Image Size**: Resized to **640×640** (stretched)  
- **Preprocessing**:
  - Auto-orientation of pixel data (EXIF orientation stripped)
  - Resized uniformly  
- **No Augmentation Applied**: Raw dataset with no synthetic transformations

---

## 📥 Data Collection & Annotation

- **Sources**: The images were collected from multiple publicly available resources across the internet.
- **Annotation**: All segmentation labels were manually created by:
  - The project author
  - A certified medical doctor
- **Review**: Every annotation was carefully reviewed and verified by a professional radiologist to ensure high-quality and clinically relevant labeling.

This collaborative annotation process ensures **accuracy**, **consistency**, and **real-world reliability**, making the dataset suitable for training medical AI systems.

---

🔧 Installation & Setup
<pre> ```python
# Step 1: Install PyTorch and essential packages
pip install torch torchvision torchaudio

# Step 2: Install the YOLOv12 framework from Ultralytics
pip install -U ultralytics

# (Optional) Step 3: Install Flash Attention for optimized performance
pip install flash-attn==2.7.3

# Step 4: Install remaining dependencies from the official YOLOv12 requirements file
pip install -U -r https://raw.githubusercontent.com/ultralytics/ultralytics/master/requirements.txt
 ``` </pre>

🔒 License
This dataset is private and intended for research and educational use only.
Commercial use is strictly prohibited.

🧾 Citation
If you use this dataset in your research, please cite it as follows:

bibtex
Copy
Edit
@misc{myfirstproject2025,
  title={Brain Tumor MRI Dataset for YOLOv12 Segmentation},
  author={Yusuf Abu Egila},
  year={2025},
  url={https://github.com/abuegila/brain-tumor-yolov12-dataset}
}
🙌 Acknowledgements
🧠 Medical annotation support by: Abdulrahman Ali

✅ Radiological review by: Ali Ahmed

📦 Tools: Roboflow, Ultralytics
