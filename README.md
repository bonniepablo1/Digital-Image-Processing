Digital Image Processing (DIP) Lab 2: Canny Edge Detection Across Diverse Imaging Domains

Overview

This repository contains the Google Colaboratory notebook for Digital Image Processing (DIP) Lab 2, focusing on the application and parameter tuning of the Canny edge detection algorithm across a variety of imaging domains. The lab explores how Canny edge detection performs in different contexts, highlighting the importance of parameters like Gaussian blur (blur_sigma) and hysteresis thresholds (t_low, t_high).


To run this notebook, you will need:

A Google account to access Google Colaboratory.

Google Drive for saving output images and managing the folder structure.

Running the Notebook:
Mount Google Drive: The first step in the notebook mounts your Google Drive to /content/drive, creating a dedicated directory DIP_Lab2 with subfolders for images and outputs.

Install Libraries: Necessary libraries such as scikit-image, Pillow, OpenCV (cv2), and NumPy are installed and imported.

Execute Cells Sequentially: Run each code cell in order, from top to bottom. The notebook is structured to guide you through the process.

Lab Exercises / Domains Explored
The lab investigates Canny edge detection in six distinct imaging domains:

Medical Imaging (MRI): Analyzing brain MRI slices to detect subtle anatomical boundaries.

Remote Sensing (Satellite): Identifying features in satellite-like imagery.

Robot Vision: Detecting object boundaries in complex scenes.

Forensics (Fingerprint): Capturing the fine ridges of a synthetic fingerprint.

Microscopic Imaging (Cells): Outlining cellular structures.

JPEG Compression Artefacts: Examining the impact of heavy JPEG compression on edge detection.

Core Functionality

detect_edges(image, t_low, t_high, blur_sigma, label): A custom function that encapsulates the Canny edge detection process, including greyscale conversion, Gaussian blurring, and Canny's internal pipeline. It also reports edge pixel statistics.

show_domain(original, edges, domain_name, filename, cmap_orig): A utility function to display the original image alongside its Canny edge map and save the resulting figure to Google Drive.

Summary of Findings & Parameter Impact

Parameter Impact

blur_sigma (Gaussian Smoothing): Crucial for balancing noise reduction and detail preservation.

Low sigma leads to noisy, speckled edges.

Optimal sigma provides clean edges while preserving fine details.

High sigma causes over-smoothing, losing fine features.

t_low and t_high (Hysteresis Thresholds): Control the sensitivity of edge detection.

Lower thresholds are effective for images with subtle gradients (e.g., Medical, Fingerprint).

Higher thresholds are suitable for images with distinct, strong edges (e.g., Satellite), filtering out weaker details.

Domain-Specific Observations

Medical Imaging (MRI): Requires careful blur_sigma tuning for subtle anatomical structures.

Remote Sensing (Satellite): Handled well with moderate blur_sigma and thresholds for outlining features.

Robot Vision: Effectively identifies object boundaries; highlights the challenge of differentiating structural vs. texture edges.

Forensics (Fingerprint): Requires minimal blurring and very low thresholds to capture fine ridge patterns due to smooth gradients.

Microscopic Imaging (Cells): Moderate parameters effectively isolate cellular outlines.

JPEG Compression Artefacts: Canny is sensitive to compression-induced noise; heavily compressed images produce noisier, less coherent edge maps.

Strengths of Canny

Robustness: Effective across a wide variety of image types.

Optimality: Designed for good detection, localization, and minimal response.

Parameter Control: Tunable parameters allow adaptation to different image characteristics.

Clear Output: Produces thin, clear edges.

Limitations of Canny

Parameter Sensitivity: Requires careful, often domain-specific, tuning.

Sensitivity to Noise/Artefacts: Can generate spurious edges from noise or compression artefacts.

Computational Cost: More intensive than simpler detectors.

No Semantic Understanding: Identifies intensity discontinuities but not what the edges represent.
