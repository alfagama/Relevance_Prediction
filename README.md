# Relevance_Prediction

## 1. INTRODUCTION

The area of text analytics (or text mining) includes techniques from multitude scientific areas (A.I., statistics,
linguistics), and it has a wide range of applications (security, marketing, information retrieval, opinion
mining). While structured data are “ready” for analysis and evaluation, unstructured text requires
transformation in order to uncover the underlying information. The transformation of unstructured text into a
structured set of data is not a straight forward task and text analytics offers a wide variety of tools to tackle
with the idioms, ambiguities and irregularities of natural language.

In this project, we will tackle a problem that involves text analysis and feature extraction from text. The
particular task is focused on predicting the quality results of a query at the site of Home Depot. Past queries
from users were evaluated on their quality from the users themselves. Thus, for each query we will have
search query, the result product and the evaluation of that query (with values in the range 0-3). We are going
to utilize Apache Spark, in order to parallelize the work, cleaning the data and extracting useful features from
them.

## 2. TASK OVERVIEW

You are given the following data:
1. train.csv : our training data. It contains the query terms, the query relevance (quality) and the title of
the product corresponding to the result of that query.
2. product_descriptions.csv: It contains full text description of the products that are found in train.csv.
3, attributes.csv : It contains additional information about the aforementioned products in the form of
product id, name of an attribute, value of that attribute.

You will work in two different flavors of the problem. In most of the cases, the unsupervised case is the most
challenging since there is no ground truth information to use.

Supervised case: the file train.csv contains the ground truth information. You need to build a model to be
able to predict the relevance. For simplicity we assume that 60% of the data will be used for training and
40% for testing. The metric to use for the evaluation is the Mean Squared Error (MSE).

Unsupervised case: in this case you simply assume that the relevance information does not exist. We assume
that any relevance score less than 1.5 is considered as 0 and any score equal or larger than 1.5 is considered
as 1. Then, you need to work only with the queries and the results in order to predict correctly if the result is
relevant to the query or not. In this case, you are not allowed to build a model since we assume that you do
not have access to ground truth information. The evaluation metric in this case is the average F1 score.
