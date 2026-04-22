# Clustering Countries for Strategic Aid Allocation

# Problem Statement
HELP International is an international humanitarian NGO committed to fighting poverty and providing basic amenities in backward countries. They have raised $10 million and need to decide how to strategically allocate this aid. 

The objective of this project is to categorize 167 countries based on socio-economic and health factors to identify those in the most "dire need" of support.

## Target Metric
The primary focus was to identify countries with:
* **High Child Mortality Rates**
* **Low Income per Person**
* **Low GDP per Capita**

## Steps Taken

### 1. Exploratory Data Analysis (EDA)
* **Univariate Analysis:** Identified outliers in GDP and Income using Box Plots.
* **Bivariate Analysis:** Confirmed a strong negative correlation between wealth (Income) and child mortality.
* **Feature Engineering:** Converted percentage-based features (Exports, Imports, Health) into absolute values to ensure better scaling.

### 2. Hypothesis & Data Preparation
* **Hypothesis:** Countries cluster into three distinct tiers: Under-developed, Developing, and Developed.
* **Scaling:** Applied `StandardScaler` to normalize the data, ensuring features like GDP didn't overshadow fertility rates due to magnitude differences.

### 3. Machine Learning Modeling
* **Algorithm:** K-Means Clustering.
* **Optimization:** Used the **Elbow Method** to determine the optimal number of clusters ($k=3$).
* **Verification:** Validated clusters using Silhouette Scores and scatter plot visualizations.

### 4. Insights & Recommendations
* **Conclusion:** Cluster 0 (48 countries) represents the high-priority zone.
* **Priority List:** Haiti, Sierra Leone, Chad, Central African Republic, and Mali are identified as the top 5 countries requiring immediate intervention.

## 📊 Final Scores & Metrics
* **Optimal Clusters:** 3
* **Cluster 0 Average Child Mortality:** ~92.9 (vs. ~5.0 in the wealthy cluster)
* **Cluster 0 Average Income:** ~$3,897 (vs. ~$45,800 in the wealthy cluster)

## 🛠️ Deployment
1. **Model Persistence:** The final K-Means model and Scaler were serialized using `pickle`.
2. **Dashboarding:** An interactive BI dashboard was deployed via **Tableau Public** to allow stakeholders to visualize aid distribution geographically.
3. **Web Access:** [(https://public.tableau.com/views/ClusteringCountriesforStrategic_AidbyKartikSingharia/StrategicAidAllocationDB?:language=en-GB&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)]
