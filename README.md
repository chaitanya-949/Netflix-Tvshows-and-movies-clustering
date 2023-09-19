# Netflix-Tvshows-and-movies-clustering
# Project Type - EDA/Unsupervised
# content
-
• Problem Statement 
• Data Summary 
• Exploratory Data Analysis (EDA) 
• Feature Engineering & Selection 
• Textual Data Preprocessing
• ML Model Implementation(clustering)
• Conclusion


# Problem Statement
Netflix is the world's largest online streaming service provider, with over 220 million subscribers as of 2022-Q2. It is crucial that they effectively cluster the shows that are hosted on their platform in order to enhance the user experience, thereby preventing subscriber churn.

We will be able to understand the shows that are similar to and different from one another by creating clusters, which may be leveraged to offer the consumers personalized show suggestions depending on their preferences.

The goal of this project is to classify/group the Netflix shows into certain clusters such that the shows within a cluster are similar to each other and the shows in different clusters are dissimilar to each other.


# variable description
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

# Data Summary
There are 7787 rows and 12 columns in the dataset
.In the director, cast, country, date, and rating columns, there are missing values. 


# EDA (INSIGHTS)
- I see movies are more in number with 5377 count and tv shows with 2410.
- In the ‘Title’ i found there is a high frequency in words like world,man,love,girl,christmas
- Number of TV SHOWS directed by directors are : 184
- Number of MOVIES directed by directors are : 5214
- The three shows directed by Alastair Fothergill are the highest on the data list.
- Jan Suter,Raul Campos have directed 18 films, more than anyone else in the dataset.
- Number of TV Shows actors: 13585
- Number of Movies actors: 23049
- The majority of the roles in the movies are played by Anupam Kher, Shahrukh Khan, and Om Puri.
- In the shows, Takahiro Sakurai, Yuki Kaji, and Daisuke Ono played the most number of roles
- The United States-based movies and TV shows were produced most, followed by India and the United Kingdom
- In India and United State, a greater number of movies are present compared to TV shows.
- In the UK, Japan, and South Korea there are a greater number of TV shows than movies.

- Netflix starts releasing more Movies/TV shows in recent years compared to old ones.
- Most Movies and TV shows are available on Netflix between 2015 and 2020, and the highest are in 2018.
- The majority of Movies and TV shows have a rating of TV-MA, which stands for "Mature Audience," followed by TV-14, which stands for "Younger Audience."
- When compared to TV shows, Movies receive the highest rating as we saw earlier in the type column.

- International Movies, Dramas, and Comedies make up the majority of the genres.
- Tv horror,Teen shows,Cult movies are stand last in the genre

# Feature engineering and selection
- I have replaced the missing values in the director, cast, and country attributes with the "empty string" .
- and in other columns if there are null values I dropped them
# Textual data preprocessing
I have added Director,cast,country,rating,listed_in,description columns together and made a new column        text_data

I have used TFIDF vectorization which stands for Term Frequency Inverse Document Frequency
The product of TF and IDF is used to calculate the overall weight of a word in a document, which is known as the TF-IDF score. Words with high TF-IDF scores are considered to be more important and relevant to the document than words with low TF-IDF scores.

I have used PCA which stands for principle component analysis to reduce the dimensionality of data.

3000 components alone account for more than 80% of the variance. Therefore, we can take the top 3000 components to reduce dimensionality and simplify the model while still being able to capture more than 80% of the variance.

![image](https://github.com/chaitanya-949/Netflix-Tvshows-and-movies-clustering/assets/122298275/3cf5923f-d213-4f71-a7fb-f3fe779cc4d4)

![image](https://github.com/chaitanya-949/Netflix-Tvshows-and-movies-clustering/assets/122298275/5104c166-fccc-406e-8ac0-381282814614)

# conclusion
In this project, we tackled a text clustering problem in which we had to categorize and group Netflix shows into specific clusters in such a way that shows in the same cluster are similar to one another and shows in different clusters are not.

There were approximately 7787 records and 12 attributes in the dataset.

We started by working on the missing values in the dataset and conducting exploratory data analysis (EDA).

It was discovered that Netflix hosts more movies than television shows on its platform, and the total number of shows added to Netflix is expanding at an exponential rate. Additionally, most of the shows were made in the United States.

The attributes were chosen as the basis for the clustering of the data: cast, country, genre, director, rating, and description The TFIDF vectorizer was used to tokenize, preprocess, and vectorize the values in these attributes.

5000 attributes in total were created by TFIDF vectorization.

The problem of dimensionality was dealt with through the use of Principal Component Analysis (PCA). Because 3000 components were able to account for more than 80% of the variance, the total number of components was limited to 3000.

Utilizing the K-Means Clustering algorithm, we first constructed clusters, and the optimal number of clusters was determined to be 7. The elbow method and Silhouette score analysis were used to get this.
The Agglomerative clustering algorithm was then used to create clusters, and the optimal number of clusters was determined to be 8. This was obtained after visualizing the dendrogram.

