---
layout: post
title: Optimizing staff allocation to produce the greatest exposure to target demographic
---

For my first data science project I analyzed the MTA turnstile data that is provided on <http://web.mta.info/developers/turnstile.html>. We were given a hypothetical scenario where an organziation called WomenTechWomenYes (WTWY) is seeking advice to find interested individuals to participate in their gala and to raise awareness for their cause. This organization wanted to deploy their teams at the entrances of subway stations. These teams would then collect email addresses to people who were interested and send them free tickets to their gala. WTWY was having trouble deciding where to deploy their street teams because of the enormous size of the MTA transit system so my job was to explore the data available online to give them recommendations of how WTWY can optimize their limited resources.

My first assumption was that the street teams would have to most exposure at train stations where there is the most traffic of people. However, the people of New York is known to be extremely diverse where you can find virtually every personality that you can think of so I took the demographics around the train stations into account. Therefore, there were two parts of my analysis. One was to see the total traffic of each station and another was to analyze the demographics around each station. 

My group decided to analyze all the data that was provided on the MTA website which ranged from May 2010 to September 2016. However, we chose to only focus on the months leading up to the gala which was in June so we decided to only look at April, May, and June of each year. Cleaning the data was extremely difficult because it was extremely messy. I did not expect to encounter this much difficulty in doing so. I now know why most data scientists say that they usually spend 80 percent of their time cleaning their data. I learned a great deal on how to clean data from struggling with this data set. I also have to give thanks to Dave, Megha, and Yao who were all in my group. The picture below shows a bar graph of the stations with the most traffic from March until June. Notice that these are the major train stations of the city where commuters from the Greater New York area enter the city. 

![alt text]({{ site.baseurl }}/images/traffic_by_month.png)

After finding this out we decided to analyze what time of day were the stations seeing the most traffic. My hypothesis was that these stations were busy during the commuting hours. The following graph confirmed my hypothesis.

![alt text]({{ site.baseurl }}/images/traffic_by_hour.png)

We looked at the demographics of NYC by zip code after finding out where and when the most traffic of people occured. We decided that the people that are most likely to be interested in attending the gala fall under these categories: females, high income, and employed in the tech industry. We pulled data from the Census and OpenSecrets.org to see where there is a high concentration of people with these traits. The graph below shows the zip codes of people who are most likely to attend the gala with the clearest color being the highest concentration.

![alt text]({{ site.baseurl }}/images/demographic.png)

Finally after looking at both graphs we were able conclude where to deploy WTWY's staff. The 5 stations are 14th Street Union Square, 59th Street lines 456QNR, 72nd Street lines 123, 66th Street Lincoln Square, and 49th Street - 7th Ave. These recommendations were generated after taking traffic and demographics into consideration. 
