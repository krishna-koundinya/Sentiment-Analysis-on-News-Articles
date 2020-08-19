# Sentiment-Analysis-on-News-Articles
## 1. Introduction
This notebook collects news articles from various publishers using the [News API](https://newsapi.org/) and performs sentiment analysis on each article using [IBM Watson Natural Language Understanding API](https://cloud.ibm.com/apidocs/natural-language-understanding?code=python#introduction).  
The output is a csv file which holds the following columns:  
**source-id, source-name, author, title, description, content, sentiment-of-content, emotion-of-content, published_date**  

## 2. Prerequisites
You will need the ibm-watson Python package, besides other well known packages to run this notebook.
### pip Installation
```
pip install --upgrade "ibm-watson>=4.5.0"
```
https://github.com/watson-developer-cloud/python-sdk
### Anaconda Installation
```
conda install -c conda-forge ibm-watson
```
## 3. About the notebook
### Getting the publishers
[News API](https://newsapi.org/) has news articles from various sources i.e. publishers.
The names and ids of these sources is collected to let the user select upto 20 sources, using multiple checkboxes.
### Querying
After selecting the sources of publications, the user can start querying for desired articles.  
The user can enter the keywords which should definitely occur in the article and also enter the keywords which should not occur in the article.  
Besides this, the user can also enter keywords which should occur in the title of the article.
### Getting the articles
Using the user input the [News API](https://newsapi.org/) is queried.  
Upto 100 hundred articles not more than a month old are collected. (Use of community edition of [News API](https://newsapi.org/) prevents extraction of further results.)
### Performing Sentiment Analysis
The [IBM Watson Natural Language Understanding API](https://cloud.ibm.com/apidocs/natural-language-understanding?code=python#introduction) lets us perform sentiment analysis on a piece of text. Using the content of the article as text we call the extract the sentiment of the article from this API.  
The [IBM Watson Natural Language Understanding API](https://cloud.ibm.com/apidocs/natural-language-understanding?code=python#introduction) also annotates the text with different emotions and their respective scores. The higher the score the more intense the emotion.
## 4. Summary
All the aforementioned data is collected and stored in a csv file.
