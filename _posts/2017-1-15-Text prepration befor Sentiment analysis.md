---
layout: post
title: Text prepration befor Sentiment analysis 
published: true
---


Before starting Sentiment analysis we need to prepare out text data. Following steps need to execute to clean the corpus and prepare it for the further analysis. 

## Removing numbers: 
   Numbers doesn't make any sense in text analysis so we need to remove them from our corpurs before further analysis. 

## Removing Urls and Links: 
   Urls and Links need to be removed from corpus for further analysis. We use regular expression to remove them. 
   
## Removing stopwords:
   Stopwords are words in English that are commonly used in every sentence, but have no analytical significance. Examples are ‘is’, ‘but’, ‘shall’, ‘by’ etc. These words were removed by matching the corpus with the stopwords list in the package.

## Stemming words: 
   In text analysis, stemming is ‘the process of reducing inflected (or sometimes derived) words to their word stem, base or root form—generally a written word form’. Stemming is done to reduce inflectional forms and sometimes derivationally related-forms of a word to a common base form. Many methods exist to stem words in a corpus.

## Suffix-dropping algorithms: 
   The last parts of all the words get truncated. For example, words like ‘programming’, ‘programmer’, ’programmed’, ‘programmable’ can all be stemmed to the root ‘program’. On the other hand, ‘rescuing’, ‘rescue’, ‘rescued’ are stemmed to form ‘rescu’, which is not a word or a root.

## Lemmatisation algorithms:
  Each word is the determination of the lemma for a word in the corpus. This is done with the understanding of the context, part of speech and the lexicon for the language. For example, ‘better’ is related to ‘good’, ‘running’ is related to ‘walk’ and so on.
  
  

