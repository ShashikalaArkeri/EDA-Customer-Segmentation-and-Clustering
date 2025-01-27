# EDA-Customer-Segmentation-and-Clustering

## **Overview**
This project focuses on analyzing customer data to derive actionable insights and segment customers into meaningful groups. The work is divided into three key tasks:

1. **Task 1**: Perform Exploratory Data Analysis (EDA) and derive business insights.  
2. **Task 2**: Build a Lookalike Model to recommend similar customers.  
3. **Task 3**: Perform Customer Segmentation using clustering techniques.  

---

## **Introduction**
Customer segmentation is essential for personalized marketing and business growth. This project leverages clustering techniques and similarity models to analyze eCommerce customer data and derive actionable insights. By dividing customers into distinct segments, businesses can design targeted strategies to improve engagement and revenue.

---

## **Task 1: Exploratory Data Analysis (EDA)**

### **Objective**  
To analyze transactional data and extract meaningful insights that support data-driven decision-making.

### **Steps**  
1. **Data Loading and Exploration**:
   - Loaded data from `Customers.csv`, `Products.csv`, and `Transactions.csv`.
   - Examined dataset structures to identify columns and data types.

2. **Data Cleaning**:
   - Managed missing values and standardized column formats.
   - Verified data types and converted `TransactionDate` to datetime format.

3. **Analysis**:
   - **Revenue by Region**:
     - South America contributed 35% of total revenue, followed by Europe at 30%.
   - **Product Performance**:
     - Books were the top-performing category, contributing 40% of total revenue.
   - **Customer Behavior**:
     - The top 10% of customers generated 60% of total revenue.
     - The average order value (AOV) was $690.
   - **Seasonal Trends**:
     - Sales peaked during November and December.

### **Key Business Insights**  
1. Focus marketing efforts on South America and Europe, which are the highest revenue-generating regions.  
2. Promote Books and Electronics while improving strategies for Clothing and Home Decor categories.  
3. Introduce loyalty programs to reward high-value customers and encourage repeat purchases.  
4. Prepare for increased demand during the holiday season (November and December).  

---

## **Task 2: Lookalike Model**

### **Objective**  
To build a Lookalike Model that recommends similar customers based on their profile and transaction history.

### **Steps**  
1. **Feature Engineering**:
   - Aggregated transaction data to calculate:
     - `TotalSpending`
     - `TransactionCount`
     - `PreferredCategory`
   - Combined these features with customer profile data such as `Region` and `SignupDate`.

2. **Similarity Calculation**:
   - Computed cosine similarity to compare customer profiles.
   - Assigned similarity scores to customer pairs.

3. **Recommendation**:
   - Identified the top 3 similar customers for each user along with similarity scores.
   - Example Output:
     ```json
     {
         "C0001": [("C0152", 1.0), ("C0164", 1.0), ("C0160", 0.99)],
         "C0002": [("C0029", 1.0), ("C0010", 0.98), ("C0060", 0.96)]
     }
     ```

4. **Deliverable**:
   - Created `Lookalike.csv` with the following structure:
     - Customer ID
     - List of top 3 similar customers with their similarity scores.

### **Evaluation**  
- The model successfully identified similar customers based on spending patterns, transaction frequency, and product preferences.

---

## **Task 3: Customer Segmentation**

### **Objective**  
To segment customers into distinct groups using clustering techniques and derive actionable insights for each group.

### **Steps**  
1. **Feature Preparation**:
   - Selected features: `TotalSpending`, `TransactionCount`, `AvgProductPrice`, `Region`, and `PreferredCategory`.
   - Normalized features using `StandardScaler` to standardize data for clustering.

2. **Clustering**:
   - Applied **KMeans Clustering** and tested cluster counts from 2 to 10.
   - Chose `k=8` based on the lowest Davies-Bouldin Index (1.25).

3. **Cluster Analysis**:
   - **Cluster 0**: High spenders with frequent transactions.
   - **Cluster 1**: Moderate spenders of premium products with low frequency.
   - **Cluster 2**: Average spenders with balanced preferences.
   - **Cluster 3**: Frequent buyers with a high preference for a specific category.
   - **Cluster 4**: Moderate spenders with above-average frequency and affordable preferences.
   - **Cluster 5**: Top spenders and frequent buyers of premium products.
   - **Cluster 6**: Low spenders and infrequent buyers of cheaper products.
   - **Cluster 7**: High spenders with frequent purchases of premium products.

4. **Visualization**:
   - Generated bar plots for `TotalSpending`, `TransactionCount`, and `AvgProductPrice` across clusters.
   - Created distribution plots for `PreferredCategory` by cluster.

### **Deliverables**  
- Clustered data with insights documented for each segment.
- Visualizations depicting cluster characteristics and preferences.

---

