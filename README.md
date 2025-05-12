# PCB Inspection System

[![License](https://img.shields.io/badge/license-MIT-blue)](LICENSE)  [![Python](https://img.shields.io/badge/python-3.8+-yellow.svg)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/pytorch-1.10+-red)](https://pytorch.org/)
[![Flask](https://img.shields.io/badge/flask-2.0+-green)](https://flask.palletsprojects.com/)

This project is an automated Printed Circuit Board (PCB) inspection system that uses AI to detect defects. It combines YOLO for PCB localization and Faster R-CNN for accurate defect identification. A Flask web interface provides a user-friendly way to visualize and analyze inspection results.

![Main Interface Screenshot](path/to/main_interface.png)  <--------- Скриншот общего вида веб-интерфейса

## Table of Contents

-   [Features](#features)
-   [Installation](#installation)
-   [Usage](#usage)
    -   [Web Interface](#web-interface)
    -   [Command Line Interface (CLI)](#command-line-interface-cli)  -   [Dataset](#dataset)
-   [Models](#models)
-   [Evaluation](#evaluation)
-   [Contributing](#contributing)
-   [License](#license)
-   [Acknowledgments](#acknowledgments)

## Features

-   **PCB Localization:** Accurate detection of PCBs in images using YOLO.
-   **Defect Detection:** Identification of various PCB defects (e.g., missing holes, short circuits) using Faster R-CNN.
-   **Real-time Analysis:** Web interface for live camera feed inspection and result visualization.
-   **Image Analysis:** Ability to upload and analyze individual images.
-   **Defect Visualization:** Bounding boxes and labels highlighting detected defects.
-   **Data Saving:** Option to save analyzed images and inspection data.
-   **Model Evaluation:** Scripts for evaluating model performance (mAP, PR curves).
-   **Task Switching:** Dynamically switch between PCB detection and defect detection tasks.

## Installation

1.  **Clone the repository:**

    ```bash
    git clone <YOUR_REPOSITORY_URL>
    cd <YOUR_REPOSITORY_NAME>
    ```

2.  **Install dependencies:**

    ```bash
    # Create a virtual environment (recommended)
    python -m venv venv
    venv\Scripts\activate  # On Windows
    source venv/bin/activate  # On Linux/macOS

    pip install -r requirements.txt
    ```

## Usage

### Web Interface

1.  **Run the Flask application:**

    ```bash
    python app.py
    ```

2.  **Open the web interface in your browser:**

    ```
    [http://127.0.0.1:5001/](http://127.0.0.1:5001/)
    ```

    ![Web Interface - Live Feed](path/to/web_interface_live.png)  <--------- Скриншот веб-интерфейса с живым видеопотоком

    * **Live Camera Feed:** View and analyze the live video stream.
    * **Image Upload:** Upload images for analysis.
    * **Task Selection:** Choose between PCB detection and defect detection.
    * **Analysis Results:** View detected PCBs and defects with bounding boxes and labels.
    * **Save Snapshot:** Save a snapshot of the current frame.
    * **Model Selection:** Option to choose different detection models (if applicable).

    ![Web Interface - Image Upload](path/to/web_interface_upload.png)  <--------- Скриншот веб-интерфейса с загруженным изображением

### Command Line Interface (CLI)  (Describe how to use CLI scripts, if you have them.  For example, for inference or evaluation)

```bash
python inference.py <weights_path> <input_dir> <output_dir>
python evaluate.py <weights_path> <data_dir>
```

## Dataset

(Describe the dataset you used for training/testing. If it's publicly available, provide a link. If not, explain its structure.)

The dataset used for training the defect detection model consists of images of PCBs with annotations for various defect types:

- Missing hole
- Mouse bite
- Open circuit
- Short
- Spur
- Spurious copper

The dataset is organized as follows:

```
data/
├── images/
│   ├── Missing_hole/
│   │   └── image1.jpg
│   │   └── ...
│   ├── Mouse_bite/
│   │   └── image2.jpg
│   │   └── ...
│   └── ...
└── Annotations/
    ├── Missing_hole/
    │   └── image1.xml
    │   └── ...
    ├── Mouse_bite/
    │   └── image2.xml
    │   └── ...
    └── ...
```

## Models

- **YOLO:** Used for PCB localization. (Specify version, if relevant, e.g., YOLOv8)
- **Faster R-CNN:** Used for defect detection. (Specify architecture, e.g., ResNet50-FPN)

(Mention where the pre-trained weights are, or how to train your own models. If you provide pre-trained weights, consider using a cloud storage link if they are large.)

## Evaluation

(Describe how you evaluated your models. Mention metrics like mAP, PR curves, etc. Refer to your evaluation scripts.)

Model performance was evaluated using Mean Average Precision (mAP) and Precision-Recall (PR) curves. Evaluation scripts are provided in the repository (`evaluate.py`, `evaluate_pr.py`, `evaluate_coco.py`).

![PR Curves](path/to/pr_curves.png) <--------- Скриншот графиков Precision-Recall (если есть)

## Contributing

(Explain how others can contribute to your project. Include guidelines for code style, pull requests, etc.)

Contributions are welcome! Please follow these guidelines:

1.  Fork the repository.
2.  Create a new branch for your feature or bug fix.
3.  Make your changes.
4.  Write tests (if applicable).
5.  Ensure all tests pass.
6.  Submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).

## Acknowledgments

(Thank anyone who helped you with the project, e.g., mentors, collaborators, dataset creators.)

Thanks to the creators of the YOLO and Faster R-CNN models.
(Add any other acknowledgments)
