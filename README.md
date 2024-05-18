# YOLOv5 Custom Dataset Application

This repository contains my work on using the [YOLOv5](https://github.com/ultralytics/yolov5) object detection model on a custom dataset. The original YOLOv5 repository by [Ultralytics](https://github.com/ultralytics) can be found [here](https://github.com/ultralytics/yolov5).

## Overview

YOLOv5 is a state-of-the-art object detection model that provides excellent accuracy and performance. This project demonstrates how to train YOLOv5 on a custom dataset and evaluate its performance.

## Features

- Clone of the original YOLOv5 repository.
- Training of YOLOv5 on a custom dataset.
- Evaluation of the trained model on a custom test set.
- Instructions and scripts for reproducing the results.

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/YOLOV5CustomDataset.git
   cd your-repo-name

2. Install the requirements
   ```bash
   pip install -r requirements.txt

3. Preparing the Custom Dataset
   ```bash
   data/
   ├── my_custom_dataset/
   │   ├── images/
   │   │   ├── train/
   │   │   │   ├── img1.jpg
   │   │   │   ├── img2.jpg
   │   │   │   └── ...
   │   │   ├── val/
   │   │   │   ├── img1.jpg
   │   │   │   ├── img2.jpg
   │   │   │   └── ...
   │   │   ├── test/
   │   │   │   ├── img1.jpg
   │   │   │   ├── img2.jpg
   │   │   │   └── ...
   │   ├── labels/
   │   │   ├── train/
   │   │   │   ├── img1.txt
   │   │   │   ├── img2.txt
   │   │   │   └── ...
   │   │   ├── val/
   │   │   │   ├── img1.txt
   │   │   │   ├── img2.txt
   │   │   │   └── ...
   │   │   ├── test/
   │   │   │   ├── img1.txt
   │   │   │   ├── img2.txt
   │   │   │   └── ...

5. Create a dataset configuration file my_custom_dataset.yaml
   ```bash
   train: data/my_custom_dataset/images/train
   val: data/my_custom_dataset/images/val
   test: data/my_custom_dataset/images/test
   
   nc: 2  # number of classes
   names: ['class1', 'class2']  # list of class names

7. Training Model
   To train YOLOv5 on your custom dataset, run:
   ```bash
   python train.py --img 640 --batch 16 --epochs 100 --data data/my_custom_dataset.yaml --weights yolov5s.pt
9. Testing Model
    To evaluate the trained model on the test set, run:
   ```bash
   python val.py --data data/my_custom_dataset.yaml --weights runs/train/exp/weights/best.pt --img 640 --task test

10. Results
The training and evaluation results, including loss curves and other metrics, can be found in the runs/ directory.


#### Acknowledgements
The original YOLOv5 repository: [Ultralytics YOLOv5](https://github.com/ultralytics/yolov5)
