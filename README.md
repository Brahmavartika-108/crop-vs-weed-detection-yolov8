🌱 Crop vs Weed Detection using YOLOv8
📌 Overview

Weeds are one of the major challenges in agriculture as they compete with crops for nutrients, water, sunlight, and space. This competition can significantly reduce crop yield and overall agricultural productivity. Farmers often rely on pesticides to remove weeds, but excessive pesticide usage can contaminate crops and harm the environment.

This project presents a deep learning–based weed detection system using YOLOv8 (You Only Look Once) for object detection. The model is trained to identify crop plants and weeds from agricultural field images.

The proposed system can be integrated with precision agriculture technologies, such as smart sprayers or agricultural robots, to apply pesticides selectively only on weeds, reducing chemical usage and improving crop health.

🎯 Project Objectives

The main objectives of this project are:

Detect crops and weeds from field images using deep learning.

Train an efficient object detection model using YOLOv8.

Evaluate the model using multiple performance metrics.

Visualize predictions and detection results.

Provide a foundation for smart pesticide spraying systems.

📂 Dataset

The dataset used in this project is available on Kaggle:

Dataset Source:
https://www.kaggle.com/datasets/utsadas108/crop-vs-weed-dataset

Dataset Details
Feature	Description
Total Images	~1300
Image Resolution	512 × 512
Image Type	RGB
Annotation Format	YOLO
Classes	Crop, Weed
Class Labels
Class ID	Label
0	Crop
1	Weed

Each image has a corresponding .txt file containing bounding box annotations.

Example annotation:

1 0.608398 0.498047 0.541016 0.531250

Format:

class_id center_x center_y width height

All values are normalized between 0 and 1.

🧠 Methodology

The workflow of the project follows these steps:

1️⃣ Dataset Preparation
2️⃣ Train/Validation Split
3️⃣ YOLO Configuration File Creation
4️⃣ Model Training using YOLOv8
5️⃣ Evaluation using multiple metrics
6️⃣ Testing on validation dataset
7️⃣ Manual testing on new images
8️⃣ Visualization of predictions

⚙️ Model Architecture

The model used in this project is YOLOv8 Nano, a lightweight and efficient object detection architecture developed by Ultralytics.

Why YOLOv8?

Real-time object detection

High detection accuracy

Efficient training

Suitable for edge devices and real-world deployment

YOLOv8 predicts:

bounding box location

object confidence score

class probability

in a single forward pass, making it extremely fast.

🏋️ Model Training

The model was trained using the following configuration:

Parameter	Value
Model	YOLOv8n
Epochs	30
Image Size	512
Batch Size	16
Framework	Ultralytics YOLO

Training was performed using the Ultralytics YOLOv8 framework.

📊 Evaluation Metrics

To measure the performance of the model, the following evaluation metrics were used:

Precision

Precision measures how many detected objects are actually correct.

Precision = TP / (TP + FP)
Recall

Recall measures how many actual objects were detected.

Recall = TP / (TP + FN)
Mean Average Precision (mAP)

Mean Average Precision is the standard evaluation metric for object detection models.

Two variations were used:

Metric	Description
mAP@50	IoU threshold of 0.5
mAP@50–95	Average across IoU thresholds from 0.5 to 0.95
📈 Results

The trained model achieved the following performance:

Metric	Score
Precision	~0.84
Recall	~0.83
mAP@50	~0.88
mAP@50-95	~0.57

These results indicate that the model can accurately detect crops and weeds in agricultural images.

📊 Visualizations

Several visualizations were generated to analyze model performance.

Confusion Matrix

The confusion matrix shows the classification performance of the model across crop and weed classes.

(results/confusion_matrix.png)

Precision-Recall Curve

The precision-recall curve illustrates the trade-off between precision and recall at different confidence thresholds.

(results/PR_curve.png)

F1 Score Curve

The F1 score represents the harmonic mean of precision and recall.

(results/F1_curve.png)

Training Performance

Training and validation loss curves are shown below:

(results/results.png)

🔍 Prediction Examples

The trained model was tested on validation images to visualize detection performance.

Detected objects are highlighted with bounding boxes:

🟩 Crop
🟥 Weed

Example predictions are available in the predictions folder.

📁 Repository Structure
crop-vs-weed-detection-yolov8
│
├── README.md
├── requirements.txt
│
├── notebook
│   └── crop_vs_weed_detection.ipynb
│
├── model
│   └── best.pt
│
├── results
│   ├── confusion_matrix.png
│   ├── PR_curve.png
│   ├── F1_curve.png
│   ├── results.png
│   └── metrics_summary.png
│
├── predictions
│   ├── sample_prediction1.jpg
│   ├── sample_prediction2.jpg
│
└── docs
    └── system_architecture.png
🚀 How to Run the Project
Install dependencies
pip install -r requirements.txt
Train the model

Run the training script or notebook.

python train.py
Run predictions
python predict.py
🌍 Applications

This system can be applied in several agricultural technologies:

Smart pesticide spraying systems

Agricultural robots

Drone-based weed monitoring

Precision agriculture systems

Automated crop management tools

🔮 Future Improvements

Possible improvements to this project include:

Expanding the dataset with more crop types

Training deeper YOLO models

Real-time detection using drones

Edge device deployment (Jetson / Raspberry Pi)

Integration with automated spraying systems

👨‍💻 Author

Utsa Das
Internship Project
Uniconverge Technologies

📜 License

This project is released under the MIT License.
