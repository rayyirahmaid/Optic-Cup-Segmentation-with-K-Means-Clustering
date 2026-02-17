# Retinal Image Processing: Optic Disc & Optic Cup Analysis

This repository contains Python/Jupyter Notebook scripts for processing and analyzing retinal fundus images. The project focuses on data exploration through color histograms and automatic segmentation of the Optic Cup (OC) using K-Means Clustering. This type of image processing pipeline is commonly used in medical imaging, particularly for assisting in the detection of glaucoma.

## 📌 Features & File Overview

This project consists of three main Jupyter Notebook (`.ipynb`) files, designed to be easily run on **Google Colab** or any local Jupyter environment.

* **`eksplorasi_histogram.ipynb`**
  * Reads full RGB retinal images and separates them into independent Red, Green, and Blue (RGB) channels.
  * Calculates and visualizes the pixel intensity distribution (histogram) for each specific color channel.
  * Useful for preliminary data exploration and understanding the color properties of the retinal images.

* **`overlay_histogram.ipynb`**
  * Performs comparative visual analysis by overlaying histograms from two different data subsets (e.g., Red channel of Optic Disc vs. Red channel of Optic Cup).
  * Normalizes the histogram data to ensure accurate comparisons regardless of the region's pixel count.

* **`segmentasi_kmeans.ipynb`**
  * Extracts the green channel from the retinal image, as it typically provides the best contrast for Optic Cup boundaries.
  * Applies **K-Means Clustering** (`k=7`) to automatically group pixels by intensity and isolates the brightest region (the Optic Cup).
  * Utilizes Mathematical Morphology (Closing with an elliptical structuring element) to refine the segmentation mask and fill in gaps.
  * Applies connected-component analysis to remove noise and fits an ellipse over the detected Optic Cup for final visualization.

---

## 🛠️ Requirements & Dependencies

To run the code in this repository, you will need Python 3.x and the following libraries:

* `opencv-python` (cv2)
* `numpy`
* `matplotlib`
* `scikit-image` (skimage)
* `scipy`

*Note: If you are using Google Colab, these libraries are already pre-installed.*

---

## 🚀 How to Use (Google Colab)

1. **Clone the Repository:** Download these `.ipynb` files to your local machine or directly upload them to your Google Drive.
2. **Prepare your Dataset:** Organize your retinal images (e.g., `.png`, `.jpg`) into specific folders on your Google Drive.
3. **Open in Google Colab:** Open the notebooks using Google Colab.
4. **Mount Google Drive:** Run the provided cell at the top of the notebooks to connect Colab to your Drive:
   ```python
   from google.colab import drive
   drive.mount('/content/drive')
