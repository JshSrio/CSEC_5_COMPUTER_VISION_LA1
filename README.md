# Laboratory Activity 1: Philippine Coin Detection
### Convolution, Spatial Filtering, and Edge Detection

## Overview
This Jupyter Notebook demonstrates a traditional computer-vision pipeline using images of Philippine coins. It processes three selected coin images and visualizes how grayscale conversion, noise reduction, convolution-based sharpening, Canny edge detection, and morphological cleanup affect the images.

The selected coins add up to **₱21.10**:
- **20 Piso** — ₱20.00
- **1 Piso** — ₱1.00
- **10 Sentimo** — ₱0.10

> **Note:** This notebook processes the coin images specified in the dataset. It does not automatically recognize arbitrary coins or capture new photos.

## Objectives
- Load and display the selected coin images.
- Convert images to grayscale.
- Reduce image noise while retaining important edges.
- Apply a sharpening kernel using convolution.
- Detect edges with the Canny algorithm.
- Clean the edge maps using morphological operations and connected-component filtering.
- Display and save intermediate and final visualizations.

## Processing Pipeline
1. **Load and prepare images** — Each image is read, center-cropped to a square, resized to 420 × 420 pixels, and combined for display.
2. **Grayscale conversion** — Converts each RGB image to a single intensity channel.
3. **Noise reduction** — Applies a median filter followed by Gaussian blur.
4. **Convolution / sharpening** — Uses a 3 × 3 sharpening kernel with `cv2.filter2D` to emphasize details.
5. **Canny edge detection** — Uses thresholds calculated from each sharpened image's median intensity.
6. **Edge cleanup** — Applies morphological closing and removes small connected components.
7. **Final visualization** — Highlights cleaned edges, labels each coin and its value, and displays the total.
8. **Export results** — Saves pipeline visualizations to the `outputs/` directory.

## Technologies Used
- Python
- Jupyter Notebook
- OpenCV (`cv2`)
- NumPy
- Matplotlib

## Requirements
Install the required Python packages:

```bash
pip install opencv-python numpy matplotlib
```

Run the notebook in Jupyter Notebook, JupyterLab, or Google Colab. The notebook uses `%matplotlib inline`, which is supported in notebook environments.

## Dataset Setup
The notebook currently expects the coin images in this Google Drive directory:

```text
/content/drive/MyDrive/COINS-20260815T115822Z-1-001/COINS
```

The configured filenames are:

| Coin | Expected filename |
|---|---|
| 20 Piso | `20.jpg` |
| 1 Piso | `Philippine peso - Wikiwand.jpeg` |
| 10 Sentimo | `File_2009phil10centobv_jpg - Wikimedia Commons.jpeg` |

Update `DATASET_DIR` in the notebook if your dataset is stored elsewhere. Make sure the filenames match exactly. If using Google Colab with Google Drive, mount your Drive before running the notebook.

## How to Run
1. Open `LA1_Sario.ipynb` in Jupyter Notebook, JupyterLab, or Google Colab.
2. Make sure the required coin image files are available in the dataset directory.
3. Install the dependencies if they are not already installed.
4. Update `DATASET_DIR` if necessary.
5. Run the notebook cells from top to bottom.
6. Review the stage-by-stage plots and the full pipeline summary.
7. Check the `outputs/` directory for the saved image files.

## Output Files
When the notebook completes successfully, it creates an `outputs/` directory containing:

| File | Description |
|---|---|
| `0_full_pipeline_summary.png` | Combined figure showing the processing stages |
| `1_original_combined.png` | Original selected coin images combined side by side |
| `2_grayscale_filtered.png` | Images after grayscale conversion and noise reduction |
| `3_convolution_sharpened.png` | Sharpened images after convolution |
| `4_edge_detected_final.png` | Cleaned edge-detection result |
| `5_final_annotated_result.png` | Annotated edge result with coin labels, values, and total |

## Expected Total
The notebook calculates the selected coin values and displays the total:

**₱20.00 + ₱1.00 + ₱0.10 = ₱21.10**


