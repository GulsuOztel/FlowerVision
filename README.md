# 🌸 FlowerVision – Deep Learning Based Flower Classification

FlowerVision is a deep learning project that classifies flower images into five different categories using Convolutional Neural Networks (CNN) with TensorFlow and Keras.

The project compares three different CNN architectures and evaluates their classification performance.

## Project Objective

The main objective is to develop an image classification model that can recognize five types of flowers:

- Daisy
- Dandelion
- Roses
- Sunflowers
- Tulips

## Dataset

The project uses the [TF Flowers dataset](https://www.tensorflow.org/datasets/catalog/tf_flowers) provided by TensorFlow Datasets.

- **Total images:** 3,670
- **Number of classes:** 5

| Flower Class | Number of Images |
|---|---:|
| Dandelion | 898 |
| Daisy | 633 |
| Tulips | 799 |
| Sunflowers | 699 |
| Roses | 641 |
| **Total** | **3,670** |

The dataset was divided into three subsets:

| Dataset | Images | Percentage |
|---|---:|---:|
| Training | 2,936 | 80% |
| Validation | 367 | 10% |
| Test | 367 | 10% |

## Technologies and Libraries

- Python
- TensorFlow
- Keras
- TensorFlow Datasets
- NumPy
- Matplotlib
- Scikit-learn

## Data Preprocessing

The following preprocessing techniques were applied:

- **Resizing:** Images were resized to 128 × 128 pixels.
- **Normalization:** Pixel values were scaled from 0–255 to 0–1.
- **Shuffling:** Training data was shuffled.
- **Batching:** Images were processed in batches of 32.
- **Data Augmentation:** RandomFlip, RandomRotation and RandomZoom were applied to training images.

## Model Architectures

Three CNN models were developed and compared.

| Model | Architecture | Parameters |
|---|---|---:|
| V1 | Flatten + Dense(128) | 7,392,965 |
| V2 | Data Augmentation + Flatten + Dense(64) | 3,706,181 |
| V3 | Data Augmentation + GlobalAveragePooling2D | 23,877 |

All models used the Adam optimizer and sparse categorical cross-entropy loss function.

## Model Comparison

| Model | Best Validation Accuracy | Minimum Validation Loss |
|---|---:|---:|
| V1 | 71.12% | 0.9330 |
| V2 | 74.11% | 0.7489 |
| V3 | 65.40% | 0.9456 |

Model V2 achieved the best validation accuracy and was selected as the final model.

## Final Model Evaluation

The selected V2 model was evaluated on the test dataset.

- **Test Accuracy:** 76.57%
- **Test Loss:** 0.6103

### Classification Report

| Class | Precision | Recall | F1-score |
|---|---:|---:|---:|
| Dandelion | 0.78 | 0.73 | 0.76 |
| Daisy | 0.79 | 0.75 | 0.77 |
| Tulips | 0.71 | 0.74 | 0.72 |
| Sunflowers | 0.84 | 0.95 | 0.89 |
| Roses | 0.71 | 0.65 | 0.68 |

The model achieved its highest recall for Sunflowers (0.95). Roses was the most challenging class, with a recall of 0.65.

## Project Results

The following visualizations are included in the project:

- Data augmentation examples
- Class distribution
- Model accuracy comparison
- Model loss comparison
- Confusion matrix

## Project Structure

```text
FlowerVision/
│
├── notebooks/
│   └── FlowerVision.ipynb
│
├── models/
│   └── flower_vision_model.keras
│
├── results/
│   ├── data_augmentation.png
│   ├── class_distribution.png
│   ├── accuracy_comparison.png
│   ├── loss_comparison.png
│   └── confusion_matrix.png
│
├── README.md
└── requirements.txt
```

## Installation

Clone the repository:

```bash
git clone https://github.com/GulsuOztel/FlowerVision.git
cd FlowerVision
```

Install the required libraries:

```bash
pip install -r requirements.txt
```

Open the notebook in Google Colab or Jupyter Notebook to explore the implementation.

## Future Improvements

- Experimenting with different CNN architectures.
- Applying transfer learning with MobileNetV2.
- Increasing dataset diversity.
- Improving classification performance for visually similar flower classes.

## Author

**Ümmügülsüm Öztel**

Computer Engineering

## Acknowledgements

Dataset: [TensorFlow Datasets – TF Flowers](https://www.tensorflow.org/datasets/catalog/tf_flowers)
