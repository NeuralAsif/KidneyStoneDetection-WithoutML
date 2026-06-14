# Kidney Stone Detection-WithoutML

A lightweight and interpretable kidney stone detection system developed using classical image processing techniques on CT scan images, without using Machine Learning or Deep Learning models.
<img width="1341" height="747" alt="Image" src="https://github.com/user-attachments/assets/2e934c84-8c37-4734-b89c-0fe86bf8ff75" />
## Overview

Kidney stone disease is one of the most common urinary tract disorders affecting millions of people worldwide. Early detection is crucial to prevent severe pain, urinary obstruction, infections, and kidney damage.

This project presents an automated kidney stone detection pipeline using traditional image processing methods. The system analyzes CT scan images, identifies potential kidney stone regions, and highlights detected stones without requiring any training data, neural networks, or large computational resources.

The project is designed for educational, research, and medical image processing purposes.

## Features

* CT scan image analysis
* Fully image-processing-based approach
* No Machine Learning or Deep Learning required
* Automatic body region extraction
* Noise reduction and image enhancement
* Threshold-based stone segmentation
* Morphological filtering
* Connected component analysis
* Kidney Region of Interest (ROI) extraction
* Stone localization and counting
* Visualization of every processing stage
  
## Methodology

The proposed system follows the pipeline below:

### 1. Image Acquisition

* Load CT scan image
* Convert image from BGR to RGB
* Convert image to grayscale

### 2. Preprocessing

* Gaussian Blur for noise reduction
* Contrast enhancement preparation
* Background suppression

### 3. Body Region Extraction

* Binary thresholding
* Largest contour extraction
* Body mask generation
* Removal of irrelevant outer regions

### 4. Segmentation

* High-intensity thresholding
* Extraction of potential stone regions

### 5. Morphological Processing

* Morphological opening
* Dilation
* Noise removal
* Shape refinement

### 6. Spine Removal

* Connected Component Analysis
* Vertebra filtering based on:

  * Area
  * Position
  * Centroid location

### 7. Kidney ROI Extraction

* Left kidney region masking
* Right kidney region masking
* Removal of irrelevant anatomical structures

### 8. Stone Candidate Analysis

For each detected object:

* Area calculation
* Perimeter calculation
* Circularity analysis

Circularity Formula:

[
Circularity = \frac{4\pi A}{P^2}
]

where:

* A = Area
* P = Perimeter

### 9. Stone Detection

Objects satisfying predefined constraints are classified as kidney stones.

### 10. Visualization

The system displays:

* Original CT Image
* Grayscale Image
* Enhanced Image
* Thresholded Image
* Morphological Output
* Spine Removed Output
* Kidney ROI
* Final Detection Result

---

## Processing Workflow

Input CT Scan

↓

Preprocessing

↓

Body Extraction

↓

Threshold Segmentation

↓

Morphological Cleaning

↓

Spine Removal

↓

Kidney ROI Selection

↓

Contour Analysis

↓

Kidney Stone Detection

↓

Result Visualization

---

## Technologies Used

* Python 3.x
* OpenCV
* NumPy
* Matplotlib

---

## Installation

Clone the repository:

```bash
git clone https://github.com/your-username/Kidney-Stone-Detection-WithoutML.git
cd Kidney-Stone-Detection-WithoutML
```

Install dependencies:

```bash
pip install opencv-python numpy matplotlib
```

---

## Usage

Update the image path inside the script:

```python
image_path = r"your_ct_scan_image.jpg"
```

Run:

```bash
python main.py
```

The program will:

1. Process the CT image
2. Detect potential kidney stones
3. Highlight detected regions
4. Display intermediate processing stages
5. Output the total number of detected stones

---

## Example Output

### Detection Information

```text
================================
STONE DETECTED
================================
Area        : 35.5
Perimeter   : 22.41
Circularity : 0.889
```

### Final Result

```text
FINAL RESULT: 2 Kidney Stone(s) Detected
```

---

## Advantages

* No training dataset required
* Fast execution
* Low computational cost
* Easy to understand and modify
* Explainable detection process
* Suitable for academic projects and image processing courses

---

## Limitations

* Threshold values may require adjustment for different datasets
* ROI selection is rule-based
* Performance depends on CT image quality
* Not intended for clinical diagnosis
* Less robust than modern deep learning approaches

---

## Future Improvements

* Automatic kidney segmentation
* Adaptive thresholding
* Multi-slice CT support
* Stone size estimation
* Stone volume measurement
* Integration with machine learning models
* Clinical dataset evaluation

---

## Disclaimer

This project is developed for educational and research purposes only. It should not be used as a substitute for professional medical diagnosis or clinical decision-making.

---

## Author

**Md. Asaduzzaman Asif**

Department of Computer Science and Engineering

Southeast University, Bangladesh

---

## License

This project is released under the MIT License.
