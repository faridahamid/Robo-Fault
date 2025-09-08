# Robo-Fault Detection Report

This report summarizes the data analysis, feature engineering, and machine learning model evaluation performed for fault detection in robotic joints, based on the `check.ipynb` notebook.

## 1. Data Preprocessing and Feature Engineering

The raw sensor data from various robotic joints (J0-J5) was preprocessed to clean and prepare it for analysis. This involved:

*   **Handling Null Values**: Null values in `speed_roll_mean` and `current_roll_mean` columns were filled using the mean of their respective columns for each joint.
*   **Feature Engineering**: Several new features were engineered to capture relevant patterns for fault detection:
    *   `abs_Current`: Absolute value of current.
    *   `abs_Speed`: Absolute value of speed.
    *   `sudden`: Represents sudden changes in current.
    *   `power`: Calculated as the product of current and speed.

## 2. Univariate Analysis

Univariate analysis was performed on various features to assess their individual discriminative power between 'no-fault' and 'fault' conditions. The `univariate_analysis` function calculated statistical metrics such as mean for both conditions, Cohen's d, t-statistic, p-value, and Area Under the Curve (AUC).

**Key Findings from Univariate Analysis (Examples from J0 Stop & Grip):**

| Feature            | Mean No Fault | Mean Fault | Cohen's d | t-stat | p-value | AUC   |
|--------------------|---------------|------------|-----------|--------|---------|-------|
| Current_J0         | ...           | ...        | ...       | ...    | ...     | ...   |
| Temperature_T0     | ...           | ...        | ...       | ...    | ...     | ...   |
| Speed_J0           | ...           | ...        | ...       | ...    | ...     | ...   |
| Tool_current       | ...           | ...        | ...       | ...    | ...     | ...   |
| abs_Current_J0     | ...           | ...        | ...       | ...    | ...     | ...   |
| abs_Speed_J0       | ...           | ...        | ...       | ...    | ...     | ...   |
| sudden0            | ...           | ...        | ...       | ...    | ...     | ...   |
| power_J0           | ...           | ...        | ...       | ...    | ...     | ...   |
| speed0_roll_mean   | ...           | ...        | ...       | ...    | ...     | ...   |
| current0_roll_mean | ...           | ...        | ...        | ...    | ...     | ...   |

*(Note: Specific numerical values for all features and joints are available in the `check.ipynb` notebook.)*

## 3. Model Training and Evaluation (XGBoost)

XGBoost classifiers were trained and evaluated for each robotic joint (J0-J5) under two scenarios: 'stop' (protective) and 'grip'. The `train_evaluate_protective_xgboost` and `train_evaluate_grip_xgboost` functions were used for this purpose. Each model's performance was assessed using Accuracy, Classification Report (Precision, Recall, F1-score), Confusion Matrix, and Feature Importance.

### Joint 0 - Stop Scenario (Protective)

*   **Accuracy**: 0.616
*   **Classification Report**:
    ```
                   precision    recall  f1-score   support

           False       0.62      0.61      0.61        49
            True       0.61      0.62      0.62        49

        accuracy                           0.62        98
       macro avg       0.62      0.62      0.62        98
    weighted avg       0.62      0.62      0.62        98
    ```
*   **Confusion Matrix**:
    ```
    [[30 19]
     [19 30]]
    ```
*   **Feature Importance**:
    | Feature        | Importance |
    |----------------|------------|
    | power_J0       | 0.223032   |
    | abs_Speed_J0   | 0.220254   |
    | abs_Current_J0 | 0.199770   |
    | Speed_J0       | 0.196918   |
    | Current_J0     | 0.160026   |

### Joint 0 - Grip Scenario

*   **Accuracy**: 0.714
*   **Classification Report**:
    ```
                   precision    recall  f1-score   support

           False       0.72      0.69      0.71        49
            True       0.71      0.73      0.72        49

        accuracy                           0.71        98
       macro avg       0.71      0.71      0.71        98
    weighted avg       0.71      0.71      0.71        98
    ```
*   **Confusion Matrix**:
    ```
    [[34 15]
     [13 36]]
    ```
*   **Feature Importance**:
    | Feature        | Importance |
    |----------------|------------|
    | power_J0       | 0.223032   |
    | abs_Speed_J0   | 0.220254   |
    | abs_Current_J0 | 0.199770   |
    | Speed_J0       | 0.196918   |
    | Current_J0     | 0.160026   |

### Joint 1 - Stop Scenario (Protective)

*   **Accuracy**: 0.75
*   **Classification Report**:
    ```
                   precision    recall  f1-score   support

             0.0       0.75      0.75      0.75        56
             1.0       0.75      0.75      0.75        56

        accuracy                           0.75       112
       macro avg       0.75      0.75      0.75       112
    weighted avg       0.75      0.75      0.75       112
    ```
*   **Confusion Matrix**:
    ```
    [[42 14]
     [14 42]]
    ```
*   **Feature Importance**:
    | Feature        | Importance |
    |----------------|------------|
    | Current_J1     | 0.212875   |
    | power_J1       | 0.169976   |
    | abs_Current_J1 | 0.163750   |
    | Temperature_J1 | 0.156176   |
    | abs_Speed_J1   | 0.153158   |
    | Speed_J1       | 0.144065   |

### Joint 1 - Grip Scenario

*   **Accuracy**: 0.765
*   **Classification Report**:
    ```
                   precision    recall  f1-score   support

           False       0.76      0.78      0.77        49
            True       0.77      0.76      0.76        49

        accuracy                           0.77        98
       macro avg       0.77      0.77      0.77        98
    weighted avg       0.77      0.77      0.77        98
    ```
*   **Confusion Matrix**:
    ```
    [[38 11]
     [12 37]]
    ```
*   **Feature Importance**:
    | Feature        | Importance |
    |----------------|------------|
    | Temperature_J1 | 0.201749   |
    | Speed_J1       | 0.172615   |
    | abs_Speed_J1   | 0.167413   |
    | power_J1       | 0.157401   |
    | abs_Current_J1 | 0.152556   |
    | Current_J1     | 0.148266   |

### Joint 2 - Stop Scenario (Protective)

*   **Accuracy**: 0.8125
*   **Classification Report**:
    ```
                   precision    recall  f1-score   support

             0.0       0.79      0.86      0.82        56
             1.0       0.84      0.77      0.80        56

        accuracy                           0.81       112
       macro avg       0.82      0.81      0.81       112
    weighted avg       0.82      0.81      0.81       112
    ```
*   **Confusion Matrix**:
    ```
    [[48  8]
     [13 43]]
    ```
*   **Feature Importance**:
    | Feature        | Importance |
    |----------------|------------|
    | abs_Speed_J2   | 0.221329   |
    | Current_J2     | 0.209235   |
    | abs_Current_J2 | 0.172965   |
    | Speed_J2       | 0.139159   |
    | power_J2       | 0.137680   |
    | Temperature_J2 | 0.119632   |

### Joint 2 - Grip Scenario

*   **Accuracy**: 0.734
*   **Classification Report**:
    ```
                   precision    recall  f1-score   support

           False       0.73      0.76      0.74        49
            True       0.74      0.71      0.73        49

        accuracy                           0.73        98
       macro avg       0.74      0.73      0.73        98
    weighted avg       0.74      0.73      0.73        98
    ```
*   **Confusion Matrix**:
    ```
    [[37 12]
     [14 35]]
    ```
*   **Feature Importance**:
    | Feature        | Importance |
    |----------------|------------|
    | Temperature_J2 | 0.249086   |
    | Current_J2     | 0.178816   |
    | abs_Current_J2 | 0.147506   |
    | power_J2       | 0.143084   |
    | Speed_J2       | 0.141002   |
    | abs_Speed_J2   | 0.140506   |

### Joint 3 - Stop Scenario (Protective)

*   **Accuracy**: 0.857
*   **Classification Report**:
    ```
                   precision    recall  f1-score   support

             0.0       0.83      0.89      0.86        56
             1.0       0.88      0.82      0.85        56

        accuracy                           0.86       112
       macro avg       0.86      0.86      0.86       112
    weighted avg       0.86      0.86      0.86       112
    ```
*   **Confusion Matrix**:
    ```
    [[50  6]
     [10 46]]
    ```
*   **Feature Importance**:
    | Feature        | Importance |
    |----------------|------------|
    | abs_Current_J3 | 0.214839   |
    | abs_Speed_J3   | 0.200994   |
    | Speed_J3       | 0.158455   |
    | Current_J3     | 0.158052   |
    | power_J3       | 0.140505   |
    | Temperature_J3 | 0.127153   |

### Joint 3 - Grip Scenario

*   **Accuracy**: 0.795
*   **Classification Report**:
    ```
                   precision    recall  f1-score   support

           False       0.78      0.82      0.80        49
            True       0.81      0.78      0.79        49

        accuracy                           0.80        98
       macro avg       0.80      0.80      0.80        98
    weighted avg       0.80      0.80      0.80        98
    ```
*   **Confusion Matrix**:
    ```
    [[40  9]
     [11 38]]
    ```
*   **Feature Importance**:
    | Feature        | Importance |
    |----------------|------------|
    | Temperature_J3 | 0.193197   |
    | Speed_J3       | 0.190744   |
    | Current_J3     | 0.160364   |
    | abs_Speed_J3   | 0.158499   |
    | abs_Current_J3 | 0.152730   |
    | power_J3       | 0.144466   |

### Joint 4 - Stop Scenario (Protective)

*   **Accuracy**: 0.705
*   **Classification Report**:
    ```
                   precision    recall  f1-score   support

             0.0       0.69      0.73      0.71        56
             1.0       0.72      0.68      0.70        56

        accuracy                           0.71       112
       macro avg       0.71      0.71      0.71       112
    weighted avg       0.71      0.71      0.71       112
    ```
*   **Confusion Matrix**:
    ```
    [[41 15]
     [18 38]]
    ```
*   **Feature Importance**:
    | Feature        | Importance |
    |----------------|------------|
    | abs_Speed_J4   | 0.278075   |
    | Speed_J4       | 0.171220   |
    | Temperature_J4 | 0.163608   |
    | power_J4       | 0.135347   |
    | Current_J4     | 0.130828   |
    | abs_Current_J4 | 0.120922   |

### Joint 4 - Grip Scenario

*   **Accuracy**: 0.785
*   **Classification Report**:
    ```
                   precision    recall  f1-score   support

           False       0.80      0.76      0.78        49
            True       0.77      0.82      0.79        49

        accuracy                           0.79        98
       macro avg       0.79      0.79      0.79        98
    weighted avg       0.79      0.79      0.79        98
    ```
*   **Confusion Matrix**:
    ```
    [[37 12]
     [ 9 40]]
    ```
*   **Feature Importance**:
    | Feature        | Importance |
    |----------------|------------|
    | Temperature_J4 | 0.195416   |
    | Speed_J4       | 0.192676   |
    | power_J4       | 0.181207   |
    | Current_J4     | 0.148327   |
    | abs_Current_J4 | 0.144289   |
    | abs_Speed_J4   | 0.138084   |

### Joint 5 - Stop Scenario (Protective)

*   **Accuracy**: 0.785
*   **Classification Report**:
    ```
                   precision    recall  f1-score   support

             0.0       0.79      0.79      0.79        56
             1.0       0.79      0.79      0.79        56

        accuracy                           0.79       112
       macro avg       0.79      0.79      0.79       112
    weighted avg       0.79      0.79      0.79       112
    ```
*   **Confusion Matrix**:
    ```
    [[44 12]
     [12 44]]
    ```
*   **Feature Importance**:
    | Feature        | Importance |
    |----------------|------------|
    | power_J5       | 0.239425   |
    | Current_J5     | 0.204771   |
    | abs_Speed_J5   | 0.197139   |
    | Temperature_J5 | 0.130631   |
    | Speed_J5       | 0.116678   |
    | abs_Current_J5 | 0.111355   |

### Joint 5 - Grip Scenario

*   **Accuracy**: 0.765
*   **Classification Report**:
    ```
                   precision    recall  f1-score   support

           False       0.77      0.76      0.76        49
            True       0.76      0.78      0.77        49

        accuracy                           0.77        98
       macro avg       0.77      0.77      0.77        98
    weighted avg       0.77      0.77      0.77        98
    ```
*   **Confusion Matrix**:
    ```
    [[37 12]
     [11 38]]
    ```
*   **Feature Importance**:
    | Feature        | Importance |
    |----------------|------------|
    | Temperature_J5 | 0.234089   |
    | Speed_J5       | 0.230429   |
    | abs_Current_J5 | 0.142513   |
    | power_J5       | 0.132442   |
    | Current_J5     | 0.131398   |
    | abs_Speed_J5   | 0.129128   |

## Conclusion

The analysis and model evaluation provide insights into the effectiveness of engineered features and XGBoost models for fault detection across different robotic joints and operational scenarios. The varying performance and feature importances highlight the need for tailored approaches for each joint and task.