# Fire Detection 🔥

This repository focuses on creating a fire detection system by fine-tuning YOLOv8 on a dedicated dataset for real-time fire detection.

## Overview

YOLO (You Only Look Once) is a pre-trained model capable of detecting up to 80 classes without additional training. However, since fire detection is not among these default classes, we fine-tuned the YOLOv8n model specifically for this task using a dedicated fire detection dataset.

## Architecture

For our implementation, we used the YOLOv8n model, which offers a good balance between speed and accuracy. The training was performed on Kaggle using a P100 GPU, with a total training time of approximately 14 minutes.

### Training Results

<!-- ![Loss Curves](./content/loss_curves.png)
![mAP](./content/mAP.png) -->
<p align="center">
  <img src="./content/loss_curves.png" alt="Loss Curves", width="80%">
</p>
<p align="center">
  <img src="./content/mAP.png" alt="mAP", width="80%">
</p>

## Dataset

We used the [Fire Detection dataset](https://www.kaggle.com/datasets/metinmekiabullrahman/fire-detection) from Kaggle, with the following distribution:

- **Training set:** 1004 images with corresponding labels
- **Validation set:** 754 images with corresponding labels
- **Test set:** 751 images with corresponding labels

The dataset is configured with a `data.yaml` file that defines the class structure.

## Usage

After training, we saved the model weights and created an application (`app.py`) that can load a video and perform inference on each frame to detect fire.

To run the application:

```bash
cd src
python app.py
```
## Demo

<p align="center">
  <img src="./content/demo_screenshot.png" alt="Demo Screenshot" width="70%">
</p>

## Acknowledgements

- [Ultralytics YOLOv8](https://github.com/ultralytics/ultralytics)
- [Fire Detection Dataset](https://www.kaggle.com/datasets/metinmekiabullrahman/fire-detection)