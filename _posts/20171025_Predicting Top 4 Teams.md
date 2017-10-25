# Predicting Top 4 teams in Spanish Soccer League

<center><img src="/files/fig/proj3/1_intro_points.png" width="400"></center>

## Introduction
This blog is based on my 3rd data science project at Metis/Chicago. 
I used the same dataset as that in 2nd project, where I built a linear regression model to predict the final points for teams in the Spanish Soccer league (called La Liga). Two primary features include goals scored and goals lost. For each team in the league, the predicted points agree quite well with the true data, with result summarized in Figure 1.
For this project, I will be focusing on using *classification* models to predict the top 4 teams in the league, which will be qualified for the next year’s Champions League, which means reputation and money for the team and players.

## Analysis Approach
Soccer data for past 20 years was scraped from [Fox sports] (http://www.foxsports.com/soccer/standings?competition=2&season=2013) and [Wikipedia]() by selenium. Pandas was applied for data standardization and exploration. Finally
I used the scikit learn, the machine learning package in python, and 6 different built-in classifiers for classification study and optimized based on the overall results. The dataset is similar to that used in the last project. 

The features and target were illustrated in Figure 2 and the tools used in this project were summarized in Table 1.

Table 1. Tools used in this project.

|Application | Tools used |
| --- | --- |
|Data scraping |[BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/) and [Selenium](http://selenium-python.readthedocs.io/)|
|Data Exploration | SQL & Pandas |
|Plotting and visualization | Matplotlib|
|Classification package| Scikit-learn |
|Classification models| Logistic regression, KNN, Naive Bayes, SVM, Decision Tree, Random Forest |


<center><img src="/files/fig/proj3/2_procedure.png" width="350"></center>
<center>Figure 2. Procedure for data analysis.</center>


## Results & Discussion
### Data Exploration
I started exploring the data by plotting the data with features and classes, as shown in Figure 3. Two primary features were included: goals scored per game and goals lost per game. The data was separated to two classes: top 4 or not-top-4. The objective of this project is to find the optimal cutting-off to separate out the two class. This graph seems reasonable in the sense that, usually, top teams would scored more goals and lose less goals.


<center><img src="/files/fig/proj3/3_data_2d.png" width="700"></center>
<p><center>Figure 3. An overview of the features and classes.</center></p> 


### Model prediction
Figure 4 shows optimized results and final scores (accuracy, precision, recall and F1) for 6 classification models. Usually, higher scores indicate better predictions. As we can see, all scores are more than 0.8, implying similar and reasonable predictions from all models.


<center><img src="/files/fig/proj3/4_models.png" width="400"></center>
<center>Figure 4. Prediction scores.</center>


### Contribution of individual players matters
Apart from the modeling, what I found most interesting about data science is to explore and discover something new. In this project, when I took a look at the prediction over time, something interesting came up. According to Figure 5,  we can clearly see that, the average precision score based on 6 models, is increasing over time, which means that the model is becoming better around the year of 2010.


<center><img src="/files/fig/proj3/5_precision_time.png" width="400"></center>
<center>Figure 5. Performance of the models varies over time.</center>


If we look at the primary feature, of ‘goals scored per game’, over time, the goals scored for top teams are increasing after the year of 2010, particularly for top 2 teams. The most possible reason I can think of is these two players and two clubs, Lionel Messi from the club of Barcelona, Cristiano Ronaldo from the team of Real Madrid. They are possibly 2 best soccer players, from 2 best soccer teams in the world, for past 10 years. 

<center><img src="/files/fig/proj3/6_2010.png" width="400"></center>
<center>Figure 6. Correlation when including more features.</center>

Here, we are looking at the contribution of a player to the team over time. x axis is the time, y axis is the goals of the player and the whole team. For example of Messi, he was born somewhere, and he became as a regular player from here, and scores many many goals from the year around 2008. Besides, the trend of team fits well with the contribution of the player, which probably indicates that contribution of Messi is critical for the improvement of the team. The same trend applies to Ronaldo and Real Madrid. This individual player contributes significantly to the team.

With that in mind, let us get back to the classification model, these two extraordinary players made their teams outperform the rest teams, easily secure two positions in top4. In other words, it is relatively easy for classification models to isolate these 2 teams, simply because they are so good.



<center><img src="/files/fig/proj3/7_messi_ronaldo.png" width="400"></center>
<center>Figure 7. Contribution of individual players to the team.</center>





## Conclusions
* It is feasible to use machine learning algorithm to predict whether a team is top 4 based on the goals scored and goals lost. 
* Although soccer is a team sports, with 11 players, an outstanding individual would have a significant effect on the team, even the league. 


## Image credits
1. [La Liga](https://twitter.com/laliga)
2. [Selenium](http://selenium-python.readthedocs.io/)
3. [Fox sports](http://www.foxsports.com/watch/fs1)
4. [Pandas](http://pandas.pydata.org/)
5. [Scikit-learn](https://github.com/scikit-learn/scikit-learn)
6. [Ronaldo](http://ftw.usatoday.com/2017/06/nike-cristiano-ronaldo-ad-adidas)
7.[Messi](https://www.youtube.com/watch?v=xMA6p0jyDYM)
8. [FC Barcelona](https://www.fcbarcelona.com/news)
9. [Real Madrid C.F.](https://twitter.com/realmadrid)
