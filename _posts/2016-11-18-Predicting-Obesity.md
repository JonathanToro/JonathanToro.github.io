---
layout: post
title: Is your neighborhood fat?
---
Obesity is a serious problem that jeopardizes any individual's well being. Being obese means having a body mass index greater (BMI) greater than 30. This increases the risk of developing a plethora of debilitating health conditions such as coronary heart disease, diabetes, depression, strokes, and even cancer. We often hear in the news about the obesity epidemic in America. According the the CDC as many as 35 percent of Americans are considered obese. This monumental figure sparked my interest in investigating why is obesity so prevalent within our population. Thus, I looked online for data to see what trends I can find about the population. I found 6 data sets from the Community Status and Health Indicators (CHSI) database that described the demographics, social behaviors, causes of deaths, preventive services use, environmental statistics, and importance of health by county. The data has 3142 counties in total. After looking through the data I saw that the obesity rate for around 30% of the counties was missing. Therefore, I decided to predict whether these missing counties were above or below the median obesity rate.

The graph below was made using d3.js and visualizes the obesity rate by county. The darker blue means that there is a higher obesity rate. The gray means that data is missing for these areas.

![alt text]({{ site.baseurl }}/images/Selection_027.png) 

The chart below shows the distribution of obesity rates in the counties. The mean and median are around 24%.

![alt text]({{ site.baseurl }}/images/Selection_028.png)

Another visualization of the obesity rates by state. 

![alt text]({{ site.baseurl }}/images/Selection_029.png)

Combining all the data sets gave me around 500 features. There are only 3142 counties so I had to reduce the dimensionality of the data. I did so by adding random noise to the data and running a random forest several times to determine the most important features that contribute to obesity rates. We were left with around 20 features. My next step was experimenting with several classification algorithms with these 20 features. The graph below shows the ROC score of all the different models that were used. We can see that Ada Boosted Trees, Gradient Boosted Trees, and Logistic Regression all had a simliar performance. For sake of interpetation I decided to further my analysis with Logistic Regression.

![alt text]({{ site.baseurl }}/images/Selection_030.png)

The chart below shows the confusion matrix for the logistic regression model. We can see that it performed generally well with both classes. THe precision and recall scores were both 0.71. The features that gave a county a higher probability of having higher obesity rates were counties with high rates of no exercise, diabetes, primary care physician visits, poverty, Asian, toxic chemicals, recent drug use, females with heart disease, under 19, and white. The features that gave a lower probability of having high obesity rates were counties with high rates of few fruit and vegetables consumption, black, ages 19-64, dentist rate, and depression. These results can imply that educating people younger than 19 years about diet and exercise is an effective way of fighting obesity. In addition, race and culture has an affect on obesity.

![alt text]({{ site.baseurl }}/images/Selection_031.png)

The graph below shows the predictions of the counties with the missing data along with the data from the training set. Orange means that the county has an obesity rate higher than the median. Brown means the counties have an obesity rate lower than the median.

![alt text]({{ site.baseurl }}/images/Selection_033.png)
