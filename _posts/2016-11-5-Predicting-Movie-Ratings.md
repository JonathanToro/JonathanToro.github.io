---
layout: post
title: Can analytics help us identify critically acclaimed movies?
---

I have always been a fan of all the Hollywood classics that is so deeply ingrained in American culture. Casablanca, The Bridge of the River Kwai, Star Wars, Jaws, and many other movies are staples of American cinema. It may be obvious now that these movies are phenomenal, but before these movies were released production companies had no idea whether their audience would like the movie. Production companies would sign famous actors and directors to attract a bigger audience, but often these two factors doesn't mean the movie will be critically acclaimed. I was curious to see if there was any way we can predict the score of a movie before it is released. Therefore, I decided to look at the web for data and see which factors are the most important in producing a quality movie. 

I started by scraping data from the <http://www.boxofficemojo.com/> and <http://www.imdb.com/>. Luckily, there was already a data set on Kaggle that scraped all the important features of a movie on <http://www.imdb.com/>. I ended up with 5000 movies with 30 features such as budget, actors, actresses, movie facebook likes, year of release, country of origin, gross, duration, MPAA rating, and many more. 

I first looked at the distribution of the IMDB scores to see how the ratings were overall. The median score was 6.6 with the top 250 movies having a score higher than 8. 

![alt text]({{ site.baseurl }}/images/Selection_016.png) 

I tested out these features with a linear regression model and only achieved a R-squared value of 27.7%. I tested the data with other models such as ridge models, adaptive boosting, lasso models, random forests, and gradient boosted regression. My best model turned out to be from using gradient boosted regression that achieved a R-squared value of 42.6% which is still isn't great, but at least it's an improvement from the linear regression model. I introduced random noise into the model so I can throw out the features that aren't important. After running my random forest model several times with the random noise I found out that the most important features to determining the IMDB score were movie facebook likes, director facebook likes, duration, and the budget of the film. THe graphs below show the relationship of the IMDB Score with some of these features.

It's interesting to note that the directors with the highest facebook likes would generally make quality movies.

![alt text]({{ site.baseurl }}/images/Selection_022.png)

Notice that movies with a budget of lower than 200 million dollars would never score higher than a 6.

![alt text]({{ site.baseurl }}/images/Selection_024.png)

The graph below just shows how gross and score were related. It was interesting to see that there weren't any movies that score less than 6 gross more than 300 million. The green line shows this

![alt text]({{ site.baseurl }}/images/Selection_025.png)

I also tried some feature engineering. I made a dummy variable for the MPAA ratings and genres. I also thought that directors who had many movies in their resume would mean that they would consistently produce quality movies. I made a dummy variable if the director of a movie was in the top 5 percent. Another dummy was if the director was in the top 40 percent, but below the top 5 percent and another dummy was for the rest of the directors. However, tafter running the same models with these features there wasn't an improvement. In the end I found out that social media following has some effect on the rating of a movie. I was suprised to see that actors do not affect the quality of a movie, but after thinking about this discovery it made sense. There has been many times where I watched a movie just for the cast, but ended up disappointed because the movie was horrible. Also since the perception of a movie is such a human element it is difficult to accurately predict the quality of a movie. It can look great on paper, but end up being a disaster such as Suicide Squad.



