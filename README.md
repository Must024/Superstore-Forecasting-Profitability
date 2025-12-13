# Superstore Sales Forecasting & Profitability Analysis
### 1. Project Purpose & Aims
In the highly competitive retail sector, increasing revenue is often prioritized over maintaining healthy profit margins. The Superstore Sales Forecasting & Profitability Analysis project aims to provide a data-driven strategy to optimize both.

The primary business problem addressed here is inconsistent profitability. While the Superstore generates significant sales, certain regions and product sub-categories are eroding margins through heavy discounting or operational inefficiencies.

*** Key Aims:

Diagnose Profitability Issues: Identify exactly where money is being lost (which regions and products).

Forecast Demand: Predict future monthly sales trends to optimize inventory management and reduce stockouts during peak seasons.

Strategic Decision Support: Provide actionable insights to leadership regarding pricing strategies, regional investments, and product portfolio adjustments.

By utilizing this analysis and the accompanying dashboard, business leaders can shift focus from "selling more" to "selling smarter," ensuring long-term sustainable growth.

### 2. Project Workflow
The analysis followed a structured data science pipeline, ensuring consistency from initial processing through to final visualization.

Data Ingestion & Cleaning
Loaded the Sample - Superstore.csv dataset.

Handled missing values (specifically filling Postal Code with 0).

Converted Order Date and Ship Date to datetime objects.

Engineered time-based features (Year, Month, Week) for granular analysis.

Exploratory Data Analysis (EDA)
Analyzed statistical distributions of Sales and Profit.

Aggregated performance metrics by Region, Category, and Sub-Category.

Created heatmaps to examine the intersection of Region and Category profitability.

Time Series Forecasting
Aggregated sales data to a monthly frequency.

Prophet Modeling: Implemented the Prophet time series library to capture seasonality and trend changes.

ARIMA Modeling: Implemented an ARIMA (1,1,1) model for baseline statistical forecasting.

Model Evaluation: Compared models using key metrics like RMSE, MAE, and MAPE.

Dashboard Construction (Tableau)
The original raw dataset (Sample - Superstore.csv) was connected directly to Tableau.

All necessary aggregations, calculations, and visualizations were built within the Tableau workbook.

** 3. Findings & Insights
Based on the quantitative analysis within the notebook, the following critical insights were uncovered:

Sales & Profit Trends
Volatility: Daily sales are highly volatile, ranging from $0.44 to $22,638.

Seasonality: A distinct, recurring spike in sales occurs towards the end of every year (Q4), driven by holiday demand, which the forecasting model successfully captures.

Growth: The overall sales trend from 2014 to 2018 is consistently positive/upward.

Product Performance
Best Category: Technology is the clear leader, generating the highest sales and healthy profits.

Worst Category: Furniture is problematic, causing significant profit erosion.

The detailed breakdown confirms that high-ticket items like Copiers and Phones drive massive profits, while Tables and Bookcases are the primary sources of financial loss.

Profitability Breakdown by Sub-Category:

Regional Performance
Leaders: The West and East regions are the strongest performers.

underperformers: The Central and South regions are underperforming.

The heatmap analysis below reveals the intersection of the problems: Furniture sales in the Central Region are a major source of financial loss.

Key Insight: The Central Region's Furniture category is a major drain on profits.

*** Model Comparison
Prophet significantly outperformed ARIMA, showing a higher predictive accuracy for this seasonal dataset.

Prophet MAPE: ~19.07%

ARIMA MAPE: ~54.11%

### 4. Forecasting Results
The forecasting component utilized the Prophet model to predict sales for the next 12 months (2018–2019 horizon).

Pattern: The forecast predicts a continued upward trajectory in sales volume.

Seasonality: The model anticipates the standard Q4 peaks will reoccur, suggesting higher demand in November and December.

Strategic Value: This forecast enables the supply chain team to proactively ramp up inventory 2–3 months before the predicted spikes, preventing revenue loss due to stockouts during the critical holiday season.

*** Sales Forecast (Next 12 Months):

### 5. Recommendations
Based on the data evidence, the following actions are recommended for leadership:

Restructure the Furniture Strategy:

Pricing: Conduct an immediate pricing and logistics review for Tables and Bookcases. Stop aggressive discounting on these high-loss items.

Operational Improvement: If high shipping costs are the cause in the Central region, explore local warehousing or 'pickup-only' models for bulky, low-margin products.

Double Down on Technology:

Increase marketing spend on high-margin winners like Copiers and Phones.

Bundle these items with lower-margin Office Supplies to boost the overall profit of the average transaction basket.

Regional Intervention:

Implement stricter discount controls specifically for sales managers in the Central Region on furniture products to prevent further profit erosion.

Operational Planning:

Use the Prophet monthly forecast numbers to set sales targets and labor schedules, ensuring warehouses are fully staffed for the predicted Q4 surge.

### 6. Tools & Technologies Used
Python 3.12

Pandas & NumPy: Data cleaning and manipulation.

Matplotlib & Seaborn: Static visualizations and heatmaps.

Prophet: Advanced time series forecasting (Additive model).

Statsmodels: ARIMA forecasting.

Tableau: Interactive dashboarding and final visualization layer.

Jupyter Notebook: Environment for analysis execution.

GitHub: Version control and project hosting.

### 7. Repository Structure
Plaintext

├── data/
│   └── Sample - Superstore.csv        # Raw dataset used by both Python and Tableau
├── notebooks/
│   └── Superstore_Analysis.ipynb      # Main analysis code and forecasting
├── tableau/
│   └── Superstore_Dashboard.twbx      # Tableau Workbook file
├── images/
│   ├── sub_category_profit.png        # Bar chart detailing product profitability
│   ├── profitability_heatmap.png      # Region x Category profit visualization
│   └── sales_forecast_prophet.png     # Time series forecast plot
├── README.md                          # Project documentation
└── requirements.txt                   # Python dependencies
** 8. Dashboard Description
The Tableau Dashboard serves as the executive summary, providing a concise, visual, and interactive synthesis of the Superstore's performance and profitability issues.

*** Key Components & KPIs:

KPI Banner: Includes immediate metrics for Total Sales and Total Profit.

Time Series Trend: Displays historical Sales and Profit over time, confirming the seasonal spikes necessary for accurate forecasting.

Profitability Breakdown: Shows detailed profit figures by Category and Sub-Category, validating the core product recommendations.

Interactive Filters: The dashboard allows users to filter by Year, Segment, and Ship Mode to drill down into specific operational aspects.

The dashboard's layout prioritizes clear communication, enabling any viewer to understand regional and product health within seconds.

### 9. Instructions for Reproducing the Analysis
To reproduce this analysis on your own machine:

Install Required Software

Download and install Tableau Desktop 2023.1 (or later).

(Optional) If you want to replicate preprocessing and forecasting steps, install Python 3.9+ and required libraries using:

Bash

pip install -r requirements.txt
Download the Dataset

Obtain the Superstore dataset from Kaggle sample superstore data resources or from the data/ folder in this repository.

Save the dataset locally in the data/ directory.

Open the Tableau Workbook

Launch Tableau Desktop.

Open the packaged workbook file: tableau/Superstore_Dashboard.twbx.

Verify Data Connection

Ensure the workbook is connected to the Superstore dataset.

If prompted, update the file path to point to your local copy of the dataset.

Run the Analysis

Navigate through the worksheets to view preprocessing and forecasting steps.

Open the Dashboard tab to explore profitability and sales visualizations.

Optional: Reproduce Preprocessing in Python

Open notebooks/Superstore_Analysis.ipynb in Jupyter Notebook.

Run the cells to replicate data cleaning and forecasting logic.

Outputs can be compared with Tableau’s dashboard results.

** Expected Output

Interactive Tableau dashboards showing:

Profitability trends

Forecasted sales and profit margins

Regional and category breakdowns

Python notebook outputs (if used) for validation.

Author: [Gafar Mustopha] Data Source: Sample Superstore Dataset
