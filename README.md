# Selective Cloud Offloading for Accurate and Efficient Object Detection

## Overview
High-accuracy object detection on resource-constrained devices is challenging due to computational limitations. This repository provides the implementation of a **Selective Cloud Offloading** approach that balances cost and accuracy by dynamically offloading uncertain detections to the cloud. The system leverages **Conformal Prediction** to quantify uncertainty and selectively offloads high-uncertainty regions to cloud-based object detection models.

## Features
- **Hybrid Object Detection:** Combines lightweight edge detection (YOLOv5-Tiny) with high-accuracy cloud-based models (Mask-RCNN).
- **Uncertainty-Aware Offloading:** Uses conformal prediction to determine which detections require cloud processing.
- **Cost-Effective Optimization:** Implements an image-stitching strategy to reduce cloud transmission and computational overhead.
- **User-Controlled Trade-offs:** Allows users to configure the balance between accuracy and cloud processing costs.
- **Near Cloud-Level Accuracy:** Achieves comparable accuracy while offloading less than 20% of the data.

## Repository Structure
```
├── src/                    # Source code for object detection and offloading
│   ├── edge_model.py       # Edge-based object detection (YOLOv5-Tiny)
│   ├── cloud_model.py      # Cloud-based object detection (Mask-RCNN)
│   ├── offloading.py       # Selective offloading decision logic
│   ├── image_stitching.py  # Optimization for cloud transmission
│   ├── evaluation.py       # Performance analysis and metrics
├── data/                   # Sample datasets
├── notebooks/              # Jupyter notebooks for experiments
├── results/                # Evaluation results and figures
├── README.md               # Project documentation
├── requirements.txt        # Required dependencies
└── LICENSE                 # License information
```

## Installation
Clone the repository and install the required dependencies:
```bash
git clone https://github.com/ddehghani/SmartOffload-OD.git
cd SmartOffload-OD
pip install -r requirements.txt
```

## Usage
### 1. Running Edge Object Detection
Run the edge model locally:
```bash
python src/edge_model.py --input data/sample.jpg
```
### 2. Selective Offloading
Execute the offloading mechanism:
```bash
python src/offloading.py --input data/sample.jpg
```
### 3. Running the Cloud Model
Process high-uncertainty detections on the cloud:
```bash
python src/cloud_model.py --input data/offloaded.jpg
```
### 4. Evaluating Performance
Compare accuracy and cost trade-offs:
```bash
python src/evaluation.py
```

## Experiments & Results
The system was evaluated on multiple image datasets, demonstrating:
- **Comparable accuracy** to full cloud offloading.
- **Over 80% reduction** in cloud data transmission.
- **Lower computational cost** compared to existing offloading methods.

## Citation
If you use this work in your research, please cite:
```
@article{dehghani2025selective,
  author    = {Davood Dehghani and Yueting Chen and Xiaohui Yu},
  title     = {Selective Cloud Offloading for Accurate and Efficient Object Detection},
  journal   = {PVLDB},
  year      = {2025},
  doi       = {XX.XX/XXX.XX}
}
```

## License
This project is licensed under the **MIT License**. See [LICENSE](LICENSE) for details.

## Acknowledgments
We thank **York University** and **Seattle University** for supporting this research. Special thanks to our advisors for their guidance and feedback.

## Contact
For any questions or collaborations, feel free to reach out:
- **Davood Dehghani** (dehghani@yorku.ca)
- **Yueting Chen** (yestinmail@gmail.com)
- **Xiaohui Yu** (xhyu@yorku.ca)
