> ### Energy consumption vs outdoor_temp vs outdoor_humidity vs outdoor_windspeed
![overall_energy_consumption](https://github.com/Abhinavcode13/equipment-energy-regression/blob/main/data/overall_energy_consumption.png)

### Implemented in the Notebook

- **Data Exploration**:
  - Summary statistics, data types, and missing value analysis
  - Visualizations for `random_variable1` and `random_variable2`
  - Correlation heatmaps

- **Data Preprocessing**:
  - Handling missing values
  - Timestamp parsing and feature extraction
  - Zone-based sensor aggregation and feature selection

- **Model Development**:
  - Train-test split (with optional stratification by month)
  - Random Forest Regression with hyperparameter tuning via `GridSearchCV`
  - Model evaluation using `RMSE` and `R²`

- **Key Insights**:
  - Identification of high-impact features
  - Justification of feature selection (including treatment of random variables)
  - Recommendations for energy efficiency

---

### Model Evaluation Metrics

- **R² Score**: Measures explained variance
- **RMSE**: Root Mean Squared Error for precision
- **Cross-Validation**: `5-fold grid search` used for model tuning (which took around ~ 2 hrs)

---

### How to Use

1. Clone the repository:
   
   ```bash
   git clone https://github.com/yourusername/equipment-energy-regression.git
   
   cd smart-factory-energy-prediction
   ```
3. Install dependencies:
   
   ```bash
   pip install -r requirements.txt
   ```
2. Launch the notebook:
   
   ```bash
   jupyter notebook energy_efficiency_analysis.ipynb
   ```

For more insights, refer to the [QA.md](https://github.com/Abhinavcode13/equipment-energy-regression/blob/main/QA.md) file.
