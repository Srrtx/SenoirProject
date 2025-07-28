# Breast Cancer Classification Project

This project aims to classify breast cancer images using deep learning techniques. The dataset used for training and evaluation is the BUSI dataset, which contains images labeled as malignant, benign, and normal.

## Project Structure

- **data_split/**: Contains subdirectories for training, validation, and testing datasets.
- **Dataset_BUSI_with_GT/**: Contains the original dataset used for training and testing the model.
- **src/**: Contains the source code for the project.
  - **data_augmentation.py**: Implements data augmentation techniques to enhance the training dataset.
  - **oversampling.py**: Implements oversampling techniques specifically for the malignant class to balance the dataset.
  - **model.py**: Defines the model architecture for the breast cancer classification task.
  - **train.py**: Contains the training loop for the model.
  - **evaluate.py**: Responsible for evaluating the trained model on validation and test datasets.
  - **utils.py**: Contains utility functions used across the other modules.
- **new.ipynb**: Jupyter notebook for experimentation and interactive development.
- **requirements.txt**: Lists the dependencies required for the project.

## Setup Instructions

1. Clone the repository:
   ```
   git clone <repository-url>
   cd breast-cancer-classification
   ```

2. Install the required packages:
   ```
   pip install -r requirements.txt
   ```

3. Prepare the dataset:
   - Place the BUSI dataset in the `Dataset_BUSI_with_GT/` directory.
   - Run the data splitting script to organize the dataset into training, validation, and test sets.

## Usage

- To train the model, run the `train.py` script:
  ```
  python src/train.py
  ```

- To evaluate the model, run the `evaluate.py` script:
  ```
  python src/evaluate.py
  ```

- For data augmentation, modify the `data_augmentation.py` file as needed.

- For oversampling the malignant class, implement your logic in `oversampling.py`.

## Notes

- Ensure that you have the necessary libraries installed as specified in `requirements.txt`.
- This project is designed for educational purposes and may require further tuning and validation for practical applications.