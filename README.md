

```
# Crime Type and Occurrence Prediction

## Overview

Crime Type and Occurrence Prediction is a machine learning project designed to analyze historical crime incident data and predict both the type of crime and its potential occurrence. By leveraging a Naive Bayes classifier along with rigorous data preprocessing and validation techniques, the project aims to provide actionable insights that can help in crime prevention and policy formulation. This tool was developed to process over 8,000 incident reports, refine classifications, and improve predictive accuracy over previous methods.

## Features

- **Large-Scale Data Analysis:** Processes a dataset of over 8,000 crime incident reports.
- **Naive Bayes Classification:** Implements a Naive Bayes model to classify crime types accurately.
- **Rigorous Testing and Validation:** Conducts thorough testing to validate the model’s predictive performance.
- **Iterative Improvement:** Continuously refines the model to achieve up to a 20% increase in prediction accuracy.
- **Actionable Insights:** Provides refined classifications that can directly influence policy adjustments for crime prevention.

## Technologies Used

- **Programming Language:** Python
- **Data Handling:** Pandas, NumPy
- **Machine Learning:** Scikit-learn (Naive Bayes classifier)
- **Data Visualization (optional):** Matplotlib
- **Excel Data Processing:** Pandas' `read_excel` for handling the dataset in Excel format

## Dataset

The project uses an Excel dataset containing historical crime incident data:

- **File:** `Crime_DataSets.xlsx`
- **Details:** The dataset includes attributes such as crime type, date, time, location, and other relevant details required for effective analysis and prediction.

### How to Use the Dataset

1. **Placement:**  
   Place the `Crime_DataSets.xlsx` file in the `data/` directory of the repository.
2. **Reading the Data:**  
   The data can be read directly using Pandas:
   ```python
   import pandas as pd
   data = pd.read_excel("data/Crime_DataSets.xlsx")
   ```
3. **Optional Conversion:**  
   You can convert the Excel data to CSV for further processing if needed:
   ```python
   data.to_csv("data/raw_incidents.csv", index=False)
   ```

## Methodology

1. **Data Preprocessing:**  
   - Clean and normalize the data.
   - Handle missing values and outliers.
   - Convert categorical variables into a numerical format suitable for model training.

2. **Feature Engineering:**  
   - Extract relevant features such as time, location, and historical patterns.
   - Create new features that could help improve model performance.

3. **Model Training:**  
   - Train a Naive Bayes classifier on the preprocessed data.
   - Use cross-validation techniques to evaluate the model.

4. **Model Evaluation:**  
   - Assess the model using appropriate metrics (e.g., accuracy, precision, recall).
   - Refine the model iteratively to improve its predictive capabilities.

5. **Prediction:**  
   - Use the trained model to predict crime types and occurrences on new data.
   - Output predictions to a CSV file for further analysis.

## Installation

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/gauravch-code/Crime-Type-and-Occurrence-Prediction.git
   cd Crime-Type-and-Occurrence-Prediction
   ```

2. **Set Up a Virtual Environment:**
   ```bash
   python -m venv venv
   ```
   - **On Windows:**
     ```bash
     venv\Scripts\activate
     ```
   - **On macOS/Linux:**
     ```bash
     source venv/bin/activate
     ```

3. **Install Dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

## Usage

1. **Data Preprocessing:**  
   Run the preprocessing script to clean and prepare the dataset:
   ```bash
   python scripts/preprocess.py --input data/Crime_DataSets.xlsx --output data/processed_incidents.csv
   ```

2. **Model Training:**  
   Train the Naive Bayes classifier using the processed data:
   ```bash
   python scripts/train.py --data data/processed_incidents.csv --model output/model.pkl
   ```

3. **Prediction:**  
   Use the trained model to predict crime types for new incident data:
   ```bash
   python scripts/predict.py --model output/model.pkl --input data/new_incidents.csv --output output/predictions.csv
   ```

## Project Structure

```
Crime-Type-and-Occurrence-Prediction/
│
├── data/
│   ├── Crime_DataSets.xlsx       # Excel dataset with historical crime reports
│   ├── raw_incidents.csv         # (Optional) CSV version of the raw data
│   ├── processed_incidents.csv   # Data after preprocessing
│   └── new_incidents.csv         # New data for predictions
│
├── scripts/
│   ├── preprocess.py             # Script for data cleaning and preprocessing
│   ├── train.py                  # Script for model training
│   └── predict.py                # Script for making predictions
│
├── output/
│   ├── model.pkl                 # Serialized trained model
│   └── predictions.csv           # Output predictions from the model
│
├── requirements.txt              # Python package dependencies
├── README.md                     # Project documentation (this file)
└── LICENSE                       # License information
```

## Contributing

Contributions are welcome! If you have suggestions, improvements, or bug fixes, please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Commit your changes and push the branch.
4. Open a pull request explaining your changes.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Contact

Developed by **Gaurav Chintakunta**  
Email: [gchin6@uic.edu](mailto:gchin6@uic.edu)  
GitHub: [gauravch-code](https://github.com/gauravch-code)
```
