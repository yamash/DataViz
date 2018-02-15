---
layout: page
title: Pipeline
<!--subtitle: Why you'd want to go on a date with me-->
---
One could go manually over all the patents, but we have nearly 50'000 of them. So we tried to extract topics automatically on patents abstracts and visualize what abstracts of patents were talking about. Our study here involves 25'000 patents (all filled in Switzerland) selected randomly from 1964 to 2013. 
## Natural Language Processing
We have few treatments to apply to our text data  
* Tokenize
* Normalize: put to lower case
* Lemmatize: keep only lemmas
* Filter out stop words
* Filter out some Part of Speech Tags

## Latent Dirchlet Allocation (LDA) for Topic Extraction
We apply a LDA topic extraction alogrithm, seeking for 30 topics. Looking at the *topics per patent* distribution, we see that there are 17 trahs topics. At that point we decided to remove them and also all the patents that were maximized by one of these topics. This reduced our data to 14,194 patents, and 13 topics (there were also some duplicates).

## Supervised Dimension Reduction using Fischer Linear Discriminant Analysis
Now we wanted to visualize this data using a dimension reduction. Considering our task is supervised because we assign the topic that maximizes the *topics per patent* distribution, we can ask a supervised dimension reduction algorithm. That's exactly what Fischer Linear Discriminant Algorithm does. It projects the data into a lower space where the split between classes is maximized.