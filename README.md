## 🧠**Brain Tumor Detection Using Convolutional Neural Network (CNN) and Open-CV**

What is a Brain Tumor?

A brain tumor is an abnormal growth of cells in or around the brain.
These cells multiply uncontrollably and form a mass (tumor) that can affect brain function by pressing on nearby tissues or altering brain activity.

In medical terms, brain tumors can be classified as:

1) Benign (non-cancerous): Grow slowly and don’t usually spread.

2) Malignant (cancerous): Grow rapidly and can invade surrounding brain tissue.

	In medical imaging and AI research, brain tumor detection is an important task because:

Early detection can save lives, Manual diagnosis from MRI scans is time-consuming and requires expertise and Deep learning models, like Convolutional Neural Networks (CNNs), can automatically
detect and classify tumors from MRI images, helping radiologists make faster and more accurate decisions.


### **1. Project Overview**

Brain tumor detection from MRI scans is a critical problem in medical image analysis.
This project leverages a **Convolutional Neural Network (CNN)** built with **TensorFlow and Keras** as well as Open-CV to classify brain MRI images as either:

* **Tumor present (Yes)**
* **No tumor (No)**

The model achieved:

* **88% accuracy**
* **ROC–AUC score of 0.86**
* **93% recall on tumor images**, indicating strong sensitivity for detecting positive cases.

---

The dataset employed in this study consists of Brain MRI images used for the classification of tumorous and non-tumorous cases. All images are stored in .jpeg format and are grayscale MRI scans of the human brain. The dataset is divided into two categories:

“yes”: images of patients diagnosed with a brain tumor.

“no”: images of patients with no visible brain tumor.


### **3. Data Preprocessing**

Data PreprocessinTo ensure uniformity and improve model performance, several preprocessing steps were applied to the Brain MRI dataset prior to training, Canny edge detection algorithm (cv2.Canny(img, 100, 200)) was applied to emphasize the structural edges and boundaries within each MRI scan.
This enhancement improved the model’s ability to identify tumor regions, leading to higher recall and overall accuracy, particularly in cases where a brain tumor
was present

### **4. Model Evaluation**

| Metric              | Score |
| :------------------ | :---- |
| **Accuracy**        | 0.88  |
| **ROC–AUC**         | 0.86  |
| **Precision (Yes)** | 0.88  |
| **Recall (Yes)**    | 0.93  |
| **F1-score (Yes)**  | 0.90  |

The trained CNN model demonstrated strong performance in classifying MRI scans as either tumorous or non-tumorous. It achieved an overall accuracy of 88% and a ROC–AUC score of 0.86, indicating good discriminative ability between the two classes.

The model showed particularly strong results for the “Yes” (tumor present) class, achieving a precision of 0.88, recall of 0.93, and an F1-score of 0.90, suggesting effective detection of positive (tumor) cases with minimal false negatives.

The confusion matrix further confirms this trend, with 14 true positives and only 1 false negative, showing the model’s reliability in identifying tumor cases.         

<div style="display: flex; align-items: flex-start; justify-content: space-between; gap: 20px;">

  <div>
    <h4>Classification Report</h4>
    <table>
      <tr><th>Class</th><th>Precision</th><th>Recall</th><th>F1-Score</th><th>Support</th></tr>
      <tr><td>No (Tumor)</td><td>0.88</td><td>0.78</td><td>0.82</td><td>9</td></tr>
      <tr><td>Yes (Tumor)</td><td>0.88</td><td>0.93</td><td>0.90</td><td>15</td></tr>
      <tr><td><b>Accuracy</b></td><td></td><td></td><td><b>0.88</b></td><td>24</td></tr>
      <tr><td><b>Macro Avg</b></td><td>0.88</td><td>0.86</td><td>0.86</td><td>24</td></tr>
      <tr><td><b>Weighted Avg</b></td><td>0.88</td><td>0.88</td><td>0.87</td><td>24</td></tr>
    </table>
  </div>

  <div>

  </div>
<img width="448" height="352" alt="Confusion Matrix" src="https://github.com/user-attachments/assets/43fb8405-cd7c-4390-be80-72d1d6b58408" />

</div>




#### **ROC–AUC Curve**

A smooth ROC curve with AUC = **0.86**, showing good separability between the two classes.

<img width="428" height="335" alt="ROC-AUC" src="https://github.com/user-attachments/assets/4eb3c26c-e250-4848-aaf5-b3f9bd280140" />

---

### **5. Observations**

* The CNN effectively detects tumor regions, with **high recall (93%)** — crucial in medical diagnostics where false negatives are costly.
* Accuracy and AUC indicate strong model performance despite a relatively small test set.
* Data augmentation and early stopping helped prevent overfitting.

---
