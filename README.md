# Black Friday Sales EDA

Exploratory Data Analysis (EDA) of the Black Friday customer transactions dataset to understand purchase behavior, uncover patterns across demographics and product categories, and inform downstream feature engineering and modeling.

> Notebook: [Black_Friday_Sales_EDA.ipynb](./Black_Friday_Sales_EDA.ipynb)

## Table of Contents
- [Overview](#overview)
- [Dataset](#dataset)
- [Repository Structure](#repository-structure)
- [Quick Start](#quick-start)
- [How to Use the Notebook](#how-to-use-the-notebook)
- [Analyses Included](#analyses-included)
- [Potential Insights](#potential-insights)
- [Next Steps](#next-steps)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## Overview
This project performs comprehensive EDA on the Black Friday dataset (commonly used from Kaggle) to:
- Profile customers by demographics (gender, age band, marital status, city category, tenure).
- Understand purchase distributions and key contributing product categories.
- Identify missing data patterns and data quality issues.
- Generate visual insights to guide feature engineering for predictive models.

The analysis lives in a single, reproducible Jupyter notebook.

## Dataset
- Typical source: Kaggle “Black Friday” dataset  
  Link: https://www.kaggle.com/datasets/mehdidag/black-friday
- Common columns:
  - User_ID, Product_ID
  - Gender (M/F), Age (e.g., 0-17, 18-25, 26-35, 36-45, 46-50, 51-55, 55+)
  - Occupation, City_Category (A/B/C), Stay_In_Current_City_Years
  - Marital_Status (0/1)
  - Product_Category_1, Product_Category_2, Product_Category_3
  - Purchase (target numeric amount)

Note: The raw dataset is not committed to this repository. Please download it from the source above and place it locally as described below.

## Repository Structure
- `Black_Friday_Sales_EDA.ipynb` — Main notebook containing the full EDA workflow.

(Optional, recommended future structure)
- `data/` — Add your CSV here (e.g., `data/BlackFriday.csv`).
- `reports/figures/` — Save plots/exports if you choose to persist figures.

## Quick Start

### 1) Clone the repository
```bash
git clone https://github.com/Idhant-Mehta/BLACK-FRIDAY.git
cd BLACK-FRIDAY
```

### 2) Set up a Python environment
Any recent Python (>=3.9) will work.

Using pip:
```bash
python -m venv .venv
# Linux/Mac
source .venv/bin/activate
# Windows
.venv\Scripts\activate

python -m pip install --upgrade pip
pip install jupyter pandas numpy matplotlib seaborn plotly scikit-learn
```

Using conda (optional):
```bash
conda create -n blackfriday-eda python=3.10 -y
conda activate blackfriday-eda
conda install -y jupyter pandas numpy matplotlib seaborn scikit-learn
pip install plotly
```

### 3) Download the dataset
- Download CSV(s) from Kaggle and place them locally, for example:
  - `data/BlackFriday.csv` (or the exact filename provided by Kaggle)
- Update the notebook’s data loading cell if your path differs.

### 4) Launch the notebook
```bash
jupyter lab
# or
jupyter notebook
```
Open `Black_Friday_Sales_EDA.ipynb` and run cells top to bottom.

## How to Use the Notebook
- Configure the data path at the top of the notebook.
- Run the preprocessing section to handle dtypes and missing values (notably `Product_Category_2` and `Product_Category_3`).
- Execute visualization cells for distributions, segmentations, and correlations.
- Optionally export figures or summary tables.

## Analyses Included
- Data overview: shape, schema, missingness matrix, basic statistics
- Cleaning: dtype normalization, handling missing `Product_Category_2/3`, category ordering for `Age` and `Stay_In_Current_City_Years`
- Univariate analysis: distributions (e.g., `Purchase`)
- Bivariate/segment analysis:
  - Purchase by Gender, Age band, Marital Status, City Category, Stay Years
  - Top Product Categories and Product_IDs by revenue or count
- Correlations and relationships:
  - Numeric correlations heatmap
  - Category-wise aggregations and pivot tables
- Feature engineering ideas:
  - Encodings for ordered categories (Age bands)
  - Aggregations per user/product for downstream modeling

## Potential Insights
These are commonly observed patterns in this dataset and may vary with your exact preprocessing:
- The 26–35 age group often shows higher average spending.
- City Category B can have strong sales volume.
- Male customers may show slightly higher purchase amounts on average.
- Product_Category_1, 5, 8 frequently rank among top contributors.

Use the notebook outputs to validate or refine these observations.

## Next Steps
- Build baseline predictive models (e.g., Linear Regression, Random Forest, XGBoost) on `Purchase`.
- Cross-validation with engineered features (frequency encodings, target encodings, interaction terms).
- Price sensitivity and cohort analysis.
- Deploy dashboards (e.g., Plotly, Streamlit) for interactive exploration.

## Contributing
Contributions are welcome:
- Open issues for bugs, ideas, or enhancements.
- Use clear commit messages and follow notebook cleanliness (restart kernel and run all before committing).

## License
No license specified. If you plan to share or use this work publicly, consider adding an open-source license (e.g., MIT) or clarifying usage terms.

## Acknowledgments
- Dataset courtesy of the Kaggle community.
- Thanks to open-source maintainers of Jupyter, pandas, NumPy, Matplotlib, Seaborn, Plotly, and scikit-learn.
