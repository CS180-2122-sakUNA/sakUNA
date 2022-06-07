# sakUNA

sakUNA is an application that maps out areas experiencing disasters with the purpose of providing disaster response and recovery efficiently based on tweets gathered in Twitter.

This project is developed by: 

- I.G. Castro (THV)
- J.N. Manalili (THX)
- G.L. dela pena (THX)

Due to the geographical location of the Philippines, the country experiences many natural disasters such as typhoons, earthquakes, volcanic eruptions, landslides, etc. With a World Risk Index Score of 26.70% last 2016 [5], the Philippines remain as one of the countries most affected by natural disasters. Hence, immediate attention is needed especially because natural disasters are getting even more destructive due to climate change [6]. To help in mitigating the effects of natural disasters or enhancing disaster risk management, implementing disaster response maps using Twitter data can be helpful in planning an efficient response [4].

## Methodology

In creating the dataset, the twitter module from the snscrape Python library was used along with itertools to collect the specified tweets filtered according to location, date created, and presence of appropriate keywords.


In data processing, the tweets were then be manually assigned to different ranks for the purpose of training the classification model.  These ranks are: 0 - Safe, 1 - Needs Help, 2 - Needs Immediate Help.  CountVectorizer was used to allow transformation of tweets into vectors based on the frequency of unigram and bigram words present in all tweets. To counter the class imbalances, the Synthetic Minority Oversampling Technique (SMOTE) was also used.

The models used were Logistic Regression and Gradient Boosting. It was found that Logistic Regression with SMOTE gives the best performance according to the performance metrics used. All of which are available using sci-kit learn.

Using folium, the geographical heatmap was created. The map shows points with predicted tweets having rank 2.
