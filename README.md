```mermaid
flowchart TD
    A[Data Collection] --> B[Data Preprocessing]
    B --> C[Feature Engineering and Selection]
    C --> D[Model Training]
    D --> E[Model Evaluation]
    E --> F[Deployment and Monitoring]

    B --> B1[Handle Missing Values]
    B --> B2[Standardize/Normalize]
    B --> B3[Encode Categorical Variables]

    C --> C1[Select Relevant Features]
    C --> C2[Target Variable Preparation]

    D --> D1[Regression (for continuous dose prediction)]
    D --> D2[Classification (for dose categories)]
    D --> D3[Cross-validation and Hyperparameter Tuning]

    E --> E1[Metrics: MAE, MSE, R-squared (for regression)]
    E --> E2[Accuracy, Precision, Recall, F1-score (for classification)]

    F --> F1[Model Deployment (API/cloud-based)]
    F --> F2[Model Monitoring and Retraining]
