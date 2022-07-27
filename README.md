# Context

Hello! This is my third data science project. After playing around with supervised learning in my previous projects, I decide to explore more on the topic of unsupervised learning, particularly clustering. Here, I use aviation dataset to create a customer segmentation, analyze the customers profile in the clusters obtained, and give business recommendations accordingly. Although I am not an expert in the aviation industry, this dataset is still very interesting and fun to play around. Enjoy!

# Files
This repo contains this README, a python notebook called Airline Customer Segmentation.ipynb, a slides in pdf format to highlight the most important aspects of this project called 'Airline Customer Segmentation - slides.pdf', and the dataset flight.csv is in the data directory.

# Data
I use the Airline Customer Segmentation dataset from [Kaggle](https://www.kaggle.com/competitions/sa-customer-segmentation). It is actually still unclear for me where this dataset is originally from, but I notice that it has been circulating around the internet since at least 4 years ago. The content of this dataset is as follows:

Basic customer information:
- `MEMBER_NO`: Membership card number (ID)
- `FFP_DATE`: Membership join date
- `FIRST_FLIGHT_DATE`: First flight date
- `GENDER`: Gender
- `FFP_TIER`: Membership card level
- `WORK_CITY`: The city where the customer works
- `WORK_PROVINCE`: The province where the customer works
- `WORK_COUNTRY`: The country where the customer works
- `AGE`: Age

Flight information:
- `LOAD_TIME`: The end time of the observation window (observation window: time period of observation)
- `FLIGHT_COUNT`: Number of flights in the observation window 
- `SUM_YR_1` : Fare revenue
- `SUM_YR_2` : Votes prices
- `SEG_KM_SUM`: Total flight kilometers in the observation window
- `LAST_FLIGHT_DATE`: Last flight date
- `LAST_TO_END`: The time from the last flight to the end of the observation window
- `AVG_INTERVAL`: Average flight time interval
- `MAX_INTERVAL`: Maximum flight interval
- `avg_discount`: Average discount rate

Integral information
- `BP_SUM`: Total basic integral
- `EXCHANGE_COUNT`: Number of points exchanged
- `Points_Sum`: Total cumulative points
- `Point_NotFlight`: points not used by the customer

# Methods

In this project, I use the LRFMC model to create the segmentation, which is commonly used for aviation dataset. I use the K-means algorithm to segment the customers, and I employ the elbow method and the silhouette score to determine the optimum number of clusters (k-value). I analyze each cluster from its typical LRFMC values, which I take from the median.

This project requires the standard `numpy`, `pandas`, `matplotlib`, `seaborn`, and `sklearn` packages. In addition, it also uses `yellowbrick` to visualize the silhouette score and `plotly` to create radar charts. So you might need to install these two packages beforehand if you want to test them out.

# Results

I find that k=5 gives the best customer segmentation based on the silhouette score. I also try using k=4 and k=6 to see what information I gain/loose. With 4 clusters only, I find that the results are not optimal as I loose the information on the potential high-value customers. However, using 6 clusters, there is an additional segment of customers with very high typical value of `C`, suggesting that these customers often use the high-class seats during flights. This possibility is interesting, and so deserves to be looked in more details in the future.
