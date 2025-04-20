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

## 🔧 Installation & Setup
```python
# Step 1: Install PyTorch and essential packages
pip install torch torchvision torchaudio

# Step 2: Install the YOLOv12 framework from Ultralytics
pip install -U ultralytics

# (Optional) Step 3: Install Flash Attention for optimized performance
pip install flash-attn==2.7.3

# Step 4: Install remaining dependencies from the official YOLOv12 requirements file
pip install -U -r https://raw.githubusercontent.com/ultralytics/ultralytics/master/requirements.txt
 ```
## 📦 Download Pretrained YOLOv12 Weights
```python
# Download the YOLOv12 segmentation weights (v1.0)
wget https://github.com/ultralytics/yolov12/releases/download/v1.0/yolov12s-seg.pt -O yolov12s-seg.pt
```

## 📥 Clone YOLOv12 GitHub Repository
```python
# Clone the official Ultralytics YOLOv12 GitHub repository
git clone https://github.com/ultralytics/ultralytics.git
```

## 🧠 Training the Model
```python
from ultralytics import YOLO

# Load the YOLOv12 segmentation model configuration
model = YOLO('ultralytics/ultralytics/cfg/models/12/yolo12-seg.yaml')

# Start training with custom dataset
results = model.train(
    data='Brain Tumor Detection and Segmentation (Yolo 12)/data.yaml',  # Path to data.yaml
    epochs=100,        # Total number of epochs
    batch=8,           # Batch size (adjust according to GPU RAM)
    imgsz=640,         # Input image resolution
    scale=0.5,         # Image scaling factor for augmentation
    mosaic=1.0,        # Mosaic augmentation probability
    mixup=0.0,         # Mixup augmentation disabled
    device="0"         # Use GPU 0 (modify if multiple GPUs are available)
)
```

## 🔍 Run Inference on Test Images
```python
from ultralytics import YOLO

# Load the trained model weights
model = YOLO('runs/segment/train10/weights/best.pt')

# Run inference on a single image
results = model.predict(
    source='Brain Tumor Detection and Segmentation (Yolo 12)/test/images/sample.jpg',  # Replace with your image path
    save=True,          # Save output image in runs/segment/predict/
    imgsz=640,          # Must match training size
    conf=0.5,           # Confidence threshold for predictions
    show=False,         # Set to True to show output image in GUI window
    save_txt=False      # Skip saving prediction as YOLO txt
)
```

## 🖼️ Display Predictions in Notebook
```python
import os
from IPython.display import Image, display

# Folder where prediction results are stored
predict_folder = 'runs/segment/predict2'

# List the files in the prediction folder
output_files = os.listdir(predict_folder)
print(output_files)  # Check saved outputs

# Display the first output image
for file in output_files:
    if file.endswith(('.jpg', '.png', '.jpeg')):
        display(Image(filename=os.path.join(predict_folder, file)))
        break
```

---

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
  url={(https://github.com/abuegila/Brain-Tumor-Detection-and-Segmentation-Yolo-12)}
}
🙌 Acknowledgements
🧠 Medical annotation support by: Abdulrahman Ali

✅ Radiological review by: Ali Ahmed

📦 Tools: Roboflow, Ultralytics
