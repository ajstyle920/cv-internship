# Week 4 Task 2 – Custom YOLO Dataset Creation

## 📌 Objective

The goal of this task is to create a labeled dataset for object detection using YOLO format.

---

## 📂 Dataset Creation Pipeline

### 1. Video Collection

* Used a real-world video containing people, bicycles, and cars.

### 2. Frame Extraction

* Extracted frames using FFmpeg at 10 FPS.
* Generated approximately 600 images.

### 3. Dataset Splitting

* Training set: 100 images
* Validation set: 40 images
* Test set: Remaining images

---

## 🏷️ Annotation

* Tool used: Label Studio

* Task: Object Detection (Bounding Boxes)

* Classes:

  * Person
  * Bicycle
  * Car

* Images were manually labeled using bounding boxes.

---

## 📁 Dataset Structure

dataset/
├── images/
│   ├── train/
│   ├── val/
│   └── test/
├── labels/
│   ├── train/
│   ├── val/
│   └── test/

---

## 📄 YOLO Format

Each label file contains:

class_id x_center y_center width height

(All values are normalized between 0 and 1)

---

## ⚙️ Configuration

### data.yaml

path: ./dataset
train: images/train
val: images/val

names:
0: person
1: bicycle
2: car

---

## 🚀 Outcome

* Successfully created a custom YOLO-compatible dataset
* Learned dataset preparation, annotation, and structuring
* Ready for training using YOLO models

---

## 📌 Notes

* Ensured proper alignment between images and labels
* Maintained consistent naming conventions
* High-quality annotations improve model performance
