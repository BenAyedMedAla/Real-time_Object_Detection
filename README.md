# Real-time Object Detection with YOLO

A real-time object detection application using YOLOv8 and OpenCV that detects and identifies objects through your webcam feed with bounding boxes and confidence scores.

## Features

- **Real-time Detection**: Live object detection through webcam
- **80 Object Classes**: Detects 80 different object classes from the COCO dataset
- **Confidence Scoring**: Displays confidence percentage for each detection
- **Bounding Boxes**: Visual rectangular boundaries around detected objects
- **Class Labels**: Shows the name of detected objects on screen

## Prerequisites

- Python 3.7 or higher
- Webcam connected to your computer
- CUDA-compatible GPU (optional, for faster inference)

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/BenAyedMedAla/Real-time_Object_Detection.git
   cd Real-time_Object_Detection
   ```

2. **Install required packages**
   ```bash
   pip install -r requirements.txt
   ```


## Project Structure

```
Real-time_Object_Detection/
│
├── main.py                 # Main application file
├── requirements.txt        # Python dependencies
├── README.md              # Project documentation
└── yolo-Weights/
    └── yolov8n.pt         # YOLO model weights
```

## Usage

1. **Run the application**
   ```bash
   python main.py
   ```

2. **Controls**
   - The webcam window will open automatically
   - Objects will be detected in real-time with bounding boxes
   - Press `q` to quit the application

## Detected Object Classes

The model can detect 80 different object classes including:

**People & Animals**: person, bird, cat, dog, horse, sheep, cow, elephant, bear, zebra, giraffe

**Vehicles**: bicycle, car, motorbike, aeroplane, bus, train, truck, boat

**Everyday Objects**: bottle, cup, fork, knife, spoon, bowl, chair, sofa, bed, laptop, cell phone

**Food Items**: banana, apple, sandwich, orange, broccoli, carrot, hot dog, pizza, donut, cake

*And many more...*

## Technical Details

- **Model**: YOLOv8 Nano (yolov8n.pt)
- **Input Resolution**: 640x480 pixels
- **Framework**: Ultralytics YOLO
- **Computer Vision**: OpenCV
- **Detection Threshold**: Configurable confidence scoring

## Configuration

You can modify the following parameters in `main.py`:

- **Camera Resolution**: Change `cap.set(3, 640)` and `cap.set(4, 480)` for different resolutions
- **Bounding Box Color**: Modify `(255, 0, 255)` in the `cv2.rectangle()` function
- **Text Properties**: Adjust font, scale, color, and thickness for object labels
- **Model**: Replace `yolov8n.pt` with other YOLO variants (yolov8s.pt, yolov8m.pt, etc.) for different speed/accuracy trade-offs

## Performance Notes

- **YOLOv8n**: Fastest inference, good for real-time applications
- **YOLOv8s/m/l/x**: Higher accuracy but slower inference
- GPU acceleration significantly improves performance
- Lower resolution increases speed but may reduce detection accuracy

## Troubleshooting

**Camera not detected:**
- Ensure your webcam is properly connected
- Try changing `cv2.VideoCapture(0)` to `cv2.VideoCapture(1)` or higher numbers

**Low FPS:**
- Reduce camera resolution
- Use a GPU if available
- Switch to YOLOv8n for faster inference

**Model not found:**
- Ensure `yolov8n.pt` is in the `yolo-Weights/` directory
- Check the file path in the code matches your directory structure

## Requirements

See `requirements.txt` for the complete list of dependencies:
- ultralytics
- opencv-python
- torch
- torchvision
- numpy

## Contributing

Feel free to submit issues, fork the repository, and create pull requests for any improvements.
