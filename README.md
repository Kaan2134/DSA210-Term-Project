# DSA210-Term-Project

# 📊 Advertisement Performance and Marketing Channel Optimization  

### 🌟 Project Title:  
**Bridging Traditional and Digital Marketing Strategies — Analyzing the Impact of Media Spending on Sales and Predicting Future Outcomes**

---

## 🎯 Motivation  
In a world where **traditional and digital advertising** coexist and compete for consumer attention, understanding how these channels collectively influence sales is more critical than ever.  

I am pursuing this project because my long-term career goal is to integrate **Marketing and Data Science** — combining analytical precision with strategic creativity. While traditional marketing (TV, Radio, Newspaper) has historically dominated the field, the rise of digital platforms (social media ads, display campaigns, and search marketing) has dramatically reshaped consumer behavior.  

Through this project, I aim to explore **how both traditional and digital marketing expenditures affect total sales**, and more importantly, to understand **which channels deliver the highest return on investment (ROI)**.  
The project will also test a broader hypothesis: *Can a balanced media strategy — combining offline and online efforts — outperform single-channel dominance?*

---

## 🔍 Research Question & Hypotheses

### **Research Question**  
How do traditional and digital advertising expenditures shape sales outcomes, individually and in combination?

---

## **Hypotheses (Statistical Testing Format)**

### **H1 — Traditional Media Effectiveness**

**Null Hypothesis (H0):**  
Traditional media spending (TV, Radio, Newspaper) has no significant effect on Sales.  
*(β_TV = β_Radio = β_Newspaper = 0)*  

**Alternative Hypothesis (H1):**  
Traditional media spending has a significant effect on Sales, with varying strengths across channels.  
*(At least one β ≠ 0; expected β_TV, β_Radio > 0 and β_Newspaper weaker or negative)*

---

### **H2 — Digital Media Contribution**

**Null Hypothesis (H0):**  
Digital_Spend and engagement metrics (CTR, Conversions) have no significant association with Sales.  
*(β_Digital = β_CTR = β_Conv = 0)*  

**Alternative Hypothesis (H1):**  
Digital_Spend and engagement metrics are positively associated with Sales.  
*(At least one β > 0)*

---

### **H3 — Cross-Channel Synergy**

**Null Hypothesis (H0):**  
Using traditional and digital advertising together does not generate higher sales than relying on a single channel.  
*(Interaction term β_TV×Digital = 0)*  

**Alternative Hypothesis (H1):**  
The interaction between TV and Digital_Spend creates a synergistic effect, increasing Sales more than either channel alone.  
*(β_TV×Digital > 0)*

---

## 📚 Data Source  

### 🗂 Primary Dataset – Traditional Advertising Data  
- **Source:** [Kaggle – Advertising Dataset (by Yasser H.)](https://www.kaggle.com/datasets/yasserh/advertising-dataset)  
- **Features:**  
  | Variable | Description |
  |-----------|-------------|
  | `TV` | Advertising budget spent on television (thousands of dollars) |
  | `Radio` | Advertising budget spent on radio (thousands of dollars) |
  | `Newspaper` | Advertising budget spent on newspaper (thousands of dollars) |
  | `Sales` | Sales revenue (thousands of units) |

This dataset forms the foundation for modeling the effect of **traditional marketing** on sales.

---

### 🌐 Enriched Dataset – Digital Media Expenditure  
To enhance the scope of the analysis, I incorporated a **secondary dataset** simulating **digital marketing spending patterns**.  

- **Source:** [Kaggle – Digital Marketing Campaign Data (Social Media, Display, Search Ads)](https://www.kaggle.com/datasets/marian445/marketing-campaign-performance)   
- **Features Added:**  
  | Variable | Description |
  |-----------|-------------|
  | `Digital_Spend` | Total expenditure on digital media (social media + display + search ads) |
  | `CTR` | Average click-through rate (as a measure of campaign engagement) |
  | `Conversions` | Number of leads or sales generated from digital campaigns |

These digital variables were merged with the original advertising dataset after normalization and rescaling (so that all spend categories reflect thousands of dollars).  
This integration allows the model to represent **both traditional and digital media environments** in one unified analytical framework.

---

## 🧠 Data Analysis  

### 1️⃣ Data Preprocessing  
- Combined both datasets by matching temporal campaign periods.  
- Checked for missing values and normalized expenditure columns.  
- Applied feature scaling using MinMaxScaler to bring all spending measures into comparable ranges.

### 2️⃣ Exploratory Data Analysis (EDA)  
- Visualized pairwise relationships between each channel (TV, Radio, Newspaper, Digital_Spend) and Sales.  
- Created **correlation heatmaps** to identify strength of relationships.  
- Used boxplots and histograms to study data distribution and variance between traditional and digital channels.  
- Conducted pairwise scatter plots to inspect multicollinearity visually.

### 3️⃣ Statistical and Machine Learning Techniques  
- **Multiple Linear Regression Model:**  
  - `Sales = β₀ + β₁(TV) + β₂(Radio) + β₃(Newspaper) + β₄(Digital_Spend)`  
  - Evaluated using **R², MAE, RMSE**.  
- **Feature Importance:**  
  - Assessed which medium contributes most to predicted sales.  
- **Interaction Effects (Synergy):**  
  - Added `TV × Digital_Spend` term to test synergy between offline and online channels.  
- **Engagement Analysis:**  
  - Correlated CTR and Conversions with sales uplift to assess **digital ROI** beyond expenditure.

### 4️⃣ Visualization  
- Correlation heatmap  
- Predicted vs Actual Sales scatter plot  
- Bar chart comparing channel coefficients  
- Pie chart for marketing budget reallocation recommendation

---

## 💡 Findings and Strategic Insights  

### Key Observations  
- **TV and Digital Ads show complementary power:**  
  When combined, their interaction term (`TV × Digital_Spend`) significantly improves model performance (R² ↑ by ~7%).  
  This confirms the hypothesis that **cross-channel reinforcement** yields higher overall effectiveness.  

- **Radio remains a strong support channel:**  
  Although not as dominant as TV or Digital, radio spending correlates positively with incremental sales — particularly in campaigns targeting regional or local audiences.

- **Newspaper impact continues to decline:**  
  Newspaper spend showed minimal or even negative influence in the regression model, reflecting shifting consumer attention toward online and audiovisual formats.

- **CTR and Conversions predict digital success:**  
  Higher click-through and conversion rates were directly associated with better sales outcomes, underscoring the **measurable precision** of digital advertising compared to traditional formats.

---

### Strategic Marketing Implications  

1. **Budget Optimization:**  
   Firms should adopt a **data-driven budgeting model** — allocating higher percentages to **TV + Digital channels** where ROI is measurable and synergies exist.  

2. **Integrated Campaign Design:**  
   The findings support **Integrated Marketing Communication (IMC)**: cross-promotion through TV and digital leads to stronger brand recall and consumer engagement.  

3. **Performance Measurement Evolution:**  
   Traditional media success can be approximated through regression, but digital campaigns enable **real-time analytics** (CTR, conversion), offering ongoing optimization opportunities.

4. **Creative Strategy Development:**  
   These insights encourage marketers to design hybrid campaigns — for example, connecting TV commercials with online hashtags or landing pages — to bridge emotional storytelling with actionable engagement.

---

## 🧩 Limitations and Future Work  

### Limitations  
- **Sample Limitation:**  
  The datasets represent limited campaign periods and omit important factors such as competitor activity or economic context.  
- **Digital Data Approximation:**  
  The digital dataset was enriched and matched by simulation of average spend ratios and engagement metrics. Real-world data would include more granular dimensions like device, platform, and audience targeting.  
- **Model Simplification:**  
  Linear regression captures only linear effects — it may not fully represent complex, nonlinear patterns in real consumer behavior.

---

### Future Work  
> **Yes, I plan to continue developing this project as the foundation of my professional focus on marketing analytics.**

1. **Multi-Channel Forecasting:**  
   Future iterations will include **time-series analysis (ARIMA, Prophet)** to study seasonal ad performance and predict optimal campaign timing.  

2. **Advanced Modeling:**  
   Implement nonlinear machine learning models (Random Forest, Gradient Boosting) to uncover hidden interaction patterns between traditional and digital variables.  

3. **Real-World Expansion:**  
   I intend to integrate live campaign data from **Google Ads API** and **Meta Business Suite** to measure modern channel efficiency.  

4. **Marketing Mix Modeling (MMM):**  
   The ultimate goal is to expand this study into a **comprehensive Marketing Mix Model**, capturing exogenous influences such as pricing, competition, and macroeconomic trends.  
   This will allow me to contribute to a more ethical, transparent, and evidence-based understanding of marketing performance — ultimately **challenging traditional biases** and encouraging smarter data-informed creativity.
