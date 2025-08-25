# ⚽ Football Player Tracker

A real-time football player tracking application that uses computer vision and YOLO object detection to track players and generate movement heatmaps.

![Python](https://img.shields.io/badge/python-v3.8+-blue.svg)
![OpenCV](https://img.shields.io/badge/OpenCV-4.0+-green.svg)
![YOLO](https://img.shields.io/badge/YOLO-v8-orange.svg)
![License](https://img.shields.io/badge/license-MIT-blue.svg)

## 🎯 Features

- **Real-time Player Detection**: Uses YOLOv8 for accurate person detection
- **Player Tracking**: Maintains consistent player IDs across frames
- **Interactive Video Player**: Play, pause, and seek through video footage
- **Movement Heatmaps**: Visual representation of player movement patterns
- **User-friendly GUI**: Built with Tkinter for easy interaction
- **Football Pitch Overlay**: Contextual field visualization

## 📸 Screenshots

### Main Interface
![Football Player Tracker Interface](https://github.com/Ahmed7Saker/yolo-/blob/main/Screenshot%202025-01-12%20005324.png)

*Live player tracking with real-time detection boxes and movement heatmap visualization*

### Features Shown
- ✅ Real-time player detection with bounding boxes
- ✅ Player ID assignment and tracking
- ✅ Movement heatmap overlay on football pitch
- ✅ Video playback controls with frame navigation
- ✅ Interactive player selection dropdown

## 🚀 Quick Start

### Prerequisites

```bash
# Python 3.8 or higher
python --version

# Required packages
pip install ultralytics opencv-python matplotlib pillow numpy
```

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/football-player-tracker.git
   cd football-player-tracker
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Download YOLO model** (automatic on first run)
   ```bash
   # YOLOv8n model will be downloaded automatically
   # Or manually download: wget https://github.com/ultralytics/assets/releases/download/v0.0.0/yolov8n-seg.pt
   ```

4. **Run the application**
   ```bash
   python Main.py
   ```

## 🎮 Usage

### Basic Operation

1. **Load Video**: Click "Open Video File" and select your football video
2. **Start Tracking**: Click "Play" to begin player detection and tracking
3. **View Heatmaps**: Select a player from the dropdown to view their movement heatmap
4. **Navigate**: Use the slider to jump to specific frames

### Supported Formats
- **Video**: MP4, AVI, MKV
- **Resolution**: Any (automatically scaled)
- **Frame Rate**: Any

### Controls
- `Play/Pause`: Start or stop video playback
- `Slider`: Navigate to specific frames
- `Player Dropdown`: Select player for heatmap visualization

## 🏗️ Architecture

```
├── PlayerTracker          # Core tracking logic
│   ├── YOLO Detection    # Person detection using YOLOv8
│   ├── ID Assignment     # Player ID tracking across frames
│   └── Position Storage  # Movement data collection
│
├── TrackerGUI            # User interface
│   ├── Video Display    # OpenCV video rendering
│   ├── Controls         # Play/pause/seek functionality
│   └── Heatmap Canvas   # Matplotlib visualization
│
└── Main                  # Application entry point
```

## 🔧 Configuration

### Tracking Parameters

```python
# In PlayerTracker.__init__()
MAX_DISTANCE = 100      # Maximum pixel distance for ID assignment
TRACK_HISTORY = 30      # Number of recent positions to maintain
HEATMAP_BINS = 50      # Histogram resolution for heatmaps
```

### Performance Tuning

- **CPU Usage**: Reduce frame rate with `self.root.after(10)` delay
- **Memory Usage**: Adjust `TRACK_HISTORY` length
- **Detection Accuracy**: Use different YOLO models (`yolov8s.pt`, `yolov8m.pt`)

## 📊 Technical Details

### Dependencies
```
ultralytics>=8.0.0    # YOLOv8 object detection
opencv-python>=4.0    # Video processing
matplotlib>=3.0       # Heatmap visualization
pillow>=8.0          # Image processing
numpy>=1.20          # Numerical computations
tkinter              # GUI framework (built-in)
```

### Algorithm Overview

1. **Frame Processing**: Extract frames from video stream
2. **Object Detection**: YOLO identifies person bounding boxes
3. **ID Assignment**: Track players using proximity-based matching
4. **Position Storage**: Maintain cumulative position history
5. **Visualization**: Generate real-time heatmaps

## 🤝 Contributing

We welcome contributions! Here's how to get started:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Development Setup

```bash
# Install development dependencies
pip install -r requirements-dev.txt

# Run tests
python -m pytest tests/

# Format code
black Main.py
```

## 🐛 Troubleshooting

### Common Issues

**YOLO Model Download Fails**
```bash
# Manually download
wget https://github.com/ultralytics/assets/releases/download/v0.0.0/yolov8n-seg.pt
```

**Video Won't Load**
```bash
# Check OpenCV installation
python -c "import cv2; print(cv2.__version__)"

# Install codec support
pip install opencv-python-headless
```

**GUI Not Responsive**
- Ensure video resolution isn't too high
- Close other applications to free memory
- Try using a lighter YOLO model

**Poor Tracking Accuracy**
- Adjust `MAX_DISTANCE` parameter
- Use higher quality YOLO model
- Ensure good video quality and lighting

## 📋 Requirements

### System Requirements
- **OS**: Windows 10+, macOS 10.14+, Ubuntu 18.04+
- **RAM**: 8GB minimum, 16GB recommended
- **GPU**: Optional (CUDA support for faster processing)
- **Python**: 3.8+ required

### Hardware Recommendations
- **CPU**: Multi-core processor (Intel i5/AMD Ryzen 5+)
- **GPU**: NVIDIA GTX 1060+ for GPU acceleration
- **Storage**: 2GB free space for models and cache

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [Ultralytics](https://ultralytics.com/) for YOLOv8
- [OpenCV](https://opencv.org/) for computer vision tools
- [Matplotlib](https://matplotlib.org/) for visualization
- Football community for inspiration

## 📞 Support

- **Issues**: [GitHub Issues](https://github.com/yourusername/football-player-tracker/issues)
- **Discussions**: [GitHub Discussions](https://github.com/yourusername/football-player-tracker/discussions)
- **Email**: support@yourproject.com

---

⭐ **Star this repository if you found it helpful!**

Made with ❤️ by [Ahmed7Saker](https://github.com/Ahmed7Saker)

