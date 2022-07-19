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
<img src='https://github.com/kaveh7293/Bank-Customer-Segmentation/blob/main/wcss.png'><br>

I used seven clusters as the optimum customer segments. To further understand different customer behaviors, I used a biplot which plot the projected data on the principal components and the loading plots simultanously.<br>
<img src='https://github.com/kaveh7293/Bank-Customer-Segmentation/blob/main/PC2_PC1.png'><br>
<img src='https://github.com/kaveh7293/Bank-Customer-Segmentation/blob/main/PC3PC1.png'><br>
<img src='https://github.com/kaveh7293/Bank-Customer-Segmentation/blob/main/PC4PC1.png'><br>
<img src='https://github.com/kaveh7293/Bank-Customer-Segmentation/blob/main/PC5_PC1.png'><br>
<img src='https://github.com/kaveh7293/Bank-Customer-Segmentation/blob/main/PC6_PC1.png'><br>
<img src='https://github.com/kaveh7293/Bank-Customer-Segmentation/blob/main/PC7.png'><br>
  Note that the light blue arrows are the feature vectors projected onto the principal components.
</p>
<p> The following important conclustions can be made based on the biplots shown above:
  <ol>
    <li>Customers in the <strong> blue cluster </strong> have a <strong> high credit limit </strong> and a <strong> high average open to buy</strong>. The customers in this cluster are more from geneder_2 (i.e., they are <strong> women </strong>)</li>
    <li>Customers in the <strong> pink cluster </strong> have a <strong> high revolving balance </strong>,  and a <strong> high transacation amount</strong>. The customers in this cluster are more from geneder_2 (i.e., they are <strong> women </strong>)</li>
<li> Customers in the <strong> purple cluster </strong> have <strong> a high amount of change in Q4 over Q1 </strong>.</li>
    </ol>
</p>
