# Machine Learning Model for a Digital Twin in a Fruit Supply Chain
 ## Overview

This repository contains the implementation of a machine learning model designed to support the development of a Digital Twin (DT) for predictive maintenance and optimization within a fruit supply chain. The model aids in prolonging the shelf-life of fruits, reducing spoilage, and optimizing storage conditions by predicting various factors like delivery status, shipment times, and the state of the produce during transit.

## Table of Contents
<ol>
  <li><a href="#background">Background</a></li>
  <li><a href="#features">Features</a></li>
  <li><a href="#data">Data</a></li>
  <li><a href="#modeling-approach">Modeling Approach</a></li>
  <li><a href="#results">Results</a></li>
  <li><a href="#installation">Installation</a></li>
  <li><a href="#Data Sourcing">Data Sourcing</a></li>
  <li><a href="#acknowledgements">Acknowledgements</a></li>
</ol>

## <a id="background"></a>Background

The fruit supply chain is characterized by its perishable nature, complex logistics, and stringent quality requirements. Mismanagement and inefficiencies in the supply chain can lead to significant fruit wastage, with about 33% of shipments lost during transit. This project leverages the concept of a Digital Twin to create a virtual replica of the supply chain that uses real-time data to predict and optimize the storage and transportation of fruits.

## <a id="features"></a>Features

The machine learning model developed in this project is capable of:
- Predicting the delivery status and estimating shipment arrival times.
- Determining the optimal mode of transportation based on fruit type, distance, and environmental conditions.
- Assessing the loss of moisture, nutritional, and edible content during storage and transit.
- Predicting late delivery risks and the state of fruit upon arrival.

## <a id="data"></a>Data

The project uses multiple datasets, including:
- Data on fruit per capita availability and the distribution between fresh and processed fruits.
- Shipment details, including import/export data, customer orders, and logistical information.

### Data Preprocessing

The datasets underwent extensive cleaning, including handling missing values, outliers, and dimensionality reduction using Principal Component Analysis (PCA). This preprocessing ensured that the data fed into the model was noise-free and relevant.

## <a id="modeling-approach"></a>Modeling Approach

The following machine learning models were implemented:

1. **Decision Tree Regressor** - For predicting shipment time.
2. **Random Forest Classifier** - For predicting delivery status.
3. **Bernoulli Naive Bayes** - For predicting late delivery risks.
4. **Support Vector Machine (SVM)** - For determining the optimal shipping mode.

### Model Training & Evaluation

The models were trained and evaluated using various metrics, including accuracy, precision, recall, confusion matrices, and ROC-AUC curves. The overall accuracy of the models exceeded 82%, with the Shipping Mode model achieving a perfect score of 1.

## <a id="results"></a>Results

The trained models demonstrated high accuracy in predicting outcomes, with significant implications for reducing fruit wastage and optimizing supply chain operations.
The models were evaluated based on their accuracy in correctly classifying tweets in both the training and testing datasets
Accuracy and Classification Report
It is defined as the ratio of number of correct predictions over the total number of predictions
Accuracy = (True Positives+Tr)/(True Positives+True Negatives+Fa)

  
Fig 6: Classification Report for Shipment time
 
Fig 7: Classification Report for Delivery Status
 
Fig 8: Classification Report for Late Delivery Risk
 
Fig 9: Classification Report for Shipping Mode
The overall accuracy of all models is above 0.82, with least accuracy of Late Delivery risk of 0.82 and a maximum of 1 for Shipping Mode. This implies that the trained model is performing well and for majority of data predictions would be correct.
Outlier and Overfitting using Box Plot
Box Plot is used to visualise the data and identify the outliers. Outliers are the points that usually are present outside the typical range of data.
 

   Fig 10: Box Plot for Shipment Time
 
Fig 11: Box Plot for Shipping Mode
These two-box plot shows that there is no outlier in shipment time box plot while there is a outlier for shipping mode meaning there is one measurement error or a variation in data for shipping mode
Heatmap of Confusion Matrix
Confusion Matrix is a performance evaluation tool that displays a table that helps in comparing predicted values and actual values. It is usually displayed using heatmap where in dark color indicate higher values.
 
   Fig 11: Heatmap for Delivery Status
 
Fig 12: Heatmap for Shipping Mode
These two-heatmap of confusion matrix show that majorly all predicted and actual values are the same and models used are effective as well. 
ROC and AUC
ROC(Receiver Operator Characteristics): It helps analysis the model ability to balance true positives and false positives. The closer the ROC curve to top-left corner the better is the model.
AUC(Area Under Curve): It represents area under the ROC curve. The closer the value of AUC is to 1 the better the model is.
 
           Fig 13: ROC & AUC Curve for Delivery Status
 
         Fig 14: ROC & AUC Curve for Late Delivery Risk
These two curves show that AUC is always bigger than 0.5 which is always a great sign and has great ability to distinguish between classes.
Precision Recall Curve with Error Regions
Precision (Positive Predictive Value): It is measure of correct positive predicted values.
Precision = (True Positives)/(True Positives+False Positives)
Precision (True Predictive Rate): It is measure of positive values that are correctly identified.
Recall = (True Positives)/(True Positives+False Negatives)
Error Regions: It is the area around prediction are  the uncertainty or variance in the prediction
 
           Fig 15: Precision-Recall Curve with Error Regions for Late Delivery Risk
 
           Fig 16: Precision-Recall Curve with Error Regions for Shipping Mode
These two curves show that there is no change in precision over a range of recall values and model performance is also great since it is near to top right corner.


## <a id="installation"></a>Installation

To set up the project locally, following steps were taken:

1. Clone the repository:
    ```bash
    git clone https://github.com/your_username/your_repository.git
    ```
2. Navigate to the project directory:
    ```bash
    cd your_repository
    ```
3. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```
## <a id="Data Sourcing"></a>Data Sourcing 

Data was collected from various sources including USDA, Economic Research Service, and the Food Availability Data System. The datasets included information on fruit per capita availability, distribution between fresh and processed fruits, import/export data, customer orders, shipment details, and more with more than 400,000 data fields. Missing values were filled with median values to maintain the integrity of the dataset. Outliers were identified and handled to reduce noise.

## <a id="acknowledgements"></a>Acknowledgements
This project was developed as part of a research paper titled "Machine Learning Model for a Digital Twin for Predictive Maintenance and Optimization in a Fruit Supply Chain" by Vania Goel, Anusha Arora with contributions and support from Dr. Neetu Goel, and Dr. Pooja Thakar.
