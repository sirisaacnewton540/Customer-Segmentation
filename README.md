# Customer Segmentation

This project performs customer segmentation using the `Online Retail.csv` dataset. The analysis includes data ingestion, exploratory data analysis (EDA), data preprocessing, customer segmentation using clustering algorithms, and visualization. The project uses Python for data analysis and visualization, and the final results are saved for further visualization in Tableau.

## Dataset (kindly unzip it before use)

The dataset `Online Retail.csv` contains the following columns:
- `InvoiceNo`: Invoice number. Nominal, a 6-digit integral number uniquely assigned to each transaction. If this code starts with 'C', it indicates a cancellation.
- `StockCode`: Product (item) code. Nominal, a 5-digit integral number uniquely assigned to each distinct product.
- `Description`: Product (item) name. Nominal.
- `Quantity`: The quantities of each product (item) per transaction. Numeric.
- `InvoiceDate`: Invoice Date and time. Numeric, the day and time when each transaction was generated.
- `UnitPrice`: Unit price. Numeric, the product price per unit in sterling.
- `CustomerID`: Customer number. Nominal, a 5-digit integral number uniquely assigned to each customer.
- `Country`: Country name. Nominal, the name of the country where each customer resides.

## Project Workflow

1. **Data Ingestion**
   - Load the dataset into a Pandas DataFrame.

2. **Exploratory Data Analysis (EDA)**
   - Display basic statistics.
   - Check for missing values.
   - Visualize distributions of `Quantity` and `UnitPrice`.
   - Visualize the number of transactions per country.

3. **Data Preprocessing**
   - Drop rows with missing `CustomerID`.
   - Remove negative or zero `Quantity` and `UnitPrice`.
   - Create a `TotalPrice` column (`Quantity` * `UnitPrice`).
   - Convert `InvoiceDate` to datetime.

4. **RFM Analysis**
   - Define snapshot date.
   - Calculate RFM (Recency, Frequency, Monetary) metrics.
   - Log transform the `Monetary` value.
   - Remove outliers.

5. **Segmentation**
   - Standardize RFM metrics.
   - Determine the optimal number of clusters using the silhouette score.
   - Apply K-Means clustering.

6. **Visualization**
   - Visualize clusters using scatter plots.
   - Create a pairplot for a comprehensive view.
   - Save the clustered data for Tableau.

## Result

## Data Visualization and Analysis

### Distribution of Quantity and Unit Price
![1](https://github.com/sirisaacnewton540/Customer-Segmentation/assets/58942453/8a82fc74-d5b1-49eb-8355-caaca7611577)
![2](https://github.com/sirisaacnewton540/Customer-Segmentation/assets/58942453/78743f9c-e80b-48a7-ae3b-e0293f544439)

These histograms show the distribution of the `Quantity` and `Unit Price` variables. Both distributions are highly skewed, indicating that most transactions involve a small quantity of items at relatively low prices. There are a few extreme values, which might be errors or outliers.

### Number of Transactions per Country
![3](https://github.com/sirisaacnewton540/Customer-Segmentation/assets/58942453/c596a08f-2852-49aa-ac4b-c7bcf133bc11)

This bar chart displays the number of transactions from each country. The majority of transactions come from the United Kingdom, which is the primary market for this dataset.

### Silhouette Scores for K-Means Clustering
![4](https://github.com/sirisaacnewton540/Customer-Segmentation/assets/58942453/81b65de9-a4ed-47a7-adeb-17a16135719d)

The silhouette score plot helps determine the optimal number of clusters for the K-Means algorithm. The highest silhouette score is achieved with three clusters, suggesting that this is the most appropriate number of clusters for our data.

### Customer Segments by Recency and Monetary Value
![5](https://github.com/sirisaacnewton540/Customer-Segmentation/assets/58942453/5bc2e33b-4c73-4a1e-95ba-c8c50c30d536)

This scatter plot shows the customer segments based on recency and monetary value. The three clusters are visually distinct, indicating that customers can be grouped into different segments based on their purchasing behavior.

### Customer Segments by Recency and Frequency
![6](https://github.com/sirisaacnewton540/Customer-Segmentation/assets/58942453/3074ca50-c702-43fd-ae09-0a84187fe96e)

This scatter plot shows the customer segments based on recency and frequency. The clusters indicate different customer behaviors, with some customers making frequent purchases and others making fewer purchases.

### Customer Segments by Frequency and Monetary Value
![7](https://github.com/sirisaacnewton540/Customer-Segmentation/assets/58942453/204d7703-7827-423a-805a-fa3dc76582b0)

This scatter plot shows the customer segments based on frequency and monetary value. Customers with high frequency and high monetary value are identified as valuable customers.

### Pair Plot of Customer Segments
![8](https://github.com/sirisaacnewton540/Customer-Segmentation/assets/58942453/257544a0-34c6-4497-864e-137c8ecaff05)

The pair plot provides a comprehensive view of the relationships between recency, frequency, and monetary value across the different clusters. It helps in understanding how these variables interact and contribute to the formation of distinct customer segments.

## Conclusion

The customer segmentation analysis reveals three distinct clusters of customers based on their purchasing behavior:

### Cluster 0: High-Value Loyal Customers
- **Recency**: These customers have made purchases very recently.
- **Frequency**: They have a high frequency of purchases.
- **Monetary**: These customers have a high total spending.
- **Characteristics**: Loyal customers who frequently make high-value purchases. They are valuable to the business and should be targeted with loyalty programs and exclusive offers.

### Cluster 1: Recent Low-Spenders
- **Recency**: These customers have also made purchases recently.
- **Frequency**: They have a moderate frequency of purchases.
- **Monetary**: Their total spending is relatively low.
- **Characteristics**: Customers who have made recent purchases but spend less. Potential to be converted into high-value customers through targeted marketing and promotions.

### Cluster 2: Inactive High-Spenders
- **Recency**: These customers have not made recent purchases.
- **Frequency**: They have a low frequency of purchases.
- **Monetary**: Despite low frequency, their total spending is high.
- **Characteristics**: Customers who spend a lot but do not purchase frequently. Strategies could include re-engagement campaigns to bring them back.

These insights can be used to tailor marketing strategies and improve customer engagement by targeting each segment with personalized offers and communication. The visualizations provide a clear understanding of the different customer segments, their behaviors, and how they contribute to the overall business.

By utilizing these clusters, the business can enhance customer satisfaction and increase revenue through targeted marketing and better customer relationship management.

## Requirements

To run the code, you need to install the following Python packages:

```bash
pip install -r requirements.txt
```

## Acknowledgments

- Special thanks to the UCI Machine Learning Repository for providing the dataset.
- Thanks to the developers of Pandas, Matplotlib, Seaborn, and Scikit-learn for their excellent libraries.
