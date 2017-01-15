---
layout: post
title: Text prepration befor Sentiment analysis 
published: true
---


Before starting Sentiment analysis we need to prepare out text data. Following steps need to execute to clean the corpus and prepare it for the further analysis. 

### Removing numbers:
Numbers doesn't make any sense in text analysis so we need to remove them from our corpurs before further analysis. 

### Removing Urls and Links:
Urls and Links need to be removed from corpus for further analysis. We use regular expression to remove them. 
   
### Removing stopwords:
Stopwords are words in English that are commonly used in every sentence, but have no analytical significance. Examples are ‘is’, ‘but’, ‘shall’, ‘by’ etc. These words were removed by matching the corpus with the stopwords list in the package.

### Stemming words: 
In text analysis, stemming is ‘the process of reducing inflected (or sometimes derived) words to their word stem, base or root form—generally a written word form’. Stemming is done to reduce inflectional forms and sometimes derivationally related-forms of a word to a common base form. Many methods exist to stem words in a corpus.

### Suffix-dropping algorithms:
The last parts of all the words get truncated. For example, words like ‘programming’, ‘programmer’, ’programmed’, ‘programmable’ can all be stemmed to the root ‘program’. On the other hand, ‘rescuing’, ‘rescue’, ‘rescued’ are stemmed to form ‘rescu’, which is not a word or a root.

### Lemmatisation algorithms:
Each word is the determination of the lemma for a word in the corpus. This is done with the understanding of the context, part of speech and the lexicon for the language. For example, ‘better’ is related to ‘good’, ‘running’ is related to ‘walk’ and so on.
  
### n-gram analysis:
Each word is broken into a part of its whole by ‘n’ characters, and the one that makes most sense is retained. For example, for n=1 (unigram), the letters ‘f’, ’l’, ’o’, ’o’, ’d’ are individually parsed from ‘flood’. For a higher n (say n=5), ‘flood’ is retained from ‘flooding’, although at n=4, ‘ding’ can also be construed as a word.

### Removing punctuation:
Punctuation marks make no impact to the analysis of text and are hence removed.

### Stripping whitespace:
Words that have extra whitespaces at the beginning, middle or end are subjected to a regular expression that removes the whitespace and retains only the words themselves.

### Checking for impure characters:
A check on the corpus after the modifications made thus far revealed that some URLs were left behind, due to the removal of whitespaces, numbers and punctuations. Regular expressions were used to remove them.
   
   When we have a lot of data than it becomes challenging to make meaningful interpretations from the huge volumes of data that need to be processed.One solution is to cluster similar data together after performing the necessary EDA operations that it becomes easier to manage the flow of information.
   
## Hierarchical Clustering
Hierarchical clustering attempts to build different levels of clusters. Strategies for hierarchical clustering fall into two types.

### Agglomerative:
where we start out with each document in its own cluster. The algorithm iteratively merges documents or clusters that are closest to each other until the entire corpus forms a single cluster. Each merge happens at a different (increasing) distance.

### Divisive:
where we start out with the entire set of documents in a single cluster. At each step the algorithm splits the cluster recursively until each document is in its own cluster. This is basically the inverse of an agglomerative strategy.

The results of hierarchical clustering are usually presented in a dendrogram.The following steps explain hierarchical clustering in simple terms:

1. Assign each document to its own (single member) cluster

2. Find the pair of clusters that are closest to each other and merge them, leaving us with one less cluster

3. Compute distances between the new cluster and each of the old clusters

4. Repeat steps 2 and 3 until you have a single cluster containing all documents


The dendrogram output is to be interpreted as follows:

1. Farther the nodes, greater is the dissimilarity and more robust is that

2. The closer the node, the weaker is the

3. The height of each node in the plot is proportional to the value of the intergroup dissimilarity between its two


#### K-Means Clustering:
As opposed hierarchical clustering, where one does not arrive at the number of clusters until after the dendrogram, in K-means, the number of clusters is decided beforehand. The algorithm then generates k document clusters in a way that ensures the within-cluster distances from each  cluster member to the centroid (or geometric mean) of the cluster is minimized.

A simplified description of the algorithm is as follows:

Assign the documents randomly to k bins

Compute the location of the centroid of each

Compute the distance between each document and each centroid

Assign each document to the bin corresponding to the centroid closest to

Stop if no document is moved to a new bin, else go to step

3.2.1 Choosing k

The most significant factor of employing k-means clustering is choosing the no. of clusters, ‘k’. The ‘elbow method’, wherein the SUM of Squared Error (SSE, the sum of the squared distance between each member of the cluster and its centroid) decreases abruptly at that value that is theoretically the optimal value of k, is widely applied to arrive at k.

When k is plotted against the SSE, it will be seen that the error decreases as k gets larger; this is because when the number of clusters increases, they become smaller, and hence the distortion is also smaller.

23

Here, the optimal value for k is shown to be 3, as that is where the SSE decreases abruptly. With k=3, the matrix of tweets was clustered using k-means.

24

The plot clearly shows that there is only marginal dissimilarity with a corpus at 98% sparsity. This is evident from the top 10 words in each of the three clusters.

cluster 1: rain need status flood helplin number contact stay safe atus
cluster 2: food need contact avail peopl near water area call status 
cluster 3: peopl safe stay flood rain need near road contact media

With respect to clustering, subject matter and corpus knowledge is the best way to understand cluster themes. With the insights gleaned thus far, it is reasonable to assume the following:

Cluster 1 contains news updates and cautionary

Cluster 2 contains messages about requests for help and volunteers

Cluster 3 contains messages about area-specific updates and some cautionary

3.3 Topic Modeling

Another technique that is employed to deduce the themes of text is topic modeling.

A topic model is a type of statistical model for discovering the abstract “topics” that occur in a collection of documents (tweets in this case). Intuitively, given that a document is about a particular topic, one would expect particular words to appear in the document more or less frequently: in this case, ‘help’ is quite common to almost every tweet.

A document typically concerns multiple topics in different proportions; thus, in a document that is 10% about subject A and 90% about subject B, there would probably be about 9 times more words about ‘B’ than words about ‘A’ (Wikipedia, n.d.).

Topic modeling has implementations in various algorithms, but the most common algorithm in use is Latent Dirichlet Allocation (LDA).

3.3.1 Latent Dirichlet Allocation

Latent Dirichlet Allocation (LDA) is a statistical model that allows sets of observations to be explained by unobserved groups that explain why some parts of the data are similar. For example, if observations are words collected into documents, it posits that each document is a mixture of a small number of topics and that each word’s creation is attributable to one of the document’s topics.

LDA allows the possibility of a document to arise from a combination of topics. For example, the following tweet may be classified as (say) 90% information & 10% sympathy/hope.

25

LDA was performed with an objective to discover 6 topics. The output gives us following set of words for each topic.

q1

Topics 1 & 3 are quite similar; this is in agreement with the results of the K-means exercise.

26

This plot graphs the probability associated with the top 100 words for each topic, sorted from most to least likely. Here too, the lines almost overlap, indicating the content similarity in the tweets.

27

 

4. Conclusion

It is clear that the general sentiment across the tweets render the tweets quite similar. It has been demonstrated that crucial information like the worst-hit areas can be identified by analyzing tweets and performing basic text analytics.

It is clear that the power of social media can be harnessed to great effect in times of crisis. This has not escaped Twitter’s notice; they have initiated the practice of creating hashtags specific to individual crises to index tweets easily. Facebook launches ‘Mark Safe’ feature to those who have listed a crisis-hit location as their place of residence.

The government agencies, NDRF and other relief agencies would do well to develop analytics capabilities focused on mining Twitter for real-time, tangible updates to take meaningful action.

4.1   Limitations of this study

 The study considers only 6000 tweets of the whole set of tweets that would have been sent on the subject.

The study also did not consider captions of pictures, news reports, and other social media reports which could have generated additional insights.

There exist other topic models and black box techniques for similar analysis that have a record of better performance. These have not been performed as they are beyond the scope of this exercise.

4.2   Challenges to Real-Time Analysis of Tweets

The following points highlight a few challenges that will be faced by any researcher trying to solve the same problem.

Retweets contain information that many users find relevant. The subjectivity of this relevance to the crisis at hand is difficult, if not impossible to measure.

This problem is compounded if the tweets contain no hashtags. In the dataset generated for this analysis, 1399 tweets (22%) had no hashtags. These tweets may also be highly relevant to the crisis but may be missed due to the lack of hashtags.

Twitter has a 140 character-limit on all tweets (not including pictures and videos). This leads users to truncate or shorten words to forms that is easily interpretable to humans, but is challenging for a machine. Eg: ‘afcted ppl’ is easily understandable to mean ‘affected people’ for a human, but not for a program. One way to solve this problem is to maintain a dictionary of such terms and match them in real-time.

4.3   Applications & Scope for Further Work

As mentioned in the introductory chapter, this is an active field. The power of social media will continue to be researched and newer applications will continue to be built to harness its  power.

One area is quashing rumors. During the Chennai floods, quite a number of false ‘news reports’ and ‘alerts’ circulated on Facebook, Twitter and the mobile messaging application WhatsApp. Machine learning can be employed to check the veracity of social media by comparing contents from actual news reports and

During the 2011 Australia floods, the civic authorities were among the most prolific users of Twitter in disseminating safety tips, general information and coordinating volunteer relief work. Every civic authority would do well to develop a framework and system to manage crises also through social media. This covers all disasters, both natural (earthquakes, floods, hurricanes) and man-made (terror strikes, shootouts).

Media outlets and government agencies can work together in planning for incidents that are expected by creating distinct identifiers and hashtags for each scenario and making the public aware of the

Disasters may strike at any time. While it may not be possible to prevent them, it is prudent to be prepared for unfortunate eventualities. Having a dedicated social network analysis platform to analyze information in real-time will definitely aid in this endeavor.

 

Our learning & journey

We came to Great Lakes PGPBABI with very little knowledge about analytics a year ago. While this capstone project is just the starting of our career, we feel proud of our first project and the amount of learning it brought to us.

Here is what our mentor, Mr. Jatinder Bedi, had to say about our Capstone Project success,” Great Lakes group approached me with a conventional topic in hand for which they already had the data. It was a movie data, which they wanted to analyze to build a movie recommendation engine. We had a choice of doing this conventional project or picking some challenging topic which would help us apply the new concepts learnt in a Great Lakes Business Analytics program. As it was a Chennai group, so I suggested them a topic “Tapping Social Media Exchanges on Twitter: A Case-Study of the 2015 Chennai Floods” with which they can relate well as it was more aligned to recent floods in Chennai. As I shared the topic, students got excited & everybody said yes. The idea was to build something from scratch and this was our chance to showcase our skills. Dr PKV, also liked the idea and gave us a go-ahead. I would say this project was a great success. Lastly, I feel very proud to be a mentor of this great project. Special thanks to Dr. PKV for his support and guidance.”

 

Also, Dr. P.K Viswanathan, Program Director – PGPBABI (Chennai) and Professor, remarked, “The Capstone Project titled Tapping Social Media Exchanges on Twitter: A Case-Study of the 2015 Chennai Floods undertaken by the BABI participants of Batch 3 is a great revelation to me in terms of innovation in approach to the entire concept of an Analytic Study. Typically, students think that analysis and modeling using quantitative data is the key to success in any Business Analytics Project. This study completely deviates from the orthodox path, yet rich in a very substantive manner what analytics could do in the ambit of Natural Language Processing(NLP) of social media messages in the form of tweets leading to actionable insights on a real time basis. 

Cohesive Themes, Cogent Presentation, Mining using Advanced Analytic Modeling, and Excellent Insights that can be leveraged by policy makers in Government are the hallmarks of this project. It was rated by the evaluation committee headed by me as the top ranking project among the many studies that were presented. 

I congratulate the team comprising Anandhi Venkat, Ashvin Kumar Elangovan, Vignesh Kumar and Vijay Somanath and the mentor Jatinder Bedi for this outstanding study. I also take this opportunity to  wish them all for many such original works.”
