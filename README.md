# Smart Traffic Light System 🚦

## Overview
This project implements an intelligent traffic light control system that uses Computer Vision to dynamically adjust green light durations based on real-time traffic density. Instead of relying on fixed timers, the system analyzes video feeds to count vehicles and optimizes traffic flow, reducing congestion and wait times.

## Key Features
* **Real-Time Object Detection:** Utilizes the YOLOv8 object detection model to accurately identify and count vehicles (cars, trucks, buses, and motorbikes) in a given frame.
* **Dynamic Timer Logic:** Automatically classifies traffic density into categories (Low, Medium, High) based on vehicle count thresholds.
* **Adaptive Green Lights:** Allocates green light durations dynamically (e.g., 15s for low traffic, 30s for medium, 60s for high) to optimize intersection throughput.

## Tech Stack
* **Language:** Python
* **Computer Vision:** YOLOv8 (Ultralytics), OpenCV
* **Environment:** Google Colab / Jupyter Notebook
* **Dataset:** [Highway Traffic Videos Dataset](https://www.kaggle.com/datasets/aryashah2k/highway-traffic-videos-dataset) (via Kaggle API)

## Execution Output
The model processes the video frame-by-frame, calculating the density and adjusting the timer on the fly. Here is a sample of the execution logs:

```text
Frame 22: Vehicle count = 14, Density = Medium, Green Light Duration = 30s
Frame 23: Vehicle count = 13, Density = Medium, Green Light Duration = 30s
Frame 24: Vehicle count = 15, Density = Medium, Green Light Duration = 30s
Frame 25: Vehicle count = 14, Density = Medium, Green Light Duration = 30s
Frame 26: Vehicle count = 21, Density = High, Green Light Duration = 60s
Frame 27: Vehicle count = 15, Density = Medium, Green Light Duration = 30s
Frame 28: Vehicle count = 15, Density = Medium, Green Light Duration = 30s
```
*(Notice how the duration jumps to 60s at Frame 26 when the vehicle count spikes to 21, demonstrating the adaptive logic).*

## How to Run
1. Clone this repository.
2. Ensure you have your `kaggle.json` API key ready.
3. Install the required dependencies:
   ```bash
   pip install ultralytics opencv-python kaggle
   ```
4. Run the Jupyter Notebook. The script will automatically download the dataset, load the YOLOv8n weights, and begin the simulation.
