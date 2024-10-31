# Machine Learning Pipeline Flow Chart

```mermaid
flowchart TD
    A[Data Collection]
    B[Data Preprocessing]
    C[Feature Engineering and Selection]
    D[Model Training]
    E[Model Evaluation]
    F[Deployment and Monitoring]

    A --> B
    B --> C
    C --> D
    D --> E
    E --> F

    B --> |Handle Missing Values|
    B --> |Standardize/Normalize|
    B --> |Encode Categorical Variables|

    C --> |Select Relevant Features|
    C --> |Target Variable Preparation|

    D --> |Regression (for continuous dose prediction)|
    D --> |Classification (for dose categories)|
    D --> |Cross-validation and Hyperparameter Tuning|

    E --> |Metrics: MAE, MSE, R-squared (for regression)|
    E --> |Accuracy, Precision, Recall, F1-score (for classification)|

    F --> |Model Deployment (API/cloud-based)|
    F --> |Model Monitoring and Retraining|
