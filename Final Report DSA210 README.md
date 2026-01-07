# 📊 Holistic Marketing Attribution Analysis

## 1. Motivation

In today's fragmented media landscape, companies allocate substantial budgets across both traditional advertising channels (TV, Radio, Newspaper) and digital platforms. However, evaluating the isolated impact of each channel often fails to capture the true dynamics of marketing effectiveness.

The primary motivation of this project is to develop a **holistic marketing attribution model** by integrating traditional advertising data with modern digital engagement metrics. The project aims to:

- Quantify the impact of different marketing channels on **Sales**
- Evaluate whether **Digital Engagement** metrics (Clicks, Likes, CTR) translate into actual revenue
- Investigate the **synergistic effects** between traditional mass media (e.g., TV) and digital marketing spend

---

## 2. Data Sources & Collection

This project employs a **hybrid dataset approach**, combining traditional advertising data with digital marketing performance metrics to create a unified, cross-channel view.

### Dataset 1: Traditional Advertising (`advertising.csv`)
- **Source:** Publicly available marketing dataset (e.g., Kaggle)
- **Features:** TV Ad Budget, Radio Ad Budget, Newspaper Ad Budget, Sales
- **Role:** Represents macro-level advertising spend and the target variable (Sales)

### Dataset 2: Digital Marketing (`digital_marketing.csv`)
- **Source:** Synthetic / public dataset simulating digital campaign performance
- **Features:** Clicks, Impressions, Engagement_Score, Conversion_Rate, ROI, Acquisition_Cost
- **Role:** Represents micro-level user interactions and efficiency metrics

### Data Preparation Strategy
Since the datasets were originally independent, they were aligned using a **synthetic ID and index-based merging strategy**. This approach simulates a unified campaign-level dataset where each row represents a distinct campaign unit or time period.

---

## 3. Data Analysis Pipeline

### Phase 1: Data Cleaning & Preprocessing
- Removed missing values and duplicate observations
- Cleaned currency-formatted values (e.g., `$12,345` → `12345.0`)
- Standardized feature formats across datasets

### Feature Engineering
- **CTR (Click-Through Rate):** `Clicks / Impressions`
- **Digital Spend:** Derived from acquisition costs to align with traditional ad budgets
- **Interaction Term:** `TV_x_Digital` to capture synergy between TV advertising and digital spending

---

### Phase 2: Exploratory Data Analysis (EDA) & Statistics
- **Univariate Analysis:** Histograms and boxplots revealed relatively normal distributions for Sales and TV budgets, while Newspaper spending was right-skewed
- **Bivariate Analysis:** Scatter plots showed a strong positive linear relationship between TV Ad Budget and Sales
- **Correlation Analysis:**  
  - TV–Sales correlation: **0.78**
  - Radio–Sales correlation: **0.57**
  - Newspaper showed weak correlation with Sales

---

### Phase 3: Machine Learning Modeling

To predict Sales and evaluate feature importance, three regression models were implemented:

- **Linear Regression:** Baseline model for linear relationships
- **Random Forest Regressor:** Captures non-linear patterns and feature interactions
- **Gradient Boosting Regressor:** High-performance predictive model

#### Validation Strategy
- 80/20 Train–Test Split
- 5-Fold Cross-Validation for robustness

#### Evaluation Metrics
- R² Score
- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)

---

## 4. Findings & Hypothesis Validation

### ✅ Hypothesis 1: Traditional Media (TV) is the primary driver of Sales  
**Result:** Validated  
- TV had the highest correlation with Sales
- Random Forest feature importance ranked TV Ad Budget as the most influential predictor (Importance > 0.60)

---

### ✅ Hypothesis 2: Higher Digital Engagement leads to higher Sales  
**Result:** Validated  
- An independent T-test comparing high vs. low engagement campaigns yielded a **p-value < 0.05**
- High-engagement campaigns generated significantly higher revenue

---

### ✅ Hypothesis 3: There is a synergy between TV and Digital Spend  
**Result:** Validated  
- The interaction feature `TV_x_Digital` improved explanatory power in Linear Regression
- Tree-based models identified the interaction as a relevant predictor, indicating a non-additive combined effect

---

## Model Performance Summary

- **Best Model:** Gradient Boosting Regressor  
- **Performance:**  
  - R² ≈ **0.98** on the test set  
  - Linear Regression baseline: R² ≈ **0.90**

These results indicate that the relationship between marketing spend and sales is complex and non-linear.  
*While the Gradient Boosting model achieved a very high R² score, this may partially reflect the controlled nature of the dataset and the synthetic merging process.*

---

## 5. Limitations & Future Work

### Limitations
- **Synthetic Merging:** Real-world attribution would benefit from joins based on actual Campaign_IDs or timestamps
- **Seasonality:** Seasonal demand fluctuations were not explicitly modeled
- **Attribution Window:** Lagged effects of advertising were not considered

### Future Work
- **Time-Series Forecasting:** Apply ARIMA or Prophet models to capture temporal dynamics
- **ROI Optimization:** Develop an optimizer to recommend optimal budget allocation across channels
- **Sentiment Analysis:** Incorporate textual data (e.g., social media posts, ad copy) to assess sentiment-driven performance

---

## 📌 Conclusion
This project demonstrates that combining traditional advertising metrics with digital engagement data provides deeper insights into marketing effectiveness. The findings highlight the dominant role of TV advertising, the revenue relevance of digital engagement, and the presence of meaningful cross-channel synergy.

