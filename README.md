# Brain Tumor MRI Dataset for YOLOv11 Segmentation

This dataset is a curated collection of high-resolution, axial-view MRI brain scans, designed for training and evaluating brain tumor segmentation models. It is fully optimized for use with YOLOv11 and supports polygon-based mask annotations for precision medical imaging analysis.

## 📁 Dataset Overview

- **Total Images Collected**: 21,990 MRI scans
- **Final Curated Dataset**: 4,240 annotated axial-view images
- **Image Size**: Standardized to 640×640 pixels
- **Annotation Format**: YOLOv11 segmentation format with polygon-based masks
- **Tumor Types**: Glioma, Meningioma, Pituitary Tumor, No Tumor

## 📊 Class Distribution

| Tumor Class   | Number of Images |
|---------------|------------------|
| Glioma        | 1,032            |
| Meningioma    | 1,111            |
| Pituitary     | 1,110            |
| No Tumor      | 1,099            |

## 📚 Dataset Sources

The images were aggregated from four publicly available and credible medical datasets:

1. **Brain Tumor MRI - Accuracy 99%** – *Kaggle*  
2. **Brain Tumor Detection** – *Roboflow (Istanbul Arel University)*  
3. **Brain Tumor MRI Data** – *Kaggle (Tom Backert)*  
4. **My First Project** – *Roboflow (YEN)*  

Following the collection of 21,990 raw images, a rigorous filtering process was performed to extract the highest quality axial-view MRI scans. This resulted in a final dataset of 4,240 images.

## 📝 Annotation & Curation

All annotations were created using **[Roboflow](https://universe.roboflow.com/braintumordetectionandsegementation/my-first-project-m9r0w-oyjto/dataset/6)**, utilizing their polygon-based segmentation tools to ensure pixel-level precision. The annotation process was supervised by:

- **Dr. Ali Ahmed** – Radiologist  
- **Dr. Abdelrhman Ali**

Their medical expertise helped ensure clinical accuracy in identifying tumor boundaries and verifying annotation consistency.

The full dataset pipeline—including annotation, image preprocessing, class balancing, and deployment—was managed end-to-end through Roboflow, which also hosted the model training and inference using the YOLOv11 segmentation workflow.

## 🧪 Dataset Splits

- **Training**: 70%  
- **Validation**: 15%  
- **Testing**: 15%  

This split ensures model generalization and fairness across all tumor types during evaluation.

## 📦 Intended Use

This dataset is ideal for training deep learning models in medical imaging, particularly object detection and segmentation networks such as YOLOv11. It is compatible with Ultralytics, Roboflow, PyTorch, and other major ML frameworks.

## 📈 Model Results (Using YOLOv11)

- **Precision**: 90.2%  
- **Recall**: 83.0%  
- **F1 Score**: 86.4%  
- **mAP@50**: 88.5%  

## 📜 License & Usage

This dataset is provided strictly for academic research and non-commercial purposes. Users must cite the original dataset sources as listed above.

## 🔗 Citation

Please reference this repository and the respective dataset providers in any published research or derived work using this dataset.
