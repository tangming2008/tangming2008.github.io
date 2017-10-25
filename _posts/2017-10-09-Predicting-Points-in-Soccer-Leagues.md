---
published: true
Category: [Data Science, Linear regression]
Title: Predicting Points in Soccer League
---

![La Liga](/files/fig/proj2/02_00_laliga.jpg?raw=true)

<center><img src="/files/fig/proj2/02_00_laliga.jpg" width="400"></center>

## Introduction
This blog is built on my second data science project at Metis/Chicago. This project consists of two parts:
* Scrape the information from the web
* Apply linear regression model to correlate features with target

## Analysis Approach
The main data set I used are standings and statistics of games in the Spanish Soccer League (also called La Liga). The data was mainly scraped from [Fox sports]( http://www.foxsports.com/soccer/standings?competition=2&season=2013). The statistics data spans across 4 seasons (from 2013 to 2017). The whole data set was split into two parts: 2014-2017 data for training and building model, and 2013-2014 season data for validation. The features and target were illustrated in Figure 1 and the tools used in this project were summarized in Table 1.

Table 1. Tools used in this project.

|Application | Tool used |
| --- | --- |
|Data scraping |[BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/) and [Selenium](http://selenium-python.readthedocs.io/)|
|Data Exploration | Pandas |
|Linear Regression | Statsmodels, Scikit-learn |
|Plotting and visualization | Matplotlib and Seaborn|



<center><img src="/files/fig/proj2/02_01_flow_bw.jpg" width="350"></center>
<center>Figure 1. Machine learning flow.</center>


## Results & Discussion
### Data Exploration
I started exploring the data by considering one single feature of “Goals scored” and plotting the “final points” against “Goals scored” in the scatter plot, as shown in Figure 2. The linear correlation between this feature and the final points is obvious. The residual seems to be randomly distributed, implying that the linear regression could be a reasonable starting point.


<center><img src="/files/fig/proj2/02_02_one_feature_residual.jpg" width="700"></center>
<p><center>Figure 2. Final points against goals scored and distribution of residuals from linear fitting.</center></p>


Next, I added more features to potentially improve the model. Although we cannot totally rely on the R scores to justify the correlation, they give a first estimation on the correlation analysis. As shown in Figure 3, adding more features (slowly) increases the accuracy of the model.


<center><img src="/files/fig/proj2/02_03_all_feature.jpg" width="400"></center>
<center>Figure 3. Correlation when including more features.</center>


### Optimization
Care should be taken when dealing with the *R* scores: adding more features undoubtedly improves the *R* square, but it does not guarantee the significance of the linear correlation. The adjusted R-square, which considers the effect of the feature numbers, approximately remains constant, indicating that the rest features (after first two variables) does not have a significant effect on the model. The final model I was using is the one considering two primary features: “goals scored” and “goals lost”. The high *R* score implies the low bias, and limited 2 features and 1 degree indicate the low complexity, keeping the model away from the overfitting region.


<center><img src="/files/fig/proj2/02_04_final_model_r.jpg" width="500"></center>
<center>Figure 4. R square varying with respect to feature numbers and the final model.</center>


### Validation
Finally, I validated the model with the test data, from 2013 to 2014 season, which is not included in building the model. Figure 5 compares the true points against the predicted points. The predicted points agree quite well with the real data, which means that the linear model offers a good first-order prediction on the final points. However, the model does not correctly predict the champion of the season (lower predicted points, but higher true points). More feature engineering is needed in the future work.


<center><img src="/files/fig/proj2/02_05_validation.jpg" width="400"></center>
<center>Figure 5. Correlation between final points and goals scored.</center>


## Conclusions
* It is possible to correlate the points with features in soccer games by linear regression
* Linear regression gives a reasonable approximation on the final points, but more in-depth analysis is necessary


## References
1. Front image: [www.vbetnews.com]( https://www.vbetnews.com/la-liga-barcelona-atletico-and-real-madrid-schedules-infographic)
