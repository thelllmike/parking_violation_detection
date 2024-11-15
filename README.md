```
# Parking Violation Detection with YOLOv5

This project uses YOLOv5 to detect cars and parking lines and determine parking violations.

## Requirements
Install the required dependencies:
```bash
pip install -r requirements.txt
```

## How to Run

### Test with Images
Run the following command to test images:
```bash
python detect.py --weights weights/best.pt --img 640 --conf 0.25 --source /path/to/image_or_folder
```

### Test with Videos
Run the following command to test a video:
```bash
python detect.py --weights weights/best.pt --img 640 --conf 0.25 --source /path/to/video.mp4
```

### Real-Time Detection with Webcam
Run the following command to use the webcam:
```bash
python detect.py --weights weights/best.pt --img 640 --conf 0.25 --source 0
```

## Training
To train the model:
```bash
python train.py --img 640 --batch 16 --epochs 50 --data parking_lines.yaml --weights yolov5s.pt
```

## Results
- Detected outputs are saved in `runs/detect/exp`.
- Metrics and training logs are saved in `runs/train/exp4`.

## Project Structure
```
yolov5_project/
├── detect.py          # Script for running detections
├── train.py           # Script for training the model
├── parking_lines.yaml # Dataset configuration file
├── weights/           # Directory for model weights
│   └── best.pt        # Trained YOLOv5 model
├── README.md          # Project documentation
├── .gitignore         # Files and directories to ignore in Git
├── requirements.txt   # Python dependencies
└── parking_env/       # Virtual environment (ignored by .gitignore)
```

## Notes
1. Ensure you update the paths in commands to match your directory structure.
2. For better performance, use a GPU when running training or inference.

## Acknowledgments
- Built with [YOLOv5](https://github.com/ultralytics/yolov5).
```