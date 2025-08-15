🔥 Fire and Smoke Detection using YOLO
📖 Project Description

This project is a computer vision-based fire and smoke detection system built using the YOLO (You Only Look Once) object detection model.
The main objective is to identify fire or smoke in images, videos, or live camera feeds with high accuracy and speed.

The system is trained on a custom dataset containing images of fire and smoke, labeled in YOLO format. The model learns to draw bounding boxes around the detected areas and classify them as either "fire" or "smoke."
It is especially useful for safety monitoring, early fire detection, and wildfire prevention.

Key highlights of the project:

Uses YOLOv11s (lightweight YOLO version) for faster inference.

Dataset split into train, validation, and test sets.

Configurable parameters for image size, learning rate, optimizer, etc.

Works in Google Colab or local Python environments.

🛠️ Code Explanation (Step-by-Step)

Here’s the step-by-step process followed in the code:

Import YOLO and Setup Environment

Install the ultralytics package (YOLO framework).

Import necessary modules for model training and prediction.

Dataset Configuration

A data.yaml file is used to define the dataset paths:

train → path to training images

val → path to validation images

test → path to testing images

Also defines the class names: fire and smoke.

Model Training

The YOLO training command is run with parameters:

task: detect (object detection task)

mode: train (to start training)

data: path to the data.yaml file

model: yolo11s.pt (pre-trained YOLO small model)

epochs: 80 (training cycles)

imgsz: 640 (image size for processing)

batch: 32 (batch size for training)

patience: 15 (stop if no improvement)

lr0: 0.0005 (learning rate)

optimizer: AdamW (optimization algorithm)

Data augmentations like HSV adjustments, mixup, and mosaic are also applied to improve robustness.

Monitoring Training

YOLO automatically logs:

Training loss

mAP (mean Average Precision)

Precision and recall values

Best model weights are saved in runs/detect/train/weights/best.pt.

Running Predictions

The mode=predict option is used with the trained model to run detection on new data.

The source parameter specifies the input:

Path to an image file

Path to a video file

0 for webcam feed

YOLO outputs:

Bounding boxes

Class labels (fire or smoke)

Confidence scores

Saving Results

YOLO saves all detection outputs in a folder under runs/detect/.

This includes processed images/videos with bounding boxes drawn.

Evaluation

The test set is used to check model performance.

Evaluation metrics include mAP50 and mAP50-95.

Higher values mean better accuracy.
