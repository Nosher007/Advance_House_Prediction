# House Price Prediction Model

## Project Overview
This project implements a machine learning solution for predicting house prices using various regression models. The implementation includes data preprocessing, feature engineering, model training, and evaluation.

## Models Implemented
* Lasso Regression
* Ridge Regression
* Random Forest
* XGBoost
* LightGBM

## Project Structure
```
├── main.ipynb          # Main notebook containing all the analysis and modeling
├── train.csv           # Training dataset
├── test.csv            # Test dataset
└── submission.csv      # Final predictions
```

## Data Processing Steps

### 1. Data Loading and Initial Exploration
* Load training and test datasets
* Initial data analysis and visualization
* Missing value identification

### 2. Missing Value Treatment
* Categorical variables filled with "None"
* Numerical variables filled with 0 or mean values

### 3. Feature Engineering
* Created new features: TotalSF, HouseAge, RemodAge
* Log transformation of skewed features
* One-hot encoding of categorical variables

## Model Performance
| Model | RMSE |
|-------|------|
| Lasso | 0.2450 |
| Random Forest | 0.1488 |
| XGBoost | 0.1406 |
| LightGBM | 0.1391 |

## Feature Engineering Details
* **TotalSF**: Combined basement, first floor, and second floor square footage
* **Age Features**: Created from YearBuilt and YearRemodAdd
* **Log Transformation**: Applied to handle skewed numerical features
* **Categorical Encoding**: One-hot encoding for categorical variables

## Prerequisites
```python
numpy
pandas
seaborn
matplotlib
scikit-learn
xgboost
lightgbm
```

## Model Training
The final model (LightGBM) parameters:
```python
params = {
    'n_estimators': 1000,
    'learning_rate': 0.05,
    'max_depth': 5,
    'random_state': 42
}
```

## Usage

1. Clone the repository
```bash
git clone [repository-url]
```

2. Install required dependencies
```bash
pip install -r requirements.txt
```

3. Run the Jupyter notebook
```bash
jupyter notebook main.ipynb
```

4. The final predictions will be saved in 'submission.csv'

## Data Preprocessing Details
* Missing values handled based on domain knowledge
* Feature scaling and transformation applied
* Categorical variables encoded
* Train-test split maintained throughout the process

## Future Improvements

1. **Feature Selection**
   * Implement more sophisticated selection techniques
   * Analyze feature importance

2. **Model Optimization**
   * Grid search for hyperparameter tuning
   * Implement model stacking

3. **Feature Engineering**
   * Create more interaction features
   * Domain-specific feature creation

4. **Model Evaluation**
   * Implement more evaluation metrics
   * Cross-validation strategies

## Notes
* Target variable (SalePrice) was log-transformed
* Cross-validation used for robust evaluation
* Feature importance analysis available for interpretability

## Contributing
1. Fork the repository
2. Create your feature branch (`git checkout -b feature/improvement`)
3. Commit your changes (`git commit -am 'Add some improvement'`)
4. Push to the branch (`git push origin feature/improvement`)
5. Create a new Pull Request

## License
This project is open-source and available under the MIT License.