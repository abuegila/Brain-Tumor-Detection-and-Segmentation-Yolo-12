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

## 📁 Repository Structure
Brain Tumor Detection and Segmentation (Yolo 12)/ ├── data.yaml # Dataset config for YOLOv12 ├── train/ │ ├── images/ │ └── labels/ ├── valid/ │ ├── images/ │ └── labels/ ├── test/ │ ├── images/ │ └── labels/

🚀 Getting Started with YOLOv12
🔧 1. Install Required Dependencies
bash
Copy
Edit
pip install torch torchvision torchaudio
pip install -U ultralytics
pip install flash-attn==2.7.3
pip install -U -r https://raw.githubusercontent.com/ultralytics/ultralytics/master/requirements.txt
⬇️ 2. Download YOLOv12 Segmentation Weights
bash
Copy
Edit
wget https://github.com/ultralytics/yolov12/releases/download/v1.0/yolov12s-seg.pt -O yolov12s-seg.pt
🔁 3. Clone YOLOv12 Repository
bash
Copy
Edit
git clone https://github.com/ultralytics/ultralytics.git
🧪 Training YOLOv12 on This Dataset
python
Copy
Edit
from ultralytics import YOLO

model = YOLO('ultralytics/ultralytics/cfg/models/12/yolo12-seg.yaml')

results = model.train(
    data='Brain Tumor Detection and Segmentation (Yolo 12)/data.yaml',
    epochs=100,
    batch=8,
    imgsz=640,
    scale=0.5,
    mosaic=1.0,
    mixup=0.0,
    device="0"  # Adjust GPU ID if needed
)
🔍 Run Inference on a Test Image
python
Copy
Edit
from ultralytics import YOLO

model = YOLO('runs/segment/train10/weights/best.pt')

results = model.predict(
    source='Brain Tumor Detection and Segmentation (Yolo 12)/test/images/sample.jpg',
    save=True,
    imgsz=640,
    conf=0.5,
    show=False,
    save_txt=False
)
📸 Visualize Output
python
Copy
Edit
import os
from IPython.display import Image, display

predict_folder = 'runs/segment/predict2'
output_files = os.listdir(predict_folder)

for file in output_files:
    if file.endswith(('.jpg', '.png', '.jpeg')):
        display(Image(filename=os.path.join(predict_folder, file)))
        break

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

✅ Radiological review by: [Radiologist's Name]

📦 Tools: Roboflow, Ultralytics
