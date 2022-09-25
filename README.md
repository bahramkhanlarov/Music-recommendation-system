# Music-recommendation-system

## Introduction 

 

With the rising popularity of several music streaming platforms such as Deezer among others, the global music industry is expected to grow exponentially. With the ever-rising demand for online music streaming services, there comes the need to personalize the user experience and provide users with what they are looking for. A music recommendation system is a powerful tool for several music streaming service providers helping their users find the right music and enjoy a hassle-free music streaming experience. 

## What is the need for recommendations in the music streaming business? 

A music recommender solution is a solution that allows music streaming platforms to offer their users relevant music recommendations in real-time. It provides personalization and thus boosts user engagement. The recommender system is helpful to both service providers and users. It saves time for the user in finding and selecting a perfect song and at the same time, it also helps service providers retain customers for a longer time on their platform. 

The music recommendation system is leveraging the music streaming business through a couple of areas. Such as maximum user engagement, meaning consumers will get themselves more engaged on the website or application when personalized music recommendations are made to them. The music recommendation engine recommends songs according to a user’s preference and creates a list of the same genres of songs. This helps users to dive even more deeply into the playlist without needing to search one after the other. As a result, the maximum of time a user is spent on a particular platform gives a boost to user engagement. 

This will also increase Customer Satisfaction. In the music streaming business, when a listener sees a music playlist completely personalized according to their taste, it appeals to them to continue to spend time listening to their favorite track one after the other.  

The recommender engine provides easy music discoverability. It allows end-users to find out more tracks and albums according to their choice. This helps users discover more songs present on your platform. Without a recommendation, many of the users will not be able to discover their favorite tracks. 

Increase in the number of subscribers is another benefit from the music recommendation system. With more ambitious artists as well as easy access to music and podcasts, it is hard to compete with opponents. The recommender engine analyzes consumed music, favorite artists, speakers, genres, or descriptions in several languages, to help music streaming platforms offer podcasts and music recommendations tailored to personal tastes. 

The recommendation engine works with information about which songs or podcasts were listened to by the user till the end and which were skipped in the middle. Lastly, it provides recommendations of genres, artists, and playlists to let the end-user enjoy and appeal to them to revisit your platform and thus convert into a subscriber. 

 The application of recommendation engine has and is bringing billions of revenues to several businesses, and it does the same to music streaming businesses too. It enhances the method of doing business online and gives a better return on investment. With advanced machine learning and AI, we can proudly say it will make customer retention and loyalty better than ever. 

## Analysis 

For this project, we need to look at Deezer ‘s Flow, its own music recommendation radio. The concept of Flow uses collaborative filtering to provide a user with the music the user wants to listen at a given time.  

The expression “You never get a second chance to make a first impression” indicates how people often make snap judgments. The same holds true when installing and trying a new application for the first time. Just as you would negatively judge someone showing up late to a first date, what would you think of an application that gives you far off the mark recommendations, even though you explicitly stated your preferences? 

In this context, online music streaming services such as Deezer must quickly come up with accurate content that new subscribers are likely to enjoy. However, while we know recommendation algorithms work well for users who have had enough interactions with the service (and that their preferences are well known), recommending music to new users remains a largely unresolved challenge for the research community. In scientific literature, this is commonly referred to as the user cold start problem. 

The goal of this challenge is to predict whether the users of the test dataset listened to the first track Flow proposed them or not. Deezer considers that a track is "listened" if the user has listened to more than 30 seconds of it (is_listened =1). If the user presses the skip button to change the song before 30 seconds, then the track is not considered as being listened (is_listened = 0). 

The test dataset consists in a list of the first recommended tracks on Flow for several users. Each row represents one user. The train dataset was generated using the listening history of these Deezer users for one month. Each row represents one listened track.  

Our first step was exploring the data and its features. In order to find the best solution for the given task we decided to use two approaches, classification, and Restricted Boltzmann Machine (RBM).  

## Classification 

Using the Random Forest Algorithm, we inspected the importance of the features and selected the most informative and important columns. With this step, now we are ready to train a model. There are several modelling algorithms one can choose from, that’s why is important to understand the problem and the solution we are aiming for. Our challenge is both a classification and a regression problem. We need to identify a relationship between the output, is a song listened or not, and the other variables as for example the timestamp of the listening, the type of the song and so on. We are also training our model with a given dataset using supervised learning and given these two criteria we can narrow down the choice of models to a few. Those are Logistic Regression, KNN. SVM, SGD.  The results we got from all the models in general were satisfying. We ranked the models to choose the best one that fits our problem, and while both Decision Tree (99.63) and Random Forest (99.63) have the same score, we decided to proceed with Random Forest as it better approaches the overfitting problem.  (For the classification script see <ins>[this notebook](https://github.com/bkhan1820/Homegate.ch-scraping-and-data-analysis-with-Pandas/blob/Master/Homegate_Data%20_Transformation%20&%20Data_Enrichment.ipynb)</ins>)

## Restricted Boltzmann Machine (RBM) 

 

Boltzmann Machine is a generative unsupervised model, which involves learning a probability distribution from an original dataset and using it to make inferences about never-before-seen data.  

Our final Recommender System will be able to predict if the user will listen to a song or not. Accordingly, by ranking the predictions with -1 to 1, (meaning 1 - the song was listened over 30 sec, 0 - the song was listened to less than 30 sec and -1 – the song was not listened at all) our Deep Learning model will be able to recommend which songs each user should listen. 

Our model is Deep Belief Networks, complex Boltzmann Machines. After preparing the train and the test datasets, in order to build the RBM, we need a matrix with the users’ “ratings”. The matrix will contain a user’s “rating” of a specific song. To create this matrix, we need to obtain the number of songs and the number of users in our dataset. 

Since we’re using PyTorch, we need to convert the data into Torch tensors. The way we do this is by using the FloatTensor utility. This will convert the dataset into PyTorch arrays.  

Next, we convert these “ratings” into binary ratings since we want to make a binary classification. Then we continue with building our Restricted Boltzmann Machine (RBM) beginning with building its architecture, in other words building the architecture of the Neural Network. In the next step we continue with training the RBM Model by defining the number of epochs and defining the loop.  

Next, we test our RBM. In this stage, we use the training set data to activate the hidden neurons in order to obtain the output. This is how we get the predicted output of the test set. We then use the absolute mean to compute the test loss. In the last stage we use our model to predict if the next song Y is going to be listened to by user X.  

 
