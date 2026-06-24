# RetailIQ E-commerce EDA & Feature Engineering Challenge

**Student Name:** Abhinav Varshney  
**Program:** B.Tech CSE (AIML & IOT)  
**Submitted to:** Prof. Rohit Gupta  
**Week:** 1  

## Phase 1: Data Audit
**Question:** The manager says "audit the data first." Where do you even begin?

To audit a 500,000-row dataset with dirty data, the initial focus is on understanding the shape, types, and completeness of the data. The first steps include:
* Using `df.info()` to check data types and memory usage.
* Running `df.isnull().sum()` to calculate the exact percentage of missing values per column.
* Using `df.describe()` to find impossible numerical values (e.g., negative prices or corrupted entries).
* Checking for duplicate rows using `df.duplicated().sum()`.
* Separating columns into numerical, low-cardinality categorical, high-cardinality categorical, and ordinal lists for targeted preprocessing later.

## Phase 2: Pricing Visualization
**Question:** Someone suspects the pricing data is heavily skewed prove it or disprove it.

E-commerce pricing data is almost always heavily right-skewed (meaning there are many cheap items, and a few very expensive items that stretch the tail to the right). To prove this, we plot a distribution graph (histogram) and a boxplot. A strong right tail on the histogram and numerous outliers above the upper whisker on the boxplot confirm the skew. *(See solution.py for the exact implementation).*

## Phase 3: Pipeline-Breaking Categoricals
**Question:** Which categorical columns will break your ML pipeline if left untouched?

If left untouched, several categorical columns will break a standard Machine Learning pipeline:
* **High-Cardinality Columns (Cities):** Applying standard One-Hot Encoding here will create thousands of new columns, causing memory crashes (the curse of dimensionality).
* **Mixed Data Types:** Columns containing both strings and integers will throw errors during mathematical operations or distance calculations.
* **Missing Values in Categoricals:** Standard Scikit-Learn models (like Logistic Regression) will fail if null strings are not explicitly imputed.
* **Ordinal Tiers (Loyalty):** Treating "Bronze, Silver, Gold" as regular nominal categories loses the mathematical relationship of their rank, degrading model performance.

## Phase 4: Scenario EDA - Return Patterns
**Question:** Why are customers returning products? Find the patterns that matter to the business.

To find actionable business patterns regarding returned products, we analyze the target variable (`Returned`) against other features:
* **Delivery Time:** Grouping by shipping times to see if late deliveries strongly correlate with higher return rates.
* **Product Category:** Calculating the return percentage per category to spot defective or highly subjective product lines (like clothing vs. electronics).
* **Price Bins:** Creating price brackets to see if expensive, premium items are returned more frequently than cheap impulse buys.
* **Loyalty Tiers:** Checking if guest/new customers return more items than established "Gold" members.

## Phase 6: Feature Correlation
**Question:** Are any features too correlated with each other? Which ones actually predict returns?

To determine if features are too correlated (multicollinearity), we generate a correlation matrix heatmap. 
* Features with a correlation coefficient above 0.85 (e.g., "Discount Amount" and "Discount Percentage") are redundant, and one should be dropped to prevent model instability. 
* To see which features actually predict returns, we calculate the Point-Biserial correlation (for numeric features vs. the binary `Returned` target) or use Mutual Information scores to rank the predictive power of every feature.
