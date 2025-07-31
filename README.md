# YOLO-v11-network-Toy-Classifier
I used the YOLO v11 network trained on a database created with sample images of Bakugan toys to predict on images and recorded/real-time videos of Bakugans, in order for it to serve as an identifier for new people getting into the collection hobby.

---

## **Object Detection in Computer Vision**
Every day, we encounter countless objects around us. As humans, we effortlessly recognize and locate them—a task so intuitive it requires no conscious effort.

For computers, however, object detection is a complex challenge. It involves analyzing an image (or video frame) and returning two key pieces of information:
1. **Classification** – Identifying what objects are present.
2. **Localization** – Determining their precise locations.

Over the years, various solutions have emerged to tackle this problem. One of the most advanced is **YOLO (You Only Look Once)**, a real-time object detection algorithm known for its speed and accuracy. In this article, we’ll explore how YOLO works and how to train it on custom datasets using TensorFlow/Keras.

---

## **How YOLO Works: Speed and Efficiency**
Unlike traditional detectors that analyze images in multiple stages, YOLO processes an entire image in a single pass. Here’s how:

1. **Grid-Based Detection** – The image is divided into a grid, with each cell predicting bounding boxes and class probabilities for objects within it.
2. **Non-Maximum Suppression (NMS)** – Since multiple boxes may detect the same object, NMS filters out redundant predictions:
   - First, it discards low-confidence detections (e.g., scores below 0.5).
   - Then, it compares overlapping boxes and keeps only the most confident one, removing duplicates.

For example, in car detection, YOLO generates multiple candidate boxes, but NMS ensures only the most accurate predictions remain:

![YOLO grid and bounding boxes](https://github.com/user-attachments/assets/d78a4cac-03d8-4a70-967b-713de2980ec2)
*YOLO’s grid-based predictions before NMS.*

![NMS filtering](https://github.com/user-attachments/assets/1dfc28d7-0f10-4bc6-8199-65f063384b34)
*NMS eliminates overlapping low-confidence boxes.*

![Final high-confidence detections](https://github.com/user-attachments/assets/404a6d5d-5acf-4e84-a5b0-7a8f21138cee)
*Final predictions after NMS.*

---

## **Why YOLO Outperforms Traditional Detectors**
While YOLO uses a convolutional neural network (CNN) like other detectors, its **single-stage approach** makes it significantly faster.

### **Two-Stage Detectors (e.g., Faster R-CNN)**
1. **Region Proposal** – First, the algorithm identifies potential object regions.
2. **Classification** – Each region is then processed by a CNN, which is computationally expensive.

### **YOLO’s Single-Stage Advantage**
- Processes the entire image at once.
- Predicts bounding boxes and classes simultaneously.
- Avoids the bottleneck of sequential region classification.

The result? Real-time performance without sacrificing accuracy. Below is a speed comparison with other detectors:

![YOLO speed comparison](https://github.com/user-attachments/assets/3d67beb5-b8de-488c-a62b-0c5981eb2b81)
*YOLO achieves high FPS while maintaining competitive precision.*

---

## Download
Due to the amount of files needed in this project, not all of them were included in this repository. All files and their dependencies can be found in the Google Drive folder below.

https://drive.google.com/drive/folders/1otI1ME5PpbOMAtXxbkFzDK6QmJAVIjGo?usp=sharing

## Test
The following video shows some prediction results on video and images.

https://github.com/user-attachments/assets/28fd05c7-8fa8-4383-b5c5-b4374575124c

---

## References

[1] [YOLOv11 Object Detection on Custom Dataset | Step-by-Step Guide](https://youtu.be/A1V8yYlGEkI?si=wzRrT8xeopZmC1MQ)

[2] https://docs.ultralytics.com/pt/tasks/detect/

[3] https://docs.ultralytics.com/pt/yolov5/tutorials/train_custom_data/

[4] https://towardsdatascience.com/how-to-train-a-custom-object-detection-model-with-yolo-v5-917e9ce13208

[5] https://blog.roboflow.com/how-to-train-yolov8-on-a-custom-dataset/
