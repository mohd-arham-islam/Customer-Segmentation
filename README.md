# Retail Customer Segmentation

The goal of this ML project is to identify major customer segments for a UK-based non-store online retail company that specializes in selling unique all-occasion gifts. The provided dataset encompasses all the transactions that took place between 1st December 2010 and 9th December 2011. By analyzing this transnational dataset, we aim to gain insights into the customer segments that drive the company's sales and understand their characteristics. This information will enable the company to tailor its marketing and operational strategies to better serve these segments, ultimately leading to improved customer satisfaction and business growth.

## EDA
During the exploratory phase of the project, several insightful visualizations were created to better understand the dataset:

### Top 5 Most Popular Items by Purchase Quantity

The chart reveals insights into the popularity of different items based on their purchase quantities. The standout item is StockCode 23843, with a remarkable 161,990 units sold, indicating high customer demand. Following closely is StockCode 23166, boasting 152,527 units sold, signifying strong popularity.

StockCode 22197 has a respectable 57,369 units sold, showing notable popularity. StockCodes 84077 and 85099B both have quantities of around 56,000 to 49,000 units, indicating significant customer demand, although not as high as the top two items.


![image](https://github.com/mohd-arham-islam/Customer-Segmentation/assets/111959286/e88258be-4d10-4a5b-a9b0-3790c1ec4adb)

### Line Chart of Revenue by InvoiceDate

The chart reveals two significant insights. Firstly, it shows clear seasonal patterns in revenue with regular peaks, suggesting certain periods have higher revenue levels. Understanding these patterns can help businesses adjust strategies for peak and slow periods.

Secondly, the chart highlights varying peak magnitudes, indicating that some periods generate substantially more revenue. Identifying the reasons behind these high-revenue periods, like promotions or special events, can inform decision-making and allow for the replication of successful strategies to boost growth and revenue.


![image](https://github.com/mohd-arham-islam/Customer-Segmentation/assets/111959286/52240ac7-8668-45b0-8727-a95bb6f19a3a)

### Revenue Distribution by Country

The chart reveals key insights about revenue distribution by country. The United Kingdom (UK) stands out as the top contributor, accounting for the majority of revenue at approximately 9 million, making it a crucial revenue driver for the company. EIRE and the Netherlands follow with around 300K and 286K in revenue, respectively, although their contributions are lower compared to the UK.

These insights offer positive business implications. The company can concentrate its efforts on maximizing revenue in the UK, the primary revenue generator. Additionally, it highlights opportunities for expansion in countries like EIRE, Netherlands, Germany, and France, enabling the company to tap into new customer bases and foster growth. By employing geographic-based customer segmentation, the company can offer personalized experiences and tailored offerings to enhance customer satisfaction and loyalty. In summary, these insights provide valuable guidance for strategic decision-making and have the potential to positively impact the company's revenue and overall business performance, with no indications of negative growth in the chart.


![image](https://github.com/mohd-arham-islam/Customer-Segmentation/assets/111959286/895d7e8a-e24b-42df-8841-b0dc8bcca738)

### Monthly variation in Revenue

The chart depicting revenue distribution by month reveals a clear seasonal pattern in the company's revenue. Most of the year sees consistent sales levels, but starting in September, there's a steady increase leading to a peak in December, indicating a significant boost in sales during the holiday season.

February marks the lowest revenue point, around 0.5 million, possibly reflecting a post-holiday spending decrease. Conversely, December has the highest revenue, about 1.75 million, likely due to heightened holiday-related shopping.

These insights offer a positive business impact opportunity. Recognizing the revenue surge during the holidays allows the company to align marketing, promotions, and inventory management strategies to cater to increased demand in December, maximizing revenue potential and achieving favorable business outcomes.


![image](https://github.com/mohd-arham-islam/Customer-Segmentation/assets/111959286/f8da80de-7ca5-447b-95ea-facdc4d6feef)

### Weekly variation in Revenue


The revenue distribution by day of the week reveals notable insights. Tuesday stands out as the most profitable day, generating nearly 2.5 million units in revenue, while Sunday records the lowest revenue, around 1 million units, possibly due to reduced customer activity. Saturdays show no recorded transactions, indicating non-operational status. Revenue across the other weekdays remains relatively uniform.

These insights have the potential to positively impact the business. Identifying Tuesday as the most profitable day allows for optimized marketing, targeted promotions, and resource allocation. Addressing lower Sunday revenue may prompt operational adjustments or customer attraction strategies. However, the absence of revenue on Saturdays could lead to negative growth if untapped market demand exists. The company should evaluate the reasons behind non-operation on Saturdays and consider extending operations to capture potential revenue opportunities.


![image](https://github.com/mohd-arham-islam/Customer-Segmentation/assets/111959286/7133a01b-53d4-4b1c-8920-20fe9d50a785)

## Feature Engineering

I removed columns with null values since they didn't provide essential information for clustering. To identify and remove outliers, I applied the z-score method, a standard statistical measure that assesses how many standard deviations a data point deviates from the mean. I set a threshold (z_threshold = 3) and considered data points with z-scores exceeding this threshold as outliers.

I also created a 'Revenue' column by multiplying the 'Quantity' and 'UnitPrice' columns, eliminating the need for additional feature manipulation. To ensure consistency in feature scales, I employed the StandardScaler method to scale the 'Revenue' column. This choice is grounded in its widespread use for standardizing numerical data, resulting in a mean of zero and unit variance, which facilitates handling features with differing scales and brings them into a comparable range.

## Model Building

I employed two clustering models, namely K Means Clustering and DBSCAN, and assessed their performance using evaluation metrics. Based on the results, I opted for the DBSCAN model as the final prediction model. DBSCAN achieved a superior Silhouette score of 0.78, while K-means yielded a score of 0.68.

The higher Silhouette score of the DBSCAN model signifies its enhanced performance in terms of clustering quality. It excelled in grouping similar data points together and effectively identified dense regions, resulting in more precise and meaningful clusters. These outcomes hold substantial value in various business applications, including customer segmentation, product categorization, and anomaly detection.

## Conclusion

In summary, this project aimed to analyze customer transaction data, revealing the United Kingdom as a significant revenue contributor and identifying potential optimization opportunities, such as Saturday operations. Tuesdays emerged as a revenue peak, highlighting the importance of targeted marketing efforts. The DBSCAN clustering model outperformed K-means with a higher Silhouette score of 0.78, enabling precise customer segmentation, product categorization, and anomaly detection. These insights inform strategic decisions in marketing, inventory management, and operations, ultimately leading to improved customer satisfaction, increased revenue, and enhanced business performance.
