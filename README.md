# 🎯 Real-Time Object Detection System

A lightweight, real-time object detection system using YOLOv8 for Google Colab with webcam support.

## 📋 Features

- ✅ Real-time webcam object detection
- ✅ Detects 80 different object classes (people, bottles, phones, etc.)
- ✅ Adjustable confidence thresholds
- ✅ Clean, non-overlapping labels
- ✅ Color-coded confidence levels
- ✅ Robust error handling

## 🚀 Quick Start

### 1. Installation
```python
!pip install ultralytics opencv-python-headless
```

### 2. Setup Webcam
```python
setup_webcam()
# Allow camera permissions when prompted
# Wait for "Camera ready" message
```

### 3. Test Camera
```python
test_capture()
# Should display a captured frame
```

### 4. Run Detection
```python
run_detection(num_frames=5, conf_threshold=0.25, delay=1.0)
```

## ⚙️ Configuration

### Detection Parameters

| Parameter | Default | Description | Recommended Range |
|-----------|---------|-------------|-------------------|
| `num_frames` | 5 | Number of frames to process | 3-20 |
| `conf_threshold` | 0.25 | Minimum confidence for detection | 0.15-0.7 |
| `delay` | 1.0 | Seconds between frames | 0.5-2.0 |

### Usage Examples

```python
# Fast scanning (more detections)
run_detection(10, 0.2, 0.5)

# High confidence only
run_detection(5, 0.6, 1.5)

# Single frame test
test_capture()
```

## 🎨 Visual Features

- **Green boxes**: High confidence (>70%)
- **Orange boxes**: Medium confidence (50-70%)
- **Red boxes**: Low confidence (<50%)
- **Smart labels**: Auto-positioned to avoid overlap
- **Live counter**: Shows detection count in top-left

## 📊 Supported Object Classes

The model can detect 80 classes including:
- **People**: person
- **Vehicles**: car, motorcycle, bus, truck, bicycle
- **Animals**: dog, cat, bird, horse
- **Everyday items**: bottle, cup, phone, laptop, book
- **Food**: banana, apple, sandwich, pizza
- [Full list available in COCO dataset]

## 🔧 Troubleshooting

### Camera Not Working
```python
# 1. Refresh page and restart runtime
# 2. Re-run setup_webcam()
# 3. Use Chrome browser for best compatibility
```

### No Detections Appearing
```python
# Lower the confidence threshold
run_detection(5, conf_threshold=0.15)
```

### Objects Not Detected
- Move object closer to camera
- Ensure good lighting
- Lower confidence threshold to 0.2 or below
- Make sure object is in supported classes

## 🛠️ Technical Stack

- **Model**: YOLOv8n (Nano - lightweight & fast)
- **Framework**: Ultralytics YOLO
- **Platform**: Google Colab
- **Language**: Python 3.x
- **Libraries**: OpenCV, NumPy

## 📈 Performance

- **Speed**: ~30-50ms per frame (YOLOv8n)
- **Accuracy**: 80+ object classes
- **Resolution**: 640x480 default
- **Model Size**: ~6MB (yolov8n)

## 🎓 Model Variants

Upgrade for better accuracy:

```python
# Faster but less accurate (default)
model = YOLO("yolov8n.pt")  # Nano

# Better accuracy, slightly slower
model = YOLO("yolov8s.pt")  # Small
model = YOLO("yolov8m.pt")  # Medium

# Best accuracy, slower
model = YOLO("yolov8l.pt")  # Large
model = YOLO("yolov8x.pt")  # Extra Large
```

## 📝 Project Structure

```
├── Cell 1: Installation
├── Cell 2: Imports
├── Cell 3: Webcam Setup
├── Cell 4: Frame Capture Function
├── Cell 5: Test Capture
├── Cell 6: Load YOLO Model
├── Cell 7: Detection Function
└── Cell 8: Run Detection Loop
```

## 🤝 Use Cases

- Security monitoring
- Inventory management
- Retail analytics
- Smart home automation
- Educational demonstrations
- Computer vision research

## 📄 License

Uses YOLOv8 by Ultralytics (AGPL-3.0)

## 🔗 Resources

- [YOLOv8 Documentation](https://docs.ultralytics.com/)
- [COCO Dataset Classes](https://cocodataset.org/)
- [OpenCV Documentation](https://docs.opencv.org/)

## 💡 Tips for Best Results

1. **Lighting**: Ensure good, even lighting
2. **Distance**: Keep objects 1-3 feet from camera
3. **Stability**: Hold camera steady or use tripod
4. **Threshold**: Start at 0.25, adjust based on results
5. **Performance**: Use YOLOv8n for speed, YOLOv8m+ for accuracy

---

**Made with using YOLOv8 and Google Colab**