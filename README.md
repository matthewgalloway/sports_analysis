# An Investigation In To The Variables That Make a Fighter Successful in the Ultimate Fighting Championship 

Dataset from kaggle (https://www.kaggle.com/rajeevw/ufcdata) combined with web scraping of sherdog website.

## 1.0 Research Questions

Statistical analysis of sports data to understand important variables for match predictions has been a study of the machine learning literature in the last 10 years[1], [2]. 

Predominantly focused on well established sports, more niche sports like mixed martial arts (MMA) have been largely ignored [3]. MMA presents an interesting problem, as a fighters skill set appears to be an important predictor of the winner of a fight (28 current champions are wrestlers, whilst 6 are kickboxers). All martial arts specialise in one method of winning either knockouts (from standing position) or submissions (from ground position). As both are permitted in MMA, a successful fighter must amalgamate two or more traditional martial arts categories to be successful. As there is currently no accurate way to describe a fighters style or understanding of the success of a style the first research question is: 

1. Can infight statistics and a fighters physical attributes be used to define styles and what is the difference in win rate of each style? 

Additionally if styles are considered important predictors for a fight, differences between the attributes used to define styles are likely to provide important information 
in to what makes a fighter successful, prompting the second research question: 

2. What are the important physical attribute and skill differences between fighters when predicting the outcome of a fight? 

![image](https://user-images.githubusercontent.com/52289894/75584702-37f31e80-5a68-11ea-913d-a3c9eda7b81d.png)


## 2.0 Findings

Modeling method of winning as a crude approximation of style by weight class highlighted that weight was likely a factor in determining style. Higher weight divisions showed an increased likelihood fights would be won by knockout early and decreased the likelihood a fight would go to a decision.
x x x 

![image](https://user-images.githubusercontent.com/52289894/75585062-28c0a080-5a69-11ea-8d3f-1212fff2029a.png)

Conceptually this made sense as the more weight behind a punch the harder the hit.Examining physical attribute differences showed that older fighters were less likely to win a fight, with no observable difference in height within a weight class between xwinners and losers.

![image](https://user-images.githubusercontent.com/52289894/75585168-67565b00-5a69-11ea-96a6-1219dcf9ec73.png)

Infight statistics were highly correlated with one another showing the first hint of skills, i.e a fighter that threw a large number of punches to the head also through a large number of punches to the body, indicating he/she was a skilled striker.
Clustering algorithms were applied to low correlation features and evaluated over the 3 main principle components.

![image](https://user-images.githubusercontent.com/52289894/75585353-ce740f80-5a69-11ea-9bb3-8cc574c4db9a.png)

K-means was unable to resolve clusters effectively whilst DBSCAN showed better resolutions with a small number of unclassified points, the averages of each cluster from DBSCAN were plotted on a parallel coordinates map, figure 5 and 4 distinct fighting styles defined in Figure 6.

![image](https://user-images.githubusercontent.com/52289894/75585488-24e14e00-5a6a-11ea-9ec5-48f415aa3260.png)

Interestingly the points that DBSCAN was not able to classify were also added to the parallel coordinates with the next two highest win averages but outperformed them by 15%, as well as showing significantly better infight variables. Although thisbehaviour seems bizarre DBSCAN is noted in literature for it anomaly detection ability​[6]​. When evaluating fighters in this smaller cluster it appeared to contain the majority of the UFC champions.

![image](https://user-images.githubusercontent.com/52289894/75585390-e9df1a80-5a69-11ea-8b41-dff1df0ee849.png)

Finally plotting the win rate of all the clusters (and the noise) to answer question 1 showed no significant difference in styles win rate with the exception of the outliers cluster, which had a significantly higher performance and was thus defined as a ‘Champion’ Cluster. 


![image](https://user-images.githubusercontent.com/52289894/75585547-45a9a380-5a6a-11ea-8637-8cb83d6e79dd.png)
