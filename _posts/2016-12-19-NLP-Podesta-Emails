---
layout: single
title: Analyzing Wikileaks using Unsupervised Learning Methods
---
This election will be one of the most memorable events in US history because of the controversies behind both candidates. 
On one side we have a candidate with no political experience and have made ridiculous statements.
One the other side we have a candidate whose entire political career is plagued by scandals. Wikileaks, a multi-national
media organization has been making headlines recently because of their leaks of John Podesta's emails who is Hillary
Clinton's campaign manager. Starting in October wikileaks has been releasing thousands of emails everyday that 
belonged to John Podesta. It was through these emails that we found out many shocking stories of corruption and deceit.
As a result, this sparked my interest so I decided to analyze these emails using a machine learning approach specifically
by using unsupervised learning methods.

My first step was to scrape the emails from Wikileaks. The amount of emails I collected were 50,887 emails. However,
a decent amount of the emails were copies of each other due to long chains of replys in the email network. After deleting all of the copies
I ended up with around 36000 emails. I mainly used Latent Dirichlet Allocation (LDA) to topic model the emails. The LDA 
is a neat algorithm is an unsupervised learning method that represents documents as mixtures of topics that spits out words 
with certain probablities. It basically breaks a text into groups of words or topics. For example, let's say we are analyzing 
a corpus about animals. The cat topic will return words such as meow, kitten, milk, kitty, and other words that are associated 
with this topic. However, unlike kmeans clustering where the results are disjoint topics with LDA a document can be a mixture of topics. For example,
 lets say document A talks about backpacking Europe to sightsee and try out all the different cuisines. A kemans clustering approach would 
 maybe picking up either sightseeing Europe or trying different cuisines. On the other hand, LDA assigns a document to a 
 mixture of topics. Therefore each document is characterized by one or more topics. So document A would be belong 50% to sightseeing 
 Europe and 50% to trying all the different cuisines Europe has to offer. 
 
 In order to generalize for all the emails I coded my model so that the LDA algorithm will return the 20 most important topics 
 discussed in the emails. Some of the topics were things you would expect from an email network such as linkedin invitations and gogole 
 calendar notifications. The more interested topics included the supreme courts stance on gun ownership and healthcare,
  Bernie Sanders, Iowa, climate change, trade, budget, clinton foundation, and of course Donald Trump. I was surprised that no 
  controversial topics came out of the model. This may be because these controversial conversations are mentioned in the emails briefly. In the end the topics returned are things that you 
  expect from a presidential campaign. 
  
  POST IS UNFINISHED WILL FINISH TOMORROW!!!
