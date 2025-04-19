# Analysis of Early Alzheimer’s Diagnosis

- Group Members :
    - Shubham Tiwari
    - Rahul Sajith
 
- Course : Artificial Intellignce in Healthcare
- Institution - Michigan Technological University


# Project Overview 

- Abstract :
  Alzheimer’s disease presents significant challenges in early diagnosis.  This project proposes an AI-powered 
holistic system for Early Diagnosis, where AI models analyze brain imaging (MRI, PET scans) and clinical data to detect early signs of Alzheimer's.

- Methodolody :
1. Data Collection & Exploration :
         - Utilized a dataset comprising 271 records and 61 features including brain region measurements and demographic data.
  - Target classes :
    - CN (Cognitively Normal)
    - MCI (Mild Cognitive Impairment)
    - AD (Alzheimer's Disease)
   
2. Data Preprocessing :
   - Dropped non-predictive columns (such as identifiers and redundant features).
   - Managed missing values by removing rows with missing data.
   - Encoded target variable into numerical categories.
   - Train-test split (80-20), stratified to maintain class distribution.
  
3. Modeling Techniques :
   - Random Forest Classifier :
       - Trained on complete feature set.
       - Evaluated with accuracy, confusion matrix, and classification metrics.

    - XGBoost Classifier :
       - Similar training and evaluation setup.

    - Demographic Features Only :
        - Tested performance exclusively using demographic features (Age, MMSE, SES).

    - SMOTE Oversampling :
        - Applied to balance class distribution during training.

4. 1D CNN :
   - CNN Architecture :
       - Convolutional Layer: 64 filters, kernel size 3, ReLU activation.
       - MaxPooling: Reduced feature map dimensionality.
       - Dropout (0.3): Mitigated overfitting.
       - Flattening: Converted 2D data to 1D for Dense layers
       - Dense Layers: One hidden Dense layer with 64 neurons (ReLU), followed by another Dropout 
              layer, and a final Dense output layer with softmax activation.

    - Training :
       - Optimized using the Adam Optimizer
       - Evaluated on the test dataset

- Findings :
1. Random Forest Classifier :
    - Accuracy: Approximately 80%
    - Strong predictive performance for CN class (Precision: 0.88, Recall: 0.97).
    - Moderate performance for AD and MCI, indicating some imbalance or difficulty distinguishing between 
      these conditions.

2. XGBoost Classifier :
    - Improved accuracy of around 86%.
    - Enhanced balanced performance across classes.
    - Notably higher recall for AD (0.83) compared to Random Forest (0.50).

3. Importance of Features :
    - Identified top influential brain regions, critical for distinguishing Alzheimer's from MCI and CN.

4. Demographics-Only Model :
    - Demonstrated limited capability alone, confirming that brain imaging significantly improves diagnostic accuracy.

5. SMOTE Application :
    - Slightly improved model balance and predictive stability on minority classes, suggesting beneficial effects of oversampling techniques for class imbalance.
  
6. 1D CNN :
    - Accuracy : The CNN model provided a robust classification performance on the test dataset, complementing traditional ML methods (Random Forest, XGBoost).
    - Training & Validation Curves : Clearly plotted the accuracy and loss over epochs, allowing for assessment of model convergence and detection of overfitting.
    - Classification Metrics : Generated comprehensive classification reports for each diagnosis class (CN, MCI, AD), allowing detailed performance comparison with the other ML models

 
- Conclusion : The project effectively applied machine learning (Random Forest, XGBoost) and deep learning (1D CNN) models to early Alzheimer's disease diagnosis, distinguishing Alzheimer's Disease (AD), Mild Cognitive Impairment (MCI), and Cognitively Normal (CN) cases using neuroimaging and demographic data. Among the evaluated models, XGBoost demonstrated superior performance with an accuracy of 86%, significantly improving Alzheimer's class identification. The CNN provided robust, complementary insights by capturing intricate feature relationships. Feature importance analysis emphasized the diagnostic value of brain imaging data over demographics alone. Future improvements include utilizing larger, diverse datasets, integrating multi-modal data, and employing advanced neural architectures to further enhance diagnostic accuracy and clinical relevance.
  

