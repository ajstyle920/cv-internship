# Week 4 - Task 1: Understanding YOLO Dataset Structure

## 🎯 Objective

The objective of this task is to explore and understand the dataset structure and configuration files used in YOLO models.

---

## 📁 Dataset Structure

The YOLO dataset consists of the following main components:

* **images/** → Contains all training and validation images
* **labels/** → Contains annotation files corresponding to each image
* **coco128-seg.yaml** → Configuration file describing dataset structure

Inside the folders:

* `images/train2017/` → training images
* `labels/train2017/` → corresponding label files

Each image has a label file with the same name.

---

## 📄 YAML File Analysis

The YAML file defines how YOLO loads and understands the dataset.

Example structure:

```yaml
path: ../datasets/coco128-seg
train: images/train2017
val: images/train2017

names:
  0: person
  1: bicycle
  2: car
  3: motorcycle
```

### Explanation:

* **path** → Root directory of dataset
* **train** → Path to training images
* **val** → Path to validation images
* **names** → Mapping of class IDs to object names

This file acts as a blueprint for training and evaluation.

---

## 🏷️ Label Files

Each image has a corresponding `.txt` file in the labels folder.

Format of each line:

```
class_id x_center y_center width height
```

### Details:

* `class_id` → Object category (e.g., person, car)
* `x_center, y_center` → Center of bounding box
* `width, height` → Size of bounding box
* All values are **normalized (between 0 and 1)**

Each line represents one object in the image.

---

## 🖼️ Images

The images folder contains real-world images used for training and validation.

YOLO reads these images and uses corresponding label files to learn object detection.

---

## 📌 Observations

* YAML file defines dataset structure and class information
* Labels provide object positions and categories
* Each image-label pair is essential for training
* Normalized coordinates make the model resolution-independent

---

## 🚀 Conclusion

Understanding the dataset structure and configuration files is important for working with YOLO models.
It helps in debugging, training custom datasets, and improving model performance.

---

## 📚 References

* https://docs.ultralytics.com/
* https://docs.ultralytics.com/datasets/
