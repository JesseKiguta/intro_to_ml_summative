# CleanAir Sentinel: Monitoring Air Quality for a Healthier Tomorrow
## Introduction
Air pollution is becoming a major concern in many African cities due to fast urbanization, increased motor traffic, and seasonal dust storms. 
Vulnerable groups including children, the elderly, and people with pre-existing conditions are the most affected by these high pollution levels, which also lead to an increase in respiratory disorders, cardiovascular diseases, and early mortality. 
However, the current public health infrastructure is ill-prepared to anticipate and efficiently respond to pollution spikes, and many African cities lack comprehensive, real-time air quality monitoring systems.

Using easily accessible environmental data, CleanAir Sentinel seeks to create a machine learning model that can categorize air quality into risk levels (Good, Moderate, Poor, and Hazardous) and predict the corresponding threats to health.

Helping local health authorities in African cities predict pollution episodes and provide early warnings to reduce health risks is the primary function of CleanAir Sentinel. 
For instance, the model can assist in informing policies like advising vulnerable populations to stay indoors, optimizing healthcare responses, or managing city-wide traffic restrictions during the dry season, when African cities experience severe dust storms or when emissions from increased traffic or industry rise.

Additionally, CleanAir Sentinel can enable NGOs and local governments to better allocate resources and take preventative measures, which will improve public health outcomes and air quality management throughout the continent.

## The dataset
The dataset used for this project can be found on Kaggle by following [this link](https://www.kaggle.com/datasets/mujtabamatin/air-quality-and-pollution-assessment)
The dataset consists of various air quality parameters collected from monitoring stations, combined with external factors influencing pollution levels. It includes:

Air Pollution Indicators: PM2.5, PM10, NO₂, SO₂, CO.
Weather Conditions: Temperature, Humidity.
Human factors: Population density and industrial zone proximity.
Health Risk Classification: Target variable indicating air quality categories (Good, Moderate, Poor, Hazardous) via one-hot encoding.
The model processes this data using classification algorithms (SVM, Neural Networks) to predict risk levels.

## ML Models

### Classical ML Algorithm: SVM
Grid searching was used to find the optimal hyperparameters for the SVM, these were:

- C = 1
- Gamma = Scale
- Kernel = Linear

Below is the accuracy the model was able to achieve as well as the classification report:

Accuracy: 0.9440
              precision    recall  f1-score   support

        Good       1.00      1.00      1.00       409
    Moderate       0.95      0.96      0.96       294
        Poor       0.84      0.88      0.86       186
   Hazardous       0.91      0.81      0.86       111

    accuracy                           0.94      1000
   macro avg       0.92      0.91      0.92      1000
weighted avg       0.94      0.94      0.94      1000

From these statistics, we can observe that the model is performing well, with an accuracy and f1 score of 0.94.
It is able to predict the "Good" category with perfect accuracy and the lowest score is recall for the "Harazdous" category at 0.81.
The "Hazardous" class was the highest difference between precision and recall showing that the SVM has slight difficulty in predicting that category in comparison to the others.

### Default Neural Network
This is how the default neural network performed from the accuracy, loss and classification report:

Test Accuracy: 0.9540
Test Loss: 0.1276

Classification Report:
              precision    recall  f1-score   support

        Good       1.00      1.00      1.00       409
    Moderate       0.98      0.96      0.97       294
        Poor       0.86      0.90      0.88       186
   Hazardous       0.89      0.86      0.88       111

    accuracy                           0.95      1000
   macro avg       0.93      0.93      0.93      1000
weighted avg       0.95      0.95      0.95      1000

Compared to the SVM, the neural network is performing slightly better with minimal optimization. It's accuracy is higher by 0.1 at 0.95, and
it's better at predicting the "Hazardous" category with an F1 score of 0.88 compared to 0.86 as well as a recall of 0.86 versus 0.81.


## Neural Network Table
This table contains different instances with different combinations of regularizers and optimizers to compare performance with the default neural network.
![Screenshot 2025-02-23 225711](https://github.com/user-attachments/assets/78e2d6af-f5cf-430b-8365-7e588bf06c9b)

Based on the table, the 2nd and 5th instance performed equally well. The worst performing model was the 4th. 
Ultimately the 5th instance was selected to be the best model overall because of its loss graph and would be the recommended model for deployment.

## Accessing the model
All the models can be easily accessed and used by running the cells in the notebook in your preferred environment (Colabs, Jupyter Notebook, VS Code, etc)

## Demo Video Link
