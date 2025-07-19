YOLOv4-DeepSort Object Tracking System
=====================================

Developed by Krishna Vats 
4th Year Computer Science Student
Email: krishnavats336@gmail.com
GitHub: https://github.com/krishnavats123

Project Overview:
-----------------
A robust computer vision system combining YOLOv4 object detection with DeepSORT tracking algorithm to:
- Detect 80+ object classes in real-time
- Maintain persistent IDs for tracked objects
- Generate analyzed video outputs with visual tracking data

System Requirements:
--------------------
- Operating System: Windows 10/11 (Linux compatible with modifications)
- Python: 3.7.x (recommended for stability)
- Hardware:
  * Minimum: 8GB RAM, CPU-only operation
  * Recommended: NVIDIA GPU with CUDA support
  * Disk Space: 2GB+ for models and dependencies

Installation Guide:
-------------------
1. Python Setup:
   - Download Python 3.7 from python.org
   - Install with "Add Python to PATH" option enabled

2. Dependency Installation:
   python get-pip.py
   python -m pip install --upgrade pip
   python -m pip install -r requirements-gpu.txt

3. Model Setup:
   - Download weights:
     * yolov4.weights (full model)
     * yolov4-tiny.weights (lightweight)
   - Place in /checkpoints folder
   - Convert weights:
     python save_model.py --weights ./checkpoints/yolov4.weights --output ./checkpoints/yolov4-416 --model yolov4

Usage Instructions:
------------------
Basic Command:
python object_tracker.py --video [input_path] --output [output_path]

Common Options:
--video       Input video path (0 for webcam)
--output      Output video save path
--tiny        Use YOLOv4-tiny for faster processing
--size        Frame size (default: 416)
--count       Display object count
--info        Show detailed tracking info

Example Use Cases:
1. Traffic Analysis:
   python object_tracker.py --video traffic.mp4 --output analyzed.mp4 --count

2. Real-time Webcam:
   python object_tracker.py --video 0 --output webcam_out.mp4 --tiny

Troubleshooting:
----------------
1. Missing Dependencies:
   - Verify all packages in requirements-gpu.txt are installed
   - Check Python version compatibility

2. Performance Issues:
   - Use --tiny flag for faster processing
   - Reduce --size parameter (e.g., 320)
   - Close background applications

3. Model Errors:
   - Confirm weights files are in /checkpoints
   - Verify successful model conversion

Customization Options:
----------------------
1. Modify detection classes:
   Edit /data/classes/coco.names

2. Adjust sensitivity:
   --score (detection threshold)
   --iou (overlap threshold)

3. Advanced:
   Edit object_tracker.py for custom logic

Project Structure:
-----------------
yolov4-deepsort/
├── checkpoints/    # Model weights
├── data/           # Test videos & configs
├── outputs/        # Processed results
├── core/           # Detection algorithms
└── object_tracker.py # Main application

Performance Notes:
------------------
- YOLOv4-tiny: ~30-60 FPS (GPU)
- Full YOLOv4: ~10-30 FPS (GPU)
- CPU-only: Significantly slower

Contact:
--------
For questions, collaborations or contributions:
Email: krishna vats@gmail.com
GitHub: https://github.com/krishna vats

License:
--------
Open-source for educational and research purposes