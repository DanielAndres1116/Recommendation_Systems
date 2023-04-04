# 1. Recommendation Systems: showing to the users what they want

A recommendation system is a tool that helps to predict the preferences or ratings a user would give to a product or item. The purpose of a recommendation system is to provide users with personalized suggestions, based on their past interactions and behavior.

There are several advantages to using recommendation systems, including:

•	Increased engagement: By providing users with personalized recommendations, you can increase their engagement with your products or services. This can lead to increased customer satisfaction and loyalty.

•	Improved user experience: Recommendation systems can help to streamline the user experience by reducing the time and effort required to find relevant products or content.

•	Increased sales: By providing users with relevant recommendations, you can increase the likelihood that they will make a purchase. This can result in increased sales and revenue for your business.

•	Improved customer insights: Recommendation systems can help to provide valuable insights into customer behavior and preferences. This information can be used to inform future product development and marketing strategies.

In conclusion, recommendation systems offer a range of benefits to businesses and organizations, by helping to increase engagement, improve the user experience, increase sales, and provide valuable customer insights.

There are different types of recommender systems, and they are:

## 1.1. Content-Based Recommendation Systems

Content-based recommendation systems use the attributes or characteristics of items to recommend other similar items. These systems analyze the content of items, such as the genre of a movie, the author of a book, or the keywords in an article, to make recommendations.

For example, a content-based recommendation system for a movie streaming service would recommend movies based on the user’s past movie preferences, such as their favorite actors, directors, or genres.

![image](https://user-images.githubusercontent.com/43154438/229680935-7d0f0d06-46a8-4192-9bb9-2124f37340d9.png)

Figure 1: representation of what Content-Based Recommendation Systems consist on.

## 1.2. Collaborative Filtering Recommendation Systems

Collaborative filtering recommendation systems use the behavior and preferences of users to make recommendations. These systems analyze the past interactions and ratings of users, such as their movie ratings or product reviews, to make recommendations to other users with similar preferences.

For example, a collaborative filtering recommendation system for a movie streaming service would recommend movies to a user based on the movie ratings and preferences of other users who have similar movie tastes.

![image](https://user-images.githubusercontent.com/43154438/229681039-e90a202e-29b8-459b-b0e2-49b8ca21d724.png)

Figure 2: representation of what Content-Based Recommendation Systems consist on.

## 1.3. Project Description

This project involves the use of a movie ratings dataset obtained from GroupLens Research. The dataset contains information about the movies watched by users of a movie-watching application and can be downloaded from the next link:

https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-ML0101EN-SkillsNetwork/labs/Module%205/data/moviedataset.zip

Since the dataset is quite large, it cannot be uploaded neither to this page nor GitHub platform, but interested parties can download it by clicking on the link provided. It’s important to note that before using the dataset, it’s necessary to review the README files to understand the usage licenses and other details.

The data was collected by GroupLens Research and made available through the MovieLens website. The collection periods varied depending on the size of the dataset.

With this dataset, you can perform various analysis and build recommendation systems to help movie enthusiasts discover new films based on their past preferences and movie ratings.

## 1.4. Explanation of the Content Based Recommendation System programming code

The code implements a content-based movie recommendation system. The system takes the input of a user’s rating of a set of movies, and recommends other movies that have similar genre characteristics to the input movies.

To accomplish this, the code performs the following steps:

1.	Loads movie information and user ratings into two pandas dataframes (movies_df and ratings_df).
2.	Cleans and processes the movie data by extracting the year of release and removing it from the movie title. It also splits the genre information into separate columns.
3.	The code creates a new dataframe (moviesWithGenres_df) that contains binary information about the presence or absence of each genre in each movie.
4.	User inputs are stored in the userInput variable, which is then merged with the movie information to obtain the movieIds for the input movies.
5.	The code creates a genre profile of the user’s preferences by taking a weighted average of the genres of the input movies, where the weight is the user’s rating of the movie.
6.	To recommend movies, the code multiplies the genre weights of each movie with the genre profile of the user and takes a weighted average to obtain a recommendation score for each movie.
7.	Finally, the code recommends the top N movies with the highest recommendation scores.
The content-based recommendation system uses a mathematical approach to recommend movies based on their genre characteristics. The system calculates the similarity between the input movies and all other movies in the database and recommends the most similar ones.

## 1.5. Explanation of the Colaborative Filtering Recommendation System programming code

The code is an implementation of a Collaborative Filtering recommendation system. Collaborative filtering is a method of making recommendations based on the preferences and behavior of similar users.

1.	The code starts by importing the required libraries and reading two data sets, ‘movies.csv’ and ‘ratings.csv’. These data sets contain information about movies and the ratings given by users to those movies, respectively. Then it manipulates the data sets to prepare them for the recommendation process.
2.	After preparing the data sets, the code takes some inputs from the user in the form of movie titles and their ratings. Then it filters the data sets to find the corresponding movie IDs and creates a new data frame called ‘inputMovies’ for the movies the user has rated.
3.	Next, the code creates a subset of the ratings data frame called ‘userSubset’ containing only the users who have rated the movies that the user has rated. The code groups these users based on their user IDs and sorts the groups based on movie IDs.
4.	After that, the code calculates the Pearson Correlation between the input user and each user in the ‘userSubset’ group. Pearson Correlation is a measure of the linear correlation between two variables. In this case, it measures the similarity between the ratings given by the input user and other users.
5.	Finally, the code uses the Pearson Correlation values to recommend movies to the user by selecting the movies with the highest average ratings from users who have a high correlation with the input user.
The code uses a lot of mathematical and statistical concepts and techniques such as mean, standard deviation, and correlation to make recommendations to the user.

## 1.6. Conclusions

In general, both content-based and collaborative filtering recommendation systems have their own strengths and weaknesses, and both can be combined to create a hybrid recommendation system that leverages the best aspects of both approaches.

### Advantages and Disadvantages of Content-Based Filtering

#### Advantages:

•	Learns user’s preferences

•	Highly personalized for the user



#### Disadvantages:

•	Doesn’t take into account what others think of the item, so low quality item recommendations might happen

•	Extracting data is not always intuitive

•	Determining what characteristics of the item the user dislikes or likes is not always obvious



### Advantages and Disadvantages of Collaborative Filtering

#### Advantages:

•	Takes other user’s ratings into consideration

•	Doesn’t need to study or extract information from the recommended item

•	Adapts to the user’s interests which might change over time



#### Disadvantages:

•	Approximation function can be slow

•	There might be a low of amount of users to approximate

•	Privacy issues when trying to learn the user’s preferences
