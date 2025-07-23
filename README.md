# Yolo-Vehicle_speed_detection
Vehicle Speed Detection
An AI-powered system to detect vehicles in video footage and estimate their speeds. This project helps in monitoring traffic, identifying overspeeding vehicles, and generating reports for traffic management.

🚀 Features Vehicle detection using YOLOv8

Speed calculation using pixel displacement → real-world calibration

Real-time or recorded video processing

Automatic overspeed alert generation

Logs of detected vehicles with timestamp, speed, and vehicle type

🛠️ Tech Stack Python 3.x

OpenCV

YOLOv8 (Ultralytics)

NumPy

Matplotlib (optional, for visualization)

Tkinter/Streamlit (optional, for UI/dashboard)

📁 Project Structure

├── models/ │ └── yolov8_weights.pt # Pre-trained YOLOv8 model weights ├── videos/ │ └── input_video.mp4 # Input video files ├── outputs/ │ └── logs.csv # Detected vehicles and speeds ├── main.py # Main program ├── requirements.txt # Required Python libraries └── README.md # Project documentation ⚙️ Installation Clone the repository:

git clone https://github.com/VijayKanagaraj7/vehicle-speed-detection.git cd vehicle-speed-detection Install dependencies:

pip install -r requirements.txt Download YOLOv8 weights:

pip install ultralytics yolo download model=yolov8n.pt Place input videos in the videos/ directory.

▶️ Usage python main.py --input videos/input_video.mp4 --output outputs/logs.csv Optional arguments:

--threshold_speed → Set speed limit (e.g., 60 km/h)

--show → Display real-time video with annotations

📐 Speed Calculation Logic Detect vehicles → Get bounding boxes.

Track center points of bounding boxes across frames.

Measure displacement in pixels → Convert to meters using calibration.

Use time difference between frames → Calculate speed = distance / time.

Calibration is based on a known reference object or manual input for real-world scaling.

✅ Results Accuracy: ~90% speed estimation accuracy in controlled environments.

Output: CSV file with vehicle ID, speed, timestamp, and overspeed flag.

🖼️ Sample Output Vehicle ID Speed (km/h) Timestamp (s) Status 1 45.6 5.3 Normal 2 78.2 7.1 Overspeed

📌 Future Improvements Integrate real-time streaming (e.g., from CCTV)

Automatic license plate recognition (ALPR)

Web dashboard for visualization (Streamlit/Flask)

