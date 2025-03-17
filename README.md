# Crime Incident Analysis Project

## Project Overview
This project focuses on analyzing crime incidents using machine learning and deep learning techniques. The objective is to predict the type of crime ("Incident Type Primary") based on various contextual factors, including location and time. The dataset consists of historical crime records, which are processed and used to train multiple classification models.

## Dataset
The dataset contains records of crime incidents with categorical and numerical attributes. Key details include:
- **Training Set**: 218,343 records
- **Validation Set**: 46,788 records
- **Test Set**: 46,788 records
- **Features**: 6 (after preprocessing)
- **Target Variable**: "Incident Type Primary"
- **Missing Values**: Address, Latitude, and Longitude were cleaned and imputed.
  Link of the dataset: https://data.buffalony.gov/Public-Safety/Crime-Incidents/d6g9-xbgu/about_data

## Data Preprocessing
### 1. Handling Missing Values
- Dropped rows with missing values in essential columns (Address, Latitude, Longitude).
- Filled missing values in categorical columns using the mode.

### 2. Data Transformation
- Converted Incident Datetime to datetime format.
- Converted Latitude and Longitude to numeric values, handling non-numeric entries.

### 3. Data Cleaning
- Standardized categorical columns by stripping spaces and converting text to lowercase.

### 4. Outlier Removal
- Used the IQR method to remove outliers in numerical features.

### 5. Feature Encoding
- Applied Label Encoding to categorical features such as Day of Week, Incident Type Primary, and Police District.
- Applied One-Hot Encoding to neighborhood and ZIP code.

### 6. Feature Scaling
- Normalized numerical features using MinMaxScaler.

## Data Visualization & Insights
1. **Crime Count by Day of the Week**: Bar chart shows crime counts are uniformly distributed across the week.
2. **Crime Incidents by Hour of the Day**: Histogram indicates crime peaks during early hours.
3. **Top 10 Most Common Crime Types**: Bar chart reveals a few crime types dominate the dataset.
4. **Correlation Matrix**: Heatmap indicates weak correlations between features.
5. **Crime Incidents by Police District**: Certain districts report significantly higher crime counts.

## Machine Learning Models
### 1. Logistic Regression
- Simple, interpretable, and probabilistic model.
- Accuracy: **98.1%**, Log Loss: **0.081**.

### 2. Random Forest Classifier
- Handles non-linearity and reduces overfitting via averaging.
- Accuracy: **98.0%**, Log Loss: **0.19**.

### 3. Support Vector Classifier (SVC)
- Effective for high-dimensional data but computationally intensive.
- Accuracy: **99.0%**, Log Loss: **0.062**.

### 4. Neural Network
- Captures complex relationships, trained using Adam optimizer and categorical cross-entropy loss.
- Accuracy: **99.0%**, Log Loss: **0.061**.

## Model Performance Comparison
| Model                 | Accuracy | Log Loss | Training Time (s) |
|-----------------------|----------|----------|-------------------|
| Logistic Regression  | 0.981    | 0.081    | 224.03            |
| Random Forest       | 0.980    | 0.190    | 25.09             |
| SVC                 | 0.990    | 0.062    | 606.95            |
| Neural Network      | 0.990    | 0.061    | 573.89            |

### Observations:
- All models achieved **high accuracy (>98%)**.
- Neural Network had the **lowest log loss**, indicating confident predictions.
- Logistic Regression had the **shortest training time**, making it efficient for quick predictions.

## Running the Project
### 1. Installation
Ensure you have the required Python packages installed. You can install them using:
```sh
pip install -r requirements.txt
```

### 2. Running the Code
Execute the Jupyter Notebook or Python script:
```sh
jupyter notebook crime_analysis.ipynb
```

### 3. Training the Models
Run the cells in the Jupyter Notebook to:
- Preprocess the data.
- Train different machine learning models.
- Evaluate model performance.

### 4. Evaluating Model Performance
- Model predictions can be compared using accuracy, log loss, and visualization plots.
- Confusion matrices and classification reports help analyze performance.

## Conclusion
- Neural Networks provide the most confident predictions but are computationally expensive.
- Logistic Regression and Random Forest serve as efficient alternatives for real-world deployment.
- The analysis aids in crime prediction, helping law enforcement take proactive measures.

## References
- [GeeksforGeeks - Support Vector Machines](https://www.geeksforgeeks.org/support-vector-machine-algorithm/)
- [GeeksforGeeks - Logistic Regression](https://www.geeksforgeeks.org/understanding-logistic-regression/)

## License
This project is licensed under the MIT License. See the LICENSE file for more details.

