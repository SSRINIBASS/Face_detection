

# Face Detection with OpenCV

This project is a straightforward implementation of face detection using Python and the OpenCV library. It provides scripts to detect human faces in both real-time video streams from a webcam and static images.


*(Image shows a successful face detection from the `face1.py` script)*

## 📜 Table of Contents

- [Features](#-features)
- [How It Works](#-how-it-works)
- [Prerequisites](#-prerequisites)
- [Installation](#-installation)
- [Usage](#-usage)
- [File Structure](#-file-structure)
- [Contributing](#-contributing)
- [License](#-license)
- [Acknowledgments](#-acknowledgments)

## ✨ Features

- **Real-time Face Detection**: Detects faces from a live webcam feed.
- **Static Image Face Detection**: Detects faces in a provided image file (`.jpg`, `.png`, etc.).
- **Haar Cascade Classifier**: Utilizes OpenCV's powerful and pre-trained Haar Cascade algorithm for robust frontal face detection.
- **Simple & Minimalist**: The code is easy to understand, making it a great starting point for beginners in computer vision.

## ⚙️ How It Works

The detection process relies on a machine learning-based approach where a cascade function is trained from a large set of positive and negative images. This project uses a pre-trained model provided by OpenCV.

1.  **Load the Classifier**: The script first loads the `haarcascade_frontalface_default.xml` file, which contains the pre-trained data for detecting frontal faces.
2.  **Image/Frame Preparation**:
    - For video, it captures frames one by one from the webcam.
    - For a static image, it loads the image file.
3.  **Grayscale Conversion**: The captured frame or image is converted to grayscale. Haar cascades perform better and faster on single-channel grayscale images.
4.  **Detection**: The `detectMultiScale` function is called on the grayscale image. It scans the image at multiple scales to find objects that match the trained features (in this case, faces). It returns a list of coordinates `(x, y, w, h)` for each detected face.
5.  **Drawing Rectangles**: The script iterates through the detected coordinates and draws a green rectangle around each face on the original color image/frame.
6.  **Display**: The final output with the rectangles is displayed in a window.

## 📋 Prerequisites

Before you begin, ensure you have the following installed:
- [Python 3.7+](https://www.python.org/downloads/)
- `pip` (Python package installer)

## 🚀 Installation

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/SSRINIBASS/Face_detection.git
    cd Face_detection
    ```

2.  **Install the required Python libraries:**
    It's recommended to use a virtual environment.
    ```bash
    # Create and activate a virtual environment (optional but recommended)
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`

    # Install dependencies
    pip install opencv-python numpy
    ```

## ▶️ Usage

The project contains two main scripts for different use cases.

### 1. Real-time Detection (from Webcam)

This script will open your primary webcam and perform face detection in real-time.

- **To run:**
  ```bash
  python face.py
  ```
- **To quit:**
  Press the **'q'** key while the video window is active.

### 2. Static Image Detection

This script will detect faces in the `ronaldo.jpg` image included in the repository.

- **To run:**
  ```bash
  python face1.py
  ```
- **To quit:**
  Press any key to close the image window.

> **Note:** You can modify `face1.py` to use a different image by changing the filename in the line `img = cv2.imread('ronaldo.jpg')`.

## 📁 File Structure

```
.
├── face.py                # Main script for real-time webcam face detection
├── face1.py               # Script for face detection in a static image
├── face2.py               # An alternative script for face detection
├── haarcascade_frontalface_default.xml # Pre-trained model for face detection
└── ronaldo.jpg            # Sample image used by face1.py
```

## 🤝 Contributing

Contributions are welcome! If you have suggestions for improvements or find any bugs, please feel free to open an issue or submit a pull request.

1.  Fork the Project
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4.  Push to the Branch (`git push origin feature/AmazingFeature`)
5.  Open a Pull Request

## 📄 License

This project is not licensed. All rights are reserved by the author. Please contact the repository owner for permissions regarding use, modification, and distribution.

## 🙏 Acknowledgments

-   This project relies heavily on the **OpenCV** library.
-   The pre-trained Haar Cascade model is provided by the OpenCV team.
