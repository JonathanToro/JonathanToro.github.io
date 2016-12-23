---
layout: single
title: Analyzing Wikileaks using Unsupervised Learning Methods
author_profile: true
read_time: true
comments: true
share: true
---
This election will be one of the most memorable events in US history because of the controversies behind both candidates. On one side we have a candidate with no political experience with an unorthodox background. On the other side we have a candidate whose entire political career is plagued by scandals. Wikileaks, a controversial multi-national media organization, has been making headlines recently because of their leaks of John Podesta's emails who's Hillary Clinton's campaign manager. Starting in October and ending on election day Wikileaks has been releasing thousands of emails daily that belonged to John Podesta. It was through these emails that we found out about many shocking stories of corruption and deceit from the Clinton family enterprise. This sparked my interest so I decided to analyze these emails using a machine learning approach specifically by using unsupervised learning methods.

My first step was to scrape the emails from Wikileaks. The total number of emails I collected were 50,887 emails. However, a decent amount of the emails were copies of each other due to long chains of replies in the email network. I ended up with around 36000 emails after deleting all of the copies. There are many unsupervised learning methods that could've been used to topic model these emails such as Kmeans clustering and Latent Dirichlet Allocation (LDA). I decided to use LDA to topic model the emails because the output can give more realistic results for topic assignment. With LDA a document can be a mixture of topics which is unlike kmeans where the results are disjoint. For example, lets say a document talks about backpacking Europe to sightsee and try out all the different cuisines. A kmeans clustering approach would pick up either sightseeing Europe or trying different cuisines. On the other hand, LDA assigns a document to a mixture of topics. Therefore, each document is characterized by one or more topics. So this document would be assigned 50% to sightseeing Europe and 50% to trying all the different cuisines Europe has to offer. 

It's important to mention that the output of a LDA model returns words associated to a topic. For example, let's say there's a corpus talking about animals. The cat topic would return words such as meow, purr, and feline. The dog topic would return words such woof, bone, compassionate, and playful. In order to generalize for all the emails, I coded my model so that the LDA algorithm will return only 20 topics. Some of the topics were things you would expect from an email network such as linkedin invitations, google calendar notifications, and promotional emails from retail companies. The more interesting topics included:

1. Supreme Court cases regarding gun law, women's rights, and healthcare
2. Discussions about the democratic primary race against Bernie Sanders
3. The elections in Iowa which is the first state to vote for in the primaries
4. Donations to the Clinton Foundation and campaign
5. Discussions about energy and climate
6. Discussions about college education
7. Discussions about Cuba
8. One topic returned the words: Iran, War, Israel, Foundation. (This was an interesting, but alarming output)
9. Cheryl Mills' role in the campaign and possibly in the controversial FBI email investigation
10. A topic that returned the words: tax, trade, rate, budget, proposal, bank, and jobs so I'm assuming it's about the economy although it's unclear.
11. The presidential race against Donald Trump

We can see that some of these topics are conversations you would expect from a presidential campaign such as the economy, climate, energy, and law. One of the controversial topics that the model returned is the eighth one listed above. However, it is important to note that LDA is often prone to creating topics that are not easily interpretable by humans so some of my interpretations could be wrong. The picture below shows the words belonging to each topic. You can look for yourself and interpret my results.

![alt text]({{ site.baseurl }}/images/Selection_047.png)

I created some visualizations of John Podesta's email network. These graphs were made by using gephi. The graph below shows all the emails sent and recieved in my data. Each node is a different email with John Podesta's being the central node.

![alt text]({{ site.baseurl }}/images/Selection_049.png)

In order to better visualize the network, I only included the top 100 email addresses that recieved the most activity in the network. The size of the node is relative to how much activity an email address has received.

![alt text]({{ site.baseurl }}/images/top_people2-1.png)
