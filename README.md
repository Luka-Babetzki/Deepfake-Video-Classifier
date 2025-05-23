# Cascade-Classifier-Face-Detection

A simple Python project for face presentation attack detection (real vs. fake face) using Local Binary Patterns (LBP) and a k-Nearest Neighbors (k-NN) classifier.

## Features

- Loads all images from user-specified training and testing folders
- Detects faces using OpenCV's Haar Cascade (Viola-Jones method)
- Extracts LBP features from detected faces
- Trains a k-NN classifier to distinguish between real and fake faces
- Supports evaluation on a test image set or live webcam feed
- Visualizes detection results with bounding boxes and labels

## Requirements

- Python 3.x
- OpenCV
- scikit-image
- NumPy

## Usage

**Install dependencies:**
```
pip install opencv-python scikit-image numpy
```

**Prepare your dataset:**

- Place your training images in `real` and `fake` subfolders inside a folder, e.g. `./data/training/real` and `./data/training/fake`.
- (Optional) Place your testing images in `real` and `fake` subfolders inside a folder, e.g. `./data/testing/real` and `./data/testing/fake`.

**Update the data folder paths at the top of `Cascade-Classifier.py` as needed:**
```python
TrainDir = 'c:/path/to/training/'  # Update this path to your training data folder
# For testing:
TrainDir = 'c:/path/to/testing/'   # Update this path to your testing data folder
```

**Run the script:**

- For webcam testing (default):
  ```
  python Cascade-Classifier.py
  ```
- For image set testing, change `test_way = 'cam'` to `test_way = 'img'` in `Cascade-Classifier.py`, then run:
  ```
  python Cascade-Classifier.py
  ```

Each mode will process and display the detection results, labeling detected faces as "real face" or "fake face". In image mode, accuracy statistics will be printed.

## Notes

- Ensure the dataset paths are correct in the script.
- The training and testing folders must each contain `real` and `fake` subfolders.
- The Haar Cascade XML file (`haarcascade_frontalface_default.xml`) must be present in the project directory.
- The webcam mode opens a live video window; press `Esc` to exit.
- Results may vary depending on the quality and diversity of your training data.