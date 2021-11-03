# Rich-Context-Classification
Backgrond
# Ongoing kaggle competition 
# Started by a non-profit organisation Coleridge Initiative
# Work with Federal Government to ensure data is used for public decision making
# Improve the use of data and evidence for public good
# Here, as a beginner to NLP, we tried to approach the topic with NER and BERT

Problem Statement
# The objective of this project is to find the mention of datasets within scientific publications.

Objective
# Find what datasets are in the publications
# To understand how the dataset is being used in these publications and the excerpts relating to those datasets
# To find links between the words used in the research articles and the data referenced in the articles.
# Data source: https://www.kaggle.com/c/coleridgeinitiative-show-us-the-data

Dataset Structure
# train - the full text of the training set's publications in JSON format, broken into multiple section titles  (~14300 files)
# test - the full text of the test set's publications in JSON format, broken into multiple section titles
# train.csv - labels of articles and data for the training set
# sample_submission.csv - a sample submission file in the correct format

Dataset Handling
# Use “GLOB” to read all the JSON file names
# Convert all content under multiple section titles to dataframe and group into single pub_id

Bert QnA
# A transformers model pre-trained on large corpus data
# Pre-trained and fine-tuned for question answering based on SQUAD benchmark
# 12 or 24 transformer layers
# Uses segment embeddings to differentiate question and reference text

BERT Masked Language Modelling
# MLM is the task of masking tokens in a sequence with a masking token and prompting the model to fill that mask with an appropriate token


NER Model Building using Spacy Package
# Using Spacy,create blank English language class and get the spacy pipe names
# Using all the entities in the training dataset that we obtained in preprocessing in which we labeled as “dataset” and add to the spacy pipe_name
# Perform multiple iterations with random shuffle
# Each iteration,update the predicted strings with nlp.update
# Parameters include the text preprocessed, drop = 0.3, losses, SGD as optimizer)

Overall result

Bert Q&A F-score - 0.07
Bert MLM F-score - 0.11
* NER Using Spacy F-score - 0.55





