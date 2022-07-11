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
<p> A k-means clustering algorithm has been usded to do a customer segmentation. We used the elbow method to determine the appropriate number of clusters that should be used for our analysis. The following figure shows the change in wcss vs. the number of clusters. Based on the following figure, I used 7 cluster segments.</p>
<img src='https://github.com/kaveh7293/Bank-Churn-Customer-Prediction/blob/main/download2.png' width="400" height="300">
