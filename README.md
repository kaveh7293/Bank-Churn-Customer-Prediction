# Bank-Customer-Segmentation
<h3> Project Description</h3><br>
<p> In this project the goal is to identify the customers that are going to churn. We get the data set from <a href=https://www.kaggle.com/datasets/sakshigoyal7/credit-card-customers>Kaggle</a>, which contains customer features and whether they have churned the bank or they are still active members. In this data set, we can detect the future customers that are going to churn the bank, using a classification algorithm. By doing so, banks can identify the customers that are capable of leaving, and do prohibitive actions. Prior to doing classification, I was interested to do a customer segmentation to categorize them into different segments wherein different cutomers have different behaviours. </p>
<h3>Road Map for Solving the Problem</h3>
<p> We use the following steps to identify customers who are going to leave the bank:<br>
  <ol>
    <li> Use data processing tools to identify missing values, and convert the string columns into numerical values (using onehotencoding). I also use a transformation for other data types used (i.e., used minmax transformation for integer data types and standard scaler for float data types)</li>
    <li> Use PCA for dimension reduction. By doing so, important features can be determined using biplot and different segments characteristics can be identified.</li>
    <li>Use a clustering algorithm to segment customers. We do that by using a simple k-means clustering algorithm.  </li>
        
  </ol>
<h3> Data Preprocessing </h3>
<p> The initial data set for this data analysis problem is shown as follows:<br>
  <img src='https://github.com/kaveh7293/Bank-Churn-Customer-Prediction/blob/main/Screenshot%202022-07-11%20140037.png' width="850" height="200"><br>
  <img src='https://github.com/kaveh7293/Bank-Churn-Customer-Prediction/blob/main/Screenshot%202022-07-11%20140723.png' width="850" height="200"><br>
  As can be seen, three different data types are available (i.e., float, integer and string (categorical)). I used a column transformation to convert these columns into their corresponding numerical values. Note that, the data shown in the above tables are not all the columns in the data. For the sake of brevity, we did not show all the columns. 
  
</p>
<h3> Dimension Reduction </h3>
<p> I obtained the following plot to determine the appropriate numbers of principal components which could explain aroung 80 % of the variability in the data. As shown, the first seven principal components explain 79 % of the variability in the data. As a result, I use seven pricipal components for dimensin reduction. <br>
  <img src='https://github.com/kaveh7293/Bank-Churn-Customer-Prediction/blob/main/Explained_Variance.png' width='600' height='450'>
 </p> 
<h3> Clustering Algorithm</h3>
<p> A k-means clustering algorithm has been usded to do a customer segmentation. We used the elbow method to determine the appropriate number of clusters that should be used for our analysis. The following figure shows the change in wcss vs. the number of clusters. Based on the following figure, I used 7 cluster segments.<br>
<img src='https://github.com/kaveh7293/Bank-Customer-Segmentation/blob/main/wcss.png' width="400" height="300"><br>
The results of the customer segmentation showed that 37% of the customers in the fifth cluster left the bank (about 100% more than the average value of 16%). The seventh cluster had the smallest fraction of customers that left the bank. To evluate the important features that are noticeably influence the clusters, I used a PCA dimension reduction to  facilitate the visualization.
  
  The corresponding visualization for the corresponding clusters are shown in the following figures based on the first three principal components of the data. Note that the first two principal components can describe aboute 41% of the variation in the data and the the first three can describe 53% of the data, so the following figures are only arround a half of total variability in the data. As can be seen, however, the variability of the clusters can be seen in the following figures even with 53% of total variability:<br>
<img src='https://github.com/kaveh7293/Bank-Churn-Customer-Prediction/blob/main/t1_t2.png' width="500" height="300"><br>
<img src='https://github.com/kaveh7293/Bank-Churn-Customer-Prediction/blob/main/t3_t1.png' width="500" height="300"><br>
<img src='https://github.com/kaveh7293/Bank-Churn-Customer-Prediction/blob/main/t3_t2.png' width="500" height="300"><br>

   In the next step, I determined the fraction of each cluster that left the bank. By doing so we can identify the common characteristics that the leaving customers share. The results showed that the yellow dots are the corresponding customer cluster with a maximum fraction of people who are prone to leave, and the cluster in purple is the one with the smallest fraction of people who are prone to leave the bank. As shown in the figures above these the yellow cluster is located on the negative part of t1 and t2 axes and is at the center of t3 axis. However, the data in purple clusters are skewed towards the positive side of the t1 axis and are located on the positive part of the t2 and t3 axes. As a result, using the loading plots for different features can provide informative results regarding the important features that distinguish cluster members in yellow and purple clusters. Since the yellow and purple clusters are distirbuted relatively similar along the t1 axis, we mostly attribute the differeces in the member properties based on the t2 and t3 scores. Based on the following figures, total revolving balance,total quarter to quarter changes, and total transaction amounts have the highest loading values corresponding to the second principal component. As a result, customers in the purple cluster most probably have a large value of revolving balance, quarter to quarter changes, and relatively high amount of transaction amount. It should be noted that the members in the purple cluster in the figure are fell on a large area from central to the upper right section of the plot. As a result, not all of the above mentioned features should be accounted for the customers tendency to leave. I guess that the features <im> value of revolving balance, quarter to quarter changes </im> are mostly important on the fraction of the customers that leave the company. I will do in the next section a visualization analysis to determine the distinguishing features among the top three candidates. Further, the information regarding the loading values corresponding the third principal component show that people in the purple cluster (are skewed toward the positive side of t3 axis) have spent a higher amount of transacations and have higher change in the quarter to quarter amount.    <br>
  One important value that can be determined based on the t score values are the loading values. The highest loading value corresponding to the first principal component is the age column and <br>
  <img src='https://github.com/kaveh7293/Bank-Churn-Customer-Prediction/blob/main/PC1.png' width="800" height="300"><br>
  <img src='https://github.com/kaveh7293/Bank-Churn-Customer-Prediction/blob/main/PC2.png' width="800" height="300"><br>
  <img src='https://github.com/kaveh7293/Bank-Churn-Customer-Prediction/blob/main/PC3.png' width="800" height="300"><br>
 
</p>
