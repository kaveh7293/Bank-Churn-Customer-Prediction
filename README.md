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
<>
<h3> Clustering algorithm</h3>
<>
