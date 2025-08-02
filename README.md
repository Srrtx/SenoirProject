# Breast Cancer Classification Project

This project aims to classify breast cancer images using deep learning techniques. The dataset used for training and evaluation is the BUSI dataset, which contains images labeled as malignant, benign, and normal.

## Project Structure

- **data_split/**: Contains subdirectories for training, validation, and testing datasets.
- **Dataset_BUSI_with_GT/**: Contains the original dataset used for training and testing the model.
- **mymodel.ipynb**: Jupyter notebook for experimentation and interactive development.
- **requirements.txt**: Lists the dependencies required for the project.

## Model Training Configuration and Techniques
- **Data Split** : Training set 70% ,Validation set: 15% ,and Test set: 15%
- **Basic Parameters**
  - Batch size: 32
  - Number of epochs: 80
  - Image size: 224 x 224
  - Learning rate: 0.001
  - Number of classes: 3 (benign, malignant, normal)

- **Model Architecture**
  Base model: ResNet50 (pretrained on ImagaNet)

- **Class Balancing Techniques**
  - Class weights computed using 'compute_class_weight('balanced')'
  - Weighted CrossEntropyLoss
  - WeightedRandomSampler for dynamic sampling

- **Data Augmentation**
  - RandomHorizontalFlip
  - Resize to 224x224
  - Normalization (ImageNet statistics): 
      - mean=[0.485, 0.456, 0.406] 
      - std=[0.229, 0.224, 0.225]

- **Optimization**
  - Optimizer: AdamW
    - Weight decay: 0.01
  - Learning rate scheduler: ReduceLROnPlateau
    - Mode: min (monitoring validation loss)
    - Factor: 0.5
    - Patience: 5
    - Minimum learning rate: 1e-5

- **Early Stopping**
  - Patience: 10 epochs
  - Monitoring: validation loss

- **Best Model Selection**
  - Saves model with best validation accuracy
  - Implements model checkpointing

- **Performance Metrics**
  - Accuracy
  - Precision
  - Recall
  - F1-score
  - Confusion Matrix

## Notes

- Ensure that you have the necessary libraries installed as specified in `requirements.txt`.
- This project is designed for educational purposes and may require further tuning and validation for practical applications.