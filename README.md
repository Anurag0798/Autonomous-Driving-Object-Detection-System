# Autonomous Driving Object Detection System

A modular Python project for simulated autonomous driving applications, featuring real-time lane detection and object detection using YOLOv8 and OpenCV. This system demonstrates how to combine computer vision techniques for robust perception - capable of detecting lanes and objects (such as vehicles, pedestrians, and more) in live video streams or recorded driving footage.

## Features

- **Lane Detection:**
  Applies edge detection and Hough Transform to identify driving lanes in each frame using classic computer vision.
- **Real-time Object Detection:**
  Utilizes Ultralytics’ YOLOv8 pre-trained model to detect common road objects with bounding boxes.
- **Dual-Pipeline Fusion:**
  Processes both lane markings and detected objects in one frame, overlaying both visualizations for a complete scene understanding.
- **Live Webcam or Video File Input:**
  Supports real-time webcam demo and processing of pre-recorded video.
- **Easy Extensibility:**
  Modular design with core functionality separated by file for customization.

## Repository Structure
```
.
├── lane_detection.py        # Lane detection module using OpenCV
├── video_processing.py      # Combined lane + object detection for video file input
└── README.md                # Project readme (this file)
```

## Requirements

- Python 3.7+
- opencv-python
- ultralytics  (for YOLOv8)
- numpy

**Install with:**
```bash
pip install opencv-python ultralytics numpy
```

## Getting Started

**1. Clone the repository**
```bash
git clone https://github.com/Anurag0798/Autonomous-Driving-Object-Detection-System.git

cd Autonomous-Driving-Object-Detection-System
```

**2. Install dependencies**
```bash
pip install opencv-python ultralytics numpy
```

**3. Run lane and object detection on a video file**
- Edit the input video path in `video_processing.py` (replace `"Put_video_path_here"` with your file path).
- Then run:
    ```bash
    python video_processing.py
    ```
- The window will display lanes and object detections overlayed together.

## How it Works

- **lane_detection.py:**  
  - Defines a mask to focus on the road/lane area.
  - Detects edges and applies Hough transform to find and visualize lane lines.

- **video_processing.py:**  
  - Reads video file frame-by-frame.
  - Applies lane detection, then YOLOv8 object detection.
  - Overlays results for a comprehensive, driving-scene visualization.

## Customization

- **Model/Thresholds:**  
  Change `"yolov8n.pt"` to another YOLOv8 model or adjust `conf` (confidence) level as desired.
- **Lane Detection ROI:**  
  Modify `region_of_interest()` in `lane_detection.py` for your preferred focus area.

## License

This project is for educational and demonstration purposes. LICENSE file added for further details.

## Acknowledgements

- **Ultralytics** for the YOLOv8 models
- **OpenCV** for robust computer vision primitives

## Contributions

Pull requests are welcome!  
Feel free to fork this repo, experiment, and suggest improvements.
If you use or learn from this project, a star is appreciated!  
For questions or enhancements, open an issue on GitHub.