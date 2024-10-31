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

    subgraph Data_Preprocessing [Data Preprocessing]
        B1(Handle Missing Values)
        B2(Standardize/Normalize)
        B3(Encode Categorical Variables)
    end
    B --> B1
    B --> B2
    B --> B3

    subgraph Feature_Engineering_and_Selection [Feature Engineering and Selection]
        C1(Select Relevant Features)
        C2(Target Variable Preparation)
    end
    C --> C1
    C --> C2

    subgraph Model_Training [Model Training]
        D1(Regression for continuous dose prediction)
        D2(Classification for dose categories)
        D3(Cross-validation and Hyperparameter Tuning)
    end
    D --> D1
    D --> D2
    D --> D3

    subgraph Model_Evaluation [Model Evaluation]
        E1(Metrics: MAE, MSE, R-squared for regression)
        E2(Accuracy, Precision, Recall, F1-score for classification)
    end
    E --> E1
    E --> E2

    subgraph Deployment_and_Monitoring [Deployment and Monitoring]
        F1(Model Deployment API/cloud-based)
        F2(Model Monitoring and Retraining)
    end
    F --> F1
    F --> F2
