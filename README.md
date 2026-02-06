# Weighing machine
This project builds an object detection model to localize weighing scales with digital screens in images.
A pretrained YOLO model is fine-tuned on a small dataset (~150 images) using automatic labeling followed by supervised training.

# Step-wise brief Project Explanation

# Step 1: Image Collection
All images containing weighing scales with digital screens are collected and placed in a single folder.

# Step 2: Automatic Data Labeling
Since no annotations are provided, bounding boxes are generated automatically:
OCR is used to detect numeric digits on the weighing scale display.
The detected digit region is expanded to cover the full weighing scale.

Bounding boxes are saved in YOLO format.

# Step 3: Dataset Preparation
The labeled data is automatically split into:
Training set (70%)
Validation set (20%)
Test set (10%)
A YOLO-compatible directory structure and data.yaml file are created.

# Step 4: Model Selection
A pretrained YOLOv8-Small object detection model is selected to balance accuracy and training speed on a small dataset.

# Step 5: Model Fine-Tuning
The model is fine-tuned on the labeled dataset using data augmentation such as flipping and color jittering to improve generalization.

# Step 6: Model Evaluation
The trained model is evaluated on the validation set using:
Precision
Recall
mAP@0.5
mAP@0.5:0.95

# Step 7: Inference on Test Images
The final model is run on unseen test images to generate:
Annotated images with bounding boxes
Confidence scores for each detected weighing scale

# Step 8: Results and Output
The project outputs include:
Trained model weights
Annotated inference images

# Step 9: Reproducibility
The entire pipeline is automated and can be executed end-to-end using a single script or notebook, ensuring reproducibility.
