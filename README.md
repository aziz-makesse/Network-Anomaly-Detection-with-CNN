# Network-Anomaly-Detection-with-CNN
A hands‑on example that turns UNSW‑NB15 network records into 6×6 grayscale images and trains a simple Convolutional Neural Network to separate normal traffic from attacks.

--

## Setup

1. Install dependencies

2. Get the data:
   ```bash
    kaggle datasets download -d dhoogla/unswnb15
    unzip unswnb15.zip -d data/unswnb15

--

## Pipeline Overview

1. Load & merge training and testing Parquet files.

2. Keep numeric columns, pad to 36 features, normalize to 0–255.

3. Reshape each record into a 6×6 image and save as PNG under images/.

4. Create TensorFlow datasets (image_dataset_from_directory), scale pixels to 0–1.

5. Define & train a small CNN (Conv → Pool → Dense → Sigmoid).

6. Evaluate on validation set and display sample predictions.

--

## Results

- Validation accuracy: ~91.7%

- Sample inference:

  - Normal image predicted as normal (99.9% confidence)

  - Attack image predicted as attack (82.9% confidence)
 
