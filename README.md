# **Melanoma Detection Using SIIM-ISIC Dataset**  
🌟 *A collaborative project by Pukar Baral, Chandu Narasimhareddyvari, and Eswar Naga Lakshman Chalamalasetty.*

---

## **Overview**  
Melanoma is the most dangerous form of skin cancer. Early detection is critical for effective treatment and high survival rates. This project leverages deep learning techniques to classify melanoma as benign or malignant using dermoscopic images and metadata from the **SIIM-ISIC Melanoma Classification Dataset**.

---

## **Objectives**  
1. **Develop a robust deep learning model** to classify skin lesions as malignant or benign.  
2. **Evaluate the model's performance** using metrics like accuracy, sensitivity, and specificity.  
3. Address challenges like class imbalance, artifacts, and low contrast in dermoscopic images.

---

## **Dataset**  
### SIIM-ISIC Melanoma Dataset Highlights:  
- **Training Data**: 33,126 images & metadata.  
- **Test Data**: 10,000 images.  
- **Features**: 
  - **Image Data**: High-resolution dermoscopic images.  
  - **Statistical Features**: Metadata like age, sex, and lesion location.  

### Data Preprocessing:
1. Handled missing values by dropping rows with minimal data loss.  
2. Performed label encoding for categorical variables.  
3. Normalized numerical features for consistent scaling.  

### Data Augmentation:
- **RandomResizeCrop**, **ScaleShiftRotate**, **HorizontalFlip**, **VerticalFlip**, **ToTensor**.

---

## **Model Architecture**  
This project employs a **multi-modal deep learning approach** using **EfficientNet-B2** and a fully connected network (FNN):  

1. **EfficientNet-B2**:
   - Convolutional Neural Network for image feature extraction.
   - Pre-trained on ImageNet for high accuracy and computational efficiency.  

2. **Fully Connected Network (FNN)**:
   - Processes metadata (age, sex, lesion location).  

3. **Classification Head**:
   - Combines image and metadata features.
   - Outputs a probability score for malignancy.

### Model Training:  
- **Cross-validation**: 6-fold GroupKFold.  
- **Optimizer**: Adam with `ReduceLROnPlateau` scheduler.  
- **Loss Function**: BCEWithLogitsLoss.  
- **Hyperparameters**:  
  - Epochs: 30  
  - Batch Size: 32  
  - Learning Rate: 0.0001  

---

## **Performance Metrics**  
- **Accuracy**: 75.36%  
- **ROC-AUC**: 93.3%  
- Confusion matrix results and out-of-fold predictions were used to validate performance.  

---

## **Challenges Addressed**  
1. **Class Imbalance**:  
   - Majority class: Benign (~97%).  
   - Addressed via data augmentation and loss weighting.  

2. **Artifacts**:  
   - Hair, patches, and shading in images.  
   - Used preprocessing techniques to mitigate their effects.  

3. **Low Contrast**:  
   - Emphasized feature extraction with EfficientNet.  

---

## **How to Run the Project**  

### Prerequisites:  
- Python 3.8+  
- Install dependencies:  
  ```bash
  pip install -r requirements.txt
  ```

### Steps:  
1. Clone the repository:  
   ```bash
   git clone https://github.com/yourusername/melanoma-detection
   cd melanoma-detection
   ```

2. Run the notebook:  
   ```bash
   jupyter notebook "Melanoma Detection Using SIIM-ISIC.ipynb"
   ```

3. Train and test the model using the preprocessed dataset.

---

## **Contributors**  
This project was collaboratively developed by:
- **Pukar Baral**  
- **Chandu Narasimhareddyvari**  
- **Eswar Naga Lakshman Chalamalasetty**

---

## **License**  
This project is licensed under the MIT License. See `LICENSE` for more details.

---

## **Acknowledgments**  
- **SIIM** and **ISIC** for providing the dataset.  
- Our mentors and peers for their guidance and feedback.

---
