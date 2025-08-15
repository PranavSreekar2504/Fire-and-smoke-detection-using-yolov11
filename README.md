🔥 Fire and Smoke Detection using YOLO
📖 Project Description

This project is a computer vision-based fire and smoke detection system built using the YOLO (You Only Look Once) object detection model.
The main objective is to identify fire or smoke in images, videos, or live camera feeds with high accuracy and speed.

The system is trained on a custom dataset containing images of fire and smoke, labeled in YOLO format. The model learns to:

Draw bounding boxes around detected areas

Classify them as either "fire" or "smoke"

Use Cases:

✅ Safety monitoring in industrial areas

✅ Early fire detection in homes and offices

✅ Wildfire detection in forest surveillance systems

Key Highlights:

🚀 Uses YOLOv11s (lightweight YOLO version) for faster inference

📊 Dataset split into train, validation, and test sets

⚙️ Configurable parameters (image size, learning rate, optimizer, etc.)

💻 Works in Google Colab or local Python environments

🛠️ Code Explanation (Step-by-Step)
1️⃣ Import YOLO and Setup Environment

Install the ultralytics package (YOLO framework)

Import modules for model training and prediction

2️⃣ Dataset Configuration

Use data.yaml file to define dataset paths:

train → path to training images

val → path to validation images

test → path to testing images

Define class names:

names:
  0: fire
  1: smoke

3️⃣ Model Training

Run YOLO training with parameters:

Task: detect (object detection task)

Mode: train (start training)

Data: path to data.yaml

Model: yolo11s.pt (pre-trained YOLO small model)

Epochs: 80

Image size: 640

Batch size: 32

Patience: 15 (stop if no improvement)

Learning rate: 0.0005

Optimizer: AdamW

Also applies data augmentations:

🎨 HSV color space adjustments

🔀 Mixup

🧩 Mosaic

4️⃣ Monitoring Training

YOLO automatically logs:

📉 Training loss

📈 mAP (mean Average Precision)

📊 Precision and recall values

The best model weights are saved at:

runs/detect/train/weights/best.pt

5️⃣ Running Predictions

Use mode=predict with the trained model:

Source options:

🖼 Image file path

🎥 Video file path

📷 0 for webcam

YOLO outputs:

Bounding boxes

Class labels (fire / smoke)

Confidence scores

6️⃣ Saving Results

All outputs are stored in:

runs/detect/


Includes processed images/videos with bounding boxes and labels.

7️⃣ Evaluation

Run model on the test set

Evaluate with metrics:

mAP50

mAP50-95

Higher values → better accuracy
