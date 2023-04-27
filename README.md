# Crypto-Clustering-Unsupervised

In this project we are using Python and unsupervised learning to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.

### Prepare the Data

To normalize the data from the CSV file  the StandardScaler() module from scikit-learn is used.

Then created a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

The first five rows of the scaled DataFrame appear as follows:

<img width="807" alt="image" src="https://user-images.githubusercontent.com/116701851/234993223-822c4128-c3a5-4b81-b356-30804e3f98fc.png">


### Find the Best Value for k Using the Original Scaled DataFrame


To find the best value for k using  the elbow method  with the following steps:

Created a list with the number of k values from 1 to 11.

Created an empty list to store the inertia values.

Created a for loop to compute the inertia with each possible value of k.

Created a dictionary with the data to plot the elbow curve.

<img width="154" alt="image" src="https://user-images.githubusercontent.com/116701851/234994911-e627ab34-f3b6-4851-a3fe-f0a3aa3e940e.png">


Plotted a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.

<img width="737" alt="image" src="https://user-images.githubusercontent.com/116701851/234995184-c67e7535-e419-420f-9851-9f22d5f1196d.png">


Answer the following question in your notebook: What is the best value for k?

<img width="129" alt="image" src="https://user-images.githubusercontent.com/116701851/234995306-453b7450-6a41-46b1-90bf-130670e8984e.png">


### Cluster Cryptocurrencies with K-means Using the Original Scaled Data

Using the following steps to cluster the cryptocurrencies for the best value for k on the original scaled data:

Initialized the K-means model with the best value for k.

Fit the K-means model using the original scaled DataFrame.

Predict the clusters to group the cryptocurrencies using the original scaled DataFrame.
Then,
Created a copy of the original data and added a new column with the predicted clusters.

Created a scatter plot using hvPlot as follows:

Setting the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
Colored the graph points with the labels found using K-means.
Added the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.


<img width="781" alt="image" src="https://user-images.githubusercontent.com/116701851/234998432-5139b802-1d01-4bdb-a715-a41ffcb07cb8.png">


### Optimize Clusters with Principal Component Analysis

 Performed a PCA and reduce the features to three principal components using the original scaled DataFrame.

Retrieved the explained variance to determine how much information can be attributed to each principal component .

<img width="591" alt="image" src="https://user-images.githubusercontent.com/116701851/235000680-8e77d7f2-07b4-427e-81fc-a32975e26c94.png">

What is the total explained variance of the three principal components?

<img width="152" alt="image" src="https://user-images.githubusercontent.com/116701851/235000840-5ddeb381-96a1-491a-b506-3a9c1839cc31.png">

Created a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

The first five rows of the PCA DataFrame appeared as follows:

<img width="321" alt="image" src="https://user-images.githubusercontent.com/116701851/235000940-ca2dda77-8826-40c2-adbe-d59beb18c010.png">

### Find the Best Value for k Using the PCA Data

Using the elbow method on the PCA data to find the best value for k using the following steps:

Created a list with the number of k-values from 1 to 11.

Created an empty list to store the inertia values.

Created a for loop to compute the inertia with each possible value of k.

Created a dictionary with the data to plot the Elbow curve.

<img width="152" alt="image" src="https://user-images.githubusercontent.com/116701851/235001893-b8481c3a-8343-42ff-a5ea-83b77dff6748.png">

Plotted a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.

<img width="734" alt="image" src="https://user-images.githubusercontent.com/116701851/235001980-bee03a24-1d2d-4927-9c81-a30523a1a6fc.png">


With the help of elbow curve plotted the following questions are answered

<img width="688" alt="image" src="https://user-images.githubusercontent.com/116701851/235002319-46e1fdf6-90da-4bca-a838-b91e1fa307ee.png">


### Cluster Cryptocurrencies with K-means Using the PCA Data

Using the following steps to cluster the cryptocurrencies for the best value for k on the PCA data:

Initialized the K-means model with the best value for k.

Fit the K-means model using the PCA data.

Predicted the clusters to group the cryptocurrencies using the PCA data.

Create a copy of the DataFrame with the PCA data and add a new column to store the predicted clusters.

<img width="428" alt="image" src="https://user-images.githubusercontent.com/116701851/235002516-4633ef71-c6c2-4b28-95ab-66657d68ee1f.png">


Created a scatter plot using hvPlot as follows:

Setting the x-axis as "PCA1" and the y-axis as "PCA2".

Color the graph points with the labels found using K-means.

Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.

<img width="638" alt="image" src="https://user-images.githubusercontent.com/116701851/235002739-9cb2b2ba-a22d-492f-ad67-02ea3be23bce.png">


Along with this , i have created a 3D plot to show the prediction which felt appropriate.

<img width="1105" alt="image" src="https://user-images.githubusercontent.com/116701851/235003138-f5652453-beb3-4c1a-97da-1101cb529778.png">


### Visualize and Compare the Results¶


In this section, visually analyzed the cluster analysis results by contrasting the outcome with and without using the optimization techniques.

<img width="440" alt="image" src="https://user-images.githubusercontent.com/116701851/235003433-e4e0a3e3-1e0b-441a-918c-689afb0a3f5f.png">

<img width="389" alt="image" src="https://user-images.githubusercontent.com/116701851/235003500-068dab13-2837-429b-a84f-d14e2cf85148.png">

# Conclusion:

What is the impact of using fewer features to cluster the data using K-Means?

The conclusion is, generally using less features results in similar outcomes to the base model as the fitting shows 4 clusters 
Reducing the number of features (columns) helps make the clusters more apparent.






