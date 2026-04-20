# Week 3 - Task 2: Video Stacking (Raw vs Detection vs Segmentation)

## 🎯 Objective

Combine three videos:

* Raw video (original frames)
* Object Detection output
* Object Segmentation output

Stack them vertically to compare results.

---

## 🛠️ Steps Performed

### 1. Created Raw Video

```bash
ffmpeg -framerate 2 -pattern_type glob -i "images_input/*.jpg" raw.mp4
```

---

### 2. Generated Detection Output

```bash
yolo task=detect mode=predict model=yolov8n.pt source=images_input save=True
```

Converted detection images to video:

```bash
ffmpeg -framerate 2 -pattern_type glob -i "runs/detect/predict/*.jpg" detect.mp4
```

---

### 3. Used Segmentation Output

Already generated in Task 1:

```
runs/segment/predict/output2.mp4
```

Renamed to:

```
segment.mp4
```

---

### 4. Stacked All Videos

```bash
ffmpeg -i raw.mp4 -i detect.mp4 -i segment.mp4 \
-filter_complex "[0:v][1:v][2:v]vstack=inputs=3[v]" \
-map "[v]" stacked.mp4
```

---

## 🎥 Final Output

* Final video: `stacked.mp4`

---

## 📌 Observations

* Detection shows bounding boxes around objects
* Segmentation highlights objects with colored masks
* Stacked video makes comparison clear and easy

---

## 🚀 Conclusion

Stacking raw, detection, and segmentation outputs provides a clear visual comparison of different computer vision techniques.
