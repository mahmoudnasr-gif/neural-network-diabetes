# Neural Network for Diabetes Prediction

## Problem
Binary classification: predict diabetes from 8 clinical features using the Pima Indians Diabetes Dataset.

## Dataset
- **Source**: Pima Indians Diabetes Database (Kaggle)
- **Samples**: 768 patients
- **Features**: 8 clinical measurements (Glucose, BMI, Age, BloodPressure, Insulin, SkinThickness, Pregnancies, DiabetesPedigreeFunction)
- **Target**: Diabetes — Yes (1) or No (0)

## Approach
- **Preprocessing**: StandardScaler normalization, 80/20 stratified train-test split
- **Model**: Feedforward neural network with ReLU activations and Sigmoid output
- **Training**: Adam optimizer (lr=0.001), binary crossentropy loss, EarlyStopping

## Results
| Model | Accuracy | Precision | Recall | F1-Score | Parameters |
|---|---|---|---|---|---|
| Original (32→16) | 74.03% | 64.00% | 59.26% | 61.54% | 833 |
| V2 (64→Dropout→32→16) | 75.32% | 66.67% | 59.26% | 62.75% | 3,201 |

## Conclusions
The V2 model outperformed the original across accuracy, precision, and F1-Score. By expanding the first hidden layer to 64 neurons, adding Dropout(0.3) regularization, and introducing a third hidden layer, the model reduced false positives from 18 to 16 while maintaining the same recall. The Dropout layer was especially important on this small 768-sample dataset, preventing overfitting and improving generalization. Both models agree on a recall of 59.26%, meaning roughly 4 in 10 actual diabetes cases are still missed — a known limitation of this dataset. The V2 architecture is recommended as a first-pass screening tool to assist clinical decision-making, but should not replace laboratory testing or physician diagnosis.

## Video Walkthrough
[Paste your video link here]
