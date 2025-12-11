# Superstore-Forecasting-Profitability
Superstore Sales Forecasting & Profitability Analysis
🎯 1. Project Purpose & Aims
In the highly competitive retail sector, increasing revenue is often prioritized over maintaining healthy profit margins. The Superstore Sales Forecasting & Profitability Analysis project aims to provide a data-driven strategy to optimize both.

The primary business problem addressed here is inconsistent profitability. While the Superstore generates significant sales, certain regions and product sub-categories are eroding margins through heavy discounting or operational inefficiencies.

Key Aims:

Diagnose Profitability Issues: Identify exactly where money is being lost (which regions and products).

Forecast Demand: Predict future monthly sales trends to optimize inventory management and reduce stockouts during peak seasons.

Strategic Decision Support: Provide actionable insights to leadership regarding pricing strategies, regional investments, and product portfolio adjustments.

By utilizing this analysis and the accompanying dashboard, business leaders can shift focus from "selling more" to "selling smarter," ensuring long-term sustainable growth.

📘 2. Project Workflow
The analysis followed a structured data science pipeline, ensuring consistency from initial processing through to final visualization.

Data Ingestion & Cleaning:

Loaded the Sample - Superstore.csv dataset.

Handled missing values (specifically filling Postal Code with 0).

Converted Order Date and Ship Date to datetime objects.

Engineered time-based features (Year, Month, Week) for granular analysis.

Exploratory Data Analysis (EDA):

Analyzed statistical distributions of Sales and Profit.

Visualized daily sales trends to detect volatility.

Aggregated performance metrics by Region, Category, and Sub-Category.

Created heatmaps to examine the intersection of Region and Category profitability.

Time Series Forecasting:

Aggregated sales data to a monthly frequency.

Prophet Modeling: Implemented Facebook Prophet to capture seasonality and trend changes.

Model Evaluation: Compared models using RMSE (Root Mean Squared Error), MAE (Mean Absolute Error), and MAPE (Mean Absolute Percentage Error).

Dashboard Construction (Tableau):

The original raw dataset (Sample - Superstore.csv) was connected directly to Tableau.

Aggregations, calculations (like Profit Ratio), and visualizations were built entirely within the Tableau workbook, referencing the same source data as the Python notebook.

📊 3. Findings & Insights
Based on the quantitative analysis within the notebook, the following critical insights were uncovered:

Sales & Profit Trends
Volatility: Daily sales are highly volatile, ranging from $0.44 to $22,638, indicating a mix of high-volume low-value items and occasional high-ticket bulk orders.

Seasonality: There is a distinct recurring spike in sales towards the end of every year (Q4), driven by holiday demand.

Growth: The overall sales trend from 2014 to 2018 is positive/upward.

Product Performance
Best Category: Technology is the clear leader, generating the highest sales and healthy profits.

Worst Category: Furniture is problematic. While it generates revenue, it suffers from significant profit losses in specific sub-categories.

Sub-Category Winners: Copiers and Phones are the most profitable items.

Sub-Category Losers: Tables and Bookcases are consistently unprofitable, likely due to high shipping costs or excessive discounting.

Regional Performance
Leaders: The West and East regions are the strongest performers, contributing the bulk of the company's profit.

Laggards: The Central and South regions are underperforming. Specifically, the heatmap analysis below reveals that Furniture in the Central Region is a major source of financial loss.

Key Insight: The Central Region's Furniture category is a major drain on profits.

Model Comparison
Prophet significantly outperformed ARIMA.

Prophet MAPE: ~19.07%

ARIMA MAPE: ~54.11%

Prophet successfully captured the seasonal "heartbeat" of the sales data, whereas ARIMA struggled with the sharp seasonal variations.

📈 4. Forecasting Results
The forecasting component utilized Facebook Prophet to predict sales for the next 12 months (2018–2019 horizon).

Pattern: The forecast predicts a continued upward trajectory in sales volume.

Seasonality: The model anticipates the standard Q4 peaks will reoccur, suggesting higher demand in November and December.

Uncertainty: The confidence intervals widen slightly over time, but the trend remains positive.

Strategic Value: By trusting this forecast, the supply chain team can proactively ramp up inventory 2–3 months before the predicted spikes, preventing revenue loss due to stockouts during the critical holiday season.

Sales Forecast (Next 12 Months):

💡 5. Recommendations
Based on the data evidence, the following actions are recommended:

Restructure the Furniture Strategy:

Tables & Bookcases: Conduct a pricing review. Stop aggressive discounting on these items immediately. If shipping costs are the culprit, explore local warehousing or pickup-only options for the Central region.

Consider discontinuing specific high-loss SKUs within the Tables category.

Double Down on Technology:

Increase marketing spend on Copiers and Phones. Bundle these high-margin items with lower-margin Office Supplies to boost overall basket profitability.

Regional Intervention:

Investigate the Central Region. The combination of Furniture sales in this area is toxic to the bottom line. Implement stricter discount controls specifically for Central region sales managers.

Operational Planning via Forecasts:

Use the Prophet monthly forecast numbers to set sales targets and labor schedules. Ensure warehouses are fully staffed for the predicted Q4 surge.

🛠️ 6. Tools & Technologies Used
Python 3.12

Pandas & NumPy: Data manipulation and aggregation.

Matplotlib & Seaborn: Static visualizations and heatmaps.

Prophet: Time series forecasting (Additive model).

Statsmodels: ARIMA forecasting.

Scikit-Learn: Calculation of evaluation metrics (MAE, MSE).

Tableau: Interactive dashboarding and final visualization layer.

📂 7. Repository Structure
Plaintext

├── data/
│   └── Sample - Superstore.csv        # Raw dataset used by both Python and Tableau
├── notebooks/
│   └── Superstore_Analysis.ipynb      # Main analysis code and forecasting
├── tableau/
│   └── Superstore_Dashboard.twbx      # Tableau Workbook file (using the raw data)
├── images/
│   ├── forecast_plot.png              # Prophet forecast chart (from Python)
│   └── profitability_heatmap.png      # Region/Category heatmap (from Python)
├── README.md                          # Project documentation
└── requirements.txt                   # Python dependencies
🎨 8. Dashboard Description
The Tableau Dashboard serves as the executive summary, providing a concise, visual, and interactive summary of the Superstore's performance.

Key Components & KPIs:

KPI Banner: Includes immediate metrics for Total Sales, Total Profit, and Overall Profit Ratio.

Geographic View (Map): Visualizes Profit across the four main regions, immediately highlighting the disparity between the West/East and the struggling Central/South regions.

Trend Line: Displays historical Sales and Profit over time, confirming the seasonal Q4 spikes.

Profitability Breakdown (Bar Charts): Shows detailed profit figures by Category and Sub-Category, validating the recommendation to promote Technology and address Furniture/Office Supplies losses.

Interactive Filters: The dashboard allows users to filter by Year, Segment, and Ship Mode to drill down into specific operational aspects.

The layout is designed for maximum clarity, allowing a viewer to understand regional and product health within seconds.

📥 9. Instructions for Reproducing the Analysis
Clone the Repository:

Bash

git clone https://github.com/yourusername/superstore-forecasting.git
cd superstore-forecasting
Install Dependencies: Ensure you have Python installed, then run:

Bash

pip install pandas numpy matplotlib seaborn prophet statsmodels scikit-learn
Run the Notebook: Launch Jupyter and open the main file:

Bash

jupyter notebook notebooks/Superstore_Analysis.ipynb
View Dashboard:

Open the tableau/Superstore_Dashboard.twbx file using Tableau Desktop or Tableau Public to view the interactive visualizations.

Author: [Your Name] Data Source: Sample Superstore Dataset
