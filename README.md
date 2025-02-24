# Face Detection and Tracking on Raspberry Pi

## Overview
This project utilizes a Raspberry Pi camera module to detect and track faces in real-time using OpenCV, Dlib, and a custom deep learning-based face detector (dnn module). The script captures video frames, detects faces, and tracks them using Dlib's correlation tracker.

## Features
- Uses **Raspberry Pi Camera Module** for real-time video capture.
- **Face detection** using a deep learning model with a confidence threshold.
- **Face tracking** with Dlib's correlation tracker.
- Displays bounding boxes around detected faces.

## Requirements
- Raspberry Pi (tested on Raspberry Pi 3B/4)
- Raspberry Pi Camera Module
- Python 3
- OpenCV
- Dlib
- NumPy

## Installation
1. Update and install dependencies:
   ```sh
   sudo apt update && sudo apt upgrade
   sudo apt install python3-pip python3-opencv libatlas-base-dev
   ```
2. Install required Python libraries:
   ```sh
   pip3 install dlib numpy imutils
   ```
3. Clone the repository (if applicable) or copy the script to your Raspberry Pi.

## Usage
Run the script using:
```sh
python3 face_tracking.py
```

## Configuration
- Adjust the **camera resolution** by modifying:
  ```python
  RES_W = 256  # Width
  RES_H = 144  # Height
  ```
- Modify the **face detection threshold** (0-1, higher is stricter):
  ```python
  THRESHOLD = 0.6
  ```
- To exit the program, press **'q'** while the OpenCV window is active.

## How It Works
1. The Raspberry Pi camera captures frames.
2. The first frame is processed using the face detection model.
3. Detected faces are initialized with Dlib’s correlation tracker.
4. For subsequent frames, the correlation tracker updates and tracks the detected faces.
5. Bounding boxes are drawn around detected faces.

## Troubleshooting
- If the script does not detect faces properly, try lowering the `THRESHOLD` value.
- Ensure your Raspberry Pi camera module is properly connected and enabled (`sudo raspi-config`).
- If performance is slow, reduce the resolution (`RES_W` and `RES_H`).

## Future Improvements
- Implement multi-face tracking with unique identifiers.
- Optimize face detection with a more efficient deep learning model.
- Add a logging system to store detected face data.

## License
--

