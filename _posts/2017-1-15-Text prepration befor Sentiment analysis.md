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
As opposed hierarchical clustering, where one does not arrive at the number of clusters until after the dendrogram, in K-means, the number of clusters is decided beforehand. The algorithm then generates k document clusters in a way that ensures the within-cluster distances from each  cluster member to the centroid (or geometric mean) of the cluster is minimized.A simplified description of the algorithm is as follows:

1. Assign the documents randomly to k bins

2. Compute the location of the centroid of each

3. Compute the distance between each document and each centroid

4. Assign each document to the bin corresponding to the centroid closest to

5. Stop if no document is moved to a new bin, else repeat

##### Choosing k
The most significant factor of employing k-means clustering is choosing the no. of clusters, ‘k’. The ‘elbow method’, wherein the SUM of Squared Error (SSE, the sum of the squared distance between each member of the cluster and its centroid) decreases abruptly at that value that is theoretically the optimal value of k, is widely applied to arrive at k, When k is plotted against the SSE, it will be seen that the error decreases as k gets larger; this is because when the number of clusters increases, they become smaller, and hence the distortion is also smaller.Here, the optimal value for k is shown to be 3, as that is where the SSE decreases abruptly. With k=3, the matrix of tweets was clustered using k-means.

With respect to clustering, subject matter and corpus knowledge is the best way to understand cluster themes. With the insights gleaned thus far, it is reasonable to assume the following:

#### Topic Modeling
Another technique that is employed to deduce the themes of text is topic modeling.

A topic model is a type of statistical model for discovering the abstract “topics” that occur in a collection of documents. Intuitively, given that a document is about a particular topic, one would expect particular words to appear in the document more or less frequently.
A document typically concerns multiple topics in different proportions; thus, in a document that is 10% about subject A and 90% about subject B, there would probably be about 9 times more words about ‘B’ than words about ‘A’.

Topic modeling has implementations in various algorithms, but the most common algorithm in use is Latent Dirichlet Allocation (LDA).

#### Latent Dirichlet Allocation
Latent Dirichlet Allocation (LDA) is a statistical model that allows sets of observations to be explained by unobserved groups that explain why some parts of the data are similar. For example, if observations are words collected into documents, it posits that each document is a mixture of a small number of topics and that each word’s creation is attributable to one of the document’s topics.

