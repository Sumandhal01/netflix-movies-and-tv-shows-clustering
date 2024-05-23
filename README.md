# netflix-movies-and-tv-shows-clustering

## Objective
This project focuses on clustering Netflix movies and TV shows based on various attributes such as genre, release year, duration, and user ratings. The goal is to group similar content together, enabling better content recommendations and analysis.

## Dataset
We get a dataset of Netflix. Tv Shows and Movies are included in this dataset. It has the following attributes:
- show_id : Unique ID for every Movie/Show
- type : Identifier - Movie/Show
- title : Title of the Movie/Show
- director : Director of the Movie/Show
- cast : Actors involved in the Movie/Show
- country : Country where the Movie/Show was produced
- date_added : Date it was added on Netflix
- release_year : Actual Release year of the Movie/Show
- rating : TV Rating of the Movie/Show
- duration : Total Duration - in minutes or number of seasons
- listed_in : Genre
- description : The Summary description

## Features
1.Data preprocessing and cleaning
2.Feature extraction and selection
3.Clustering using K-means algorithm
4.Visualization of clusters
5.Recommendation System

## Library used
- numpy
- pandas
- matplotlib
- seaborn
- wordcloud
- nltk
- sklearn
- scipy

## Data Cleaning and Data Preprocessing
 [1] Handling Duplicate Values :
 - Dataset having no duplicated values.
 [2] Handling Null / Missing Values :
 - Since there are many null values for features like director, cast, and country, those null values cannot be dropped; 
 instead, they have been substituted with director Unavailable, Cast Unavailability, and Country Unavailable, accordingly.
 - Features such as date_added and rating have a very low number of null values, so we dropped those null values.
 [3] Handling Outliers :
 - Outliers from variable release_year are successfully treated using the interquartile range.
 [4] Feature Engineering :
 - Converted feature date_added to datetime and created new features from it, such as year_added,
 month_added, and day_added, before removing the feature date_added. 
 - The listed_in feature has been renamed to geners.
 - Because year cannot be a float, the feature release_year data type changed from float64 to int64.
 [5] Textual Data Preprocessing :
 - We processed text data from the description variable by removing punctuation, stopwords, whitespace, emails, urls, special characters etc.
 - Text vectorized after lemmanization and got a TFIDF matrix using TfidfVectorizer for feeding to the model as input.

## Model Building
 We implemented the following unsupervised machine learning models:
 - K-Means Clustering
 - Hierarchical Clustering
 - DBSCAN Clustering

## Conclusion
In this project, we successfully applied three different clustering algorithms (K-Means, Hierarchical, and DBSCAN) to group Netflix movies and TV shows based on their similarities. Each algorithm provided valuable insights into the data, and we evaluated their performance using various metrics such as silhouette score, Calinski-Harabasz score, and Davies-Bouldin score.

Based on our analysis, the K-Means clustering algorithm with 6 clusters provided a good balance between cluster separation and compactness. The hierarchical clustering algorithm with 7 clusters also yielded meaningful clusters, while the DBSCAN algorithm identified 18 clusters with varying sizes.

Furthermore, we built word clouds for each cluster to visualize the most frequent words associated with each group. This analysis provided additional insights into the characteristics of each cluster and helped us understand the underlying themes and trends within the Netflix content.
