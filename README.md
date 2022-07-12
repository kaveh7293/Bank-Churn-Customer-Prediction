# Bank-Churn-Customer-Prediction
<h3> Project Description</h3><br>
<p> In this project the goal is to identify the customers that are going to churn. We get the data set from <a href=https://www.kaggle.com/datasets/sakshigoyal7/credit-card-customers>Kaggle</a>, which contains customer features and whether they have churned the bank or they are still active members. In this data set, we can detect the future customers that are going to churn the bank, using a classification algorithm. By doing so, banks can identify the customers that are capable of leaving, and do prohibitive actions. </p>
<h3>Road Map for Solving the Problem</h3>
<p> We use the following steps to identify customers who are going to leave the bank:<br>
  <ol>
    <li> Use data processing tools to identify missing values, and convert the string columns into numerical values (using onehotencoding). I also use a transformation for other data types used (i.e., used minmax transformation for integer data types and standard scaler for float data types)</li>
    <li>Use a clustering algorithm to segment customers. We do that by using a simple k-means clustering algorithm. Afterwards, one can obtain the fraction of each cluster who left the banking services. The cluster with a higher fraction of customers who left the bank is identified, and their features are determined using explanatory data analysis and PCA. </li>
    <li>Use a classification algorithm to fit a classification algorithm. By doing so, the bank compnay can identify their customers who are going to leave the company. I did this algorithm by using a random forest algorithm.</li>
    
  </ol>
<h3> Data preprocessing </h3>
<p> The initial data set for this data analysis problem is shown as follows:<br>
  <img src='https://github.com/kaveh7293/Bank-Churn-Customer-Prediction/blob/main/Screenshot%202022-07-11%20140037.png' width="850" height="200"><br>
  <img src='https://github.com/kaveh7293/Bank-Churn-Customer-Prediction/blob/main/Screenshot%202022-07-11%20140723.png' width="850" height="200"><br>
  As can be seen, three different data types are available (i.e., float, integer and string (categorical)). I used a column transformation to convert these columns into their corresponding numerical values. Note that, the data shown in the above tables are not all the columns in the data. For the sake of brevity, we did not show all the columns. 
  
</p>
<h3> Clustering algorithm</h3>
<p> A k-means clustering algorithm has been usded to do a customer segmentation. We used the elbow method to determine the appropriate number of clusters that should be used for our analysis. The following figure shows the change in wcss vs. the number of clusters. Based on the following figure, I used 7 cluster segments.<br>
<img src='https://github.com/kaveh7293/Bank-Churn-Customer-Prediction/blob/main/download2.png' width="400" height="300"><br>
The results of the customer segmentation showed that 37% of the customers in the fifth cluster left the bank (about 100% more than the average value of 16%). The seventh cluster had the smallest fraction of customers that left the bank. To evluate the important features that are noticeably influence the clusters, I used a PCA dimension reduction to  facilitate the visualization.
  
  The corresponding visualization for the corresponding clusters are shown in the following figures based on the first three principal components of the data. Note that the first two principal components can describe aboute 41% of the variation in the data and the the first three can describe 53% of the data, so the following figures are only arround a half of total variability in the data. As can be seen, however, the variability of the clusters can be seen in the following figures even with 53% of total variability:<br>
<img src='https://github.com/kaveh7293/Bank-Churn-Customer-Prediction/blob/main/t1_t2.png' width="500" height="300"><br>
<img src='https://github.com/kaveh7293/Bank-Churn-Customer-Prediction/blob/main/t3_t1.png' width="500" height="300"><br>
<img src='https://github.com/kaveh7293/Bank-Churn-Customer-Prediction/blob/main/t3_t2.png' width="500" height="300"><br>

  Note that the yellow dots are the corresponding customer cluster with a maximum fraction of people who are prone to leave, and the cluster in purple is the one with the smallest fraction of people who are prone to leave the bank. As shown in the figures above these the yellow cluster is located on the negative part of t1 and t2 axes and is at the center of t3 axis. However, the purple clusters are located on the positive part of the t2 and t3 axes and on the central part of the t1 axis. As a result, using the loading plots for different features can provide informative results regarding the important features that distinguish cluster members in yellow and purple clusters. Both green and yellow clusters are in the negative part of t1 axis, so information regarding the loading values along the first principal component only provide results about their common features. As shown in the following table<br>
  One important value that can be determined based on the t score values are the loading value. The highest loading value corresponding to the first principal component is the age column and 
  <img src='https://github.com/kaveh7293/Bank-Churn-Customer-Prediction/blob/main/PC1.png'width="400" height="300"><br>
  <img src='https://github.com/kaveh7293/Bank-Churn-Customer-Prediction/blob/main/PC2.png'width="400" height="300"><br>
  <img src='https://github.com/kaveh7293/Bank-Churn-Customer-Prediction/blob/main/PC3.png'width="400" height="300"><br>
  In the next step, I determined the fraction of each cluster that left the bank. By doing so we can identify the common characteristics that the customers share in the cluster with a higher fraction of. The analysis showed that people in the third cluster are more prone to leave the bank. As a result, we determine their common characteristics.
</p>
