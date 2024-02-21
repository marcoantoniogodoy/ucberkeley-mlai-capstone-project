# Capstone Project: Let's make it a hit song!

**By Marco Antonio Godoy**

#### Executive summary
For more than 20 years, I've been actively and passively involved in the highly competitive music industry, in roles related to music production, engineering, composition, songwriting, performance and consulting. I've had the opportunity to work with many artists from different nationalities, styles and backgrounds, in a wide array of projects, from collaborations (aka "no money") to fully funded productions backed by major record labels. Over the years, I've witnessed how some of these artists have achieved international recognition, while others have not been able to grow their local niche audiences. Surprisingly, the financial support that major labels provide to their artists doesn't always translate into successful acts. In fact, by leveraging the power of social media, some independent artists have been able to grow bigger audiences than some of their counterparts, even with much smaller marketing budgets. Moreover, I've noticed how fans seem to favor the charisma and big persona of some artists over the exceptional talent of others. However, one crucial differentiator between those who "make it" in the music business and those who don't is that behind every successful artist there's always a "hit" (top played) song. Therefore, I find in this capstone project the perfect opportunity to leverage AI/ML techniques with the goal of identifying the  qualities and attributes that make a song a "hit".  

#### Rationale
Some years ago, a friend of mine came to my studio asking for my help to record a song that he had just written. Although he was already a successful songwriter at the time, I admit that when I heard the song I didn't see any potential on it to become a hit. My friend, on the other hand, was convinced it was. I still helped him record the song, which in my opinion only had the quality of a songwriter demo (those which are pitched to artists). A few months later, I received a call from that same friend thanking me enthusiastically for helping him out with the record. The song and the recording we made that day had become a major hit!

That personal experience made me understand at a deep level the complexities of the music business, specially because of its subjective nature. Many record labels spend fortunes in the development of artists, but they struggle to find songs that have potential to become hits. This might be the reason why some artists have resorted into recording cover songs (songs that have been recorded previously by other artists). 

Therefore, designing a model that can predict with a high precision if a song has the potential to become a hit can translate into significant cost reductions for both the artists and the record labels since it would help reduce the "guess" work when choosing which songs to record and promote.   

#### Research Question
What are the attributes that a song needs to have to become a "hit"?

#### Data Sources
This analysis is primarily based on a dataset titled [Spotify Dataset 2023](https://www.kaggle.com/datasets/tonygordonjr/spotify-dataset-2023?select=spotify_tracks_data_2023.csv) by [Tony Gordon](https://www.kaggle.com/tonygordonjr) available at Kaggle. The author did an exceptional job fetching the data from the Spotify API and organizing it into five subdatasets containing "albums", "artists data", "Spotify data", "features data" and "tracks data". The total columns for the entire dataset is 108, and the largest dataset ("tracks data") contains a total of 438938 entries, and a feature named "track_popularity" which will be a crucial feature in this analysis.  Although this dataset seems to contain all the data needed to work on this analysis, additional data can be obtained from the [Spotify API](https://developer.spotify.com/documentation/web-api) 

Another important data source is the [Billboard](https://www.billboard.com/), which contains music listings rated by popularity and considered industry standard. For example: [Billboard Hot 100](https://www.billboard.com/charts/hot-100/) which lists the top 100 songs in the US and the [Billboard Global 200](https://www.billboard.com/charts/billboard-global-200/) which lists the 200 songs in the global market. 


#### Methodology
Based on the research question, the goal of the analysis is to build a model that can predict if a song has the potential to become a hit. This means, finding the most important attributes that are common among hit (top played) songs. Therefore, we first need to define a threshold for what we'd considered to be a top song. For example, although aiming to build a model  that predicts if a song will be the number one would be extremely powerful, the precision of such model would then result in a low recall. Meaning it would ignore attributes for songs that could make it into the top 100 songs which is considered an industry standard by Billboard. Once the decision is made on the threshold, we'll introduce the target variable "hit" based on if the song popularity is below or above the threshold. 

 
At this point, the problem will become a binary classification problem. Therefore, the analysis will leverage data classification models such as Logistic Regression, K-Nearest, Support Vector Machines and Decision Trees.  

#### Results
During the data modeling phase the following results were obtained:
<ul>
    <li>
        As per training time, the best performing model was the KNN (aside from the Dummy Classifier), followed by the logistic regression model.
    </li>
    <li>
        As it relates to test accuracy and precision, the best results were produced by the Decision Tree classifier, followed by the Logistic Regression model. 
    </li>
    <li>
        In regards to recall, KNN and SVM obtained a perfect score of 1. However, this might be an indication of overfitting. Therefore, we may consider more proper recall scores by the Logistic regression model followed by the Decision Tree classifier. 
    </li>
    <li>
    Using feature selection it was determined that the most influential feature when it comes to track popularity is the track's genre. Moreover, the "pop" genre seems to be the most determining factor. 
    </li>
    <li>
    Although model optimization was performed via GridSearchCV, the models trained with the default hyper parameters produced better results. Therefore, further hyperparameter tuning may be necessary in 
future iterations.</li>
</ul>




#### Next steps
At this stage of the project we have produced a clean dataset that contains what we believe to be the most relevant features to create a model that can predict with high accuracy if a song has the potential to be a hit. 

As it was found, the most determining factor seems to be the song genre, from which the "pop" genre seems to be the strongest genre among hit songs. However, this dataset provides a rich amount of information about track characteristics, including tempo, key, mode, energy, etc., that we believe are worth exploring aside from song genre. Therefore, as a next step, we'll perform another iteration where the song genre is ignored to see if we can obtain valuable information about the characteristics of hit songs.

Additionally, we will look into validating our model with information obtained from the Billboard music charts since these charts are considered standards in the music industry. 

#### Outline of project

- [Main Notebook](https://github.com/marcoantoniogodoy/ucberkeley-mlai-capstone-project/blob/main/CapstoneProject_20.1.ipynb)


##### Contact and Further Information
If you have any questions, comments or suggestions, please reach out via [LinkedIn](https://www.linkedin.com/in/marco-antonio-godoy)