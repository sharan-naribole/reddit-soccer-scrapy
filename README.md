#Soccer Team Popularity on Reddit

## Introduction

Reddit includes a subreddit for soccer content entries [/r/soccer](https://www.reddit.com/r/soccer/), comprising of an enormous community of over 500,000 subscribers. Hundreds of submissions (posts) are voted based on their content and discussed on a daily basis. The common submissions include live goals, news articles and pre-, live and post-match analysis. Many a time /r/soccer is where I vent my frustration whenever Manchester United suffers defeat!  The anonymity of Reddit provides a powerful tool for users to express their opinions about the clubs they support and also the clubs they don't like. This unique feature provides a mechanism to prevent the building of echo chambers in the discussions.

/r/soccer also provides each subscriber the feature to select a "flair" which is the team crest (team logo) of the club/country the user supports. A miniature team logo is displayed beside the username in their posts and comments. This gives other readers context and insight into the user's thinking and adds another interesting dimension to the conversations that take place. Although one can observe the flairs for each users, Reddit does not provide the flair distribution across the whole of /r/soccer. In this project, my objective is to scrape and analyze the flair distribution across the top posts in /r/soccer and this distribution's relationship with comments activity, submission score and submission type. 

## Instructions

```python
scrapy crawl flairs -o reddit_data.csv

python processing.py

python analysis.py
```

## Data Collection

### Objective

For each submission on /r/soccer, my goal is to collect the following features:

- Submission Title: to decipher the type of submission for e.g., goal video, news article, live match discussion etc.

- Submission Score (~= Upvotes - Downvotes): indicates the quality of the submission

- Number of comments: indicates the user activity on the submission

- Per-user flair map: dictionary of unique username and user flair  in the top 500 comments. This will be utilized for the flair distribution analysis.

### Tools

- [Scrapy Python framework] (https://github.com/sharan-naribole/reddit-soccer-scrapy/blob/master/flairs/flairs/spiders/rsoccer_flairs.py) 

- [SelectorGadget Chrome extension] (http://selectorgadget.com/)  

## Data Processing

The goal of data processing is to compute the following metrics for each submission:

- Flair diversity: the unique number of flairs

- Percentage share per flair: The percentage of comments belonging to a given flair. This metric is computed for every team both club and country flairs for e.g. England, Real Madrid, Brazil etc.

- Top Percentage share: The highest percentage value among all flairs

- Number of comments

### Tools

- pandas

- matplotlib  

## Files

- [processing.py](https://github.com/sharan-naribole/reddit-soccer-scrapy/blob/master/processing.py) converts the scraped data to corresponding data frames. 

- [analysis.py](https://github.com/sharan-naribole/reddit-soccer-scrapy/blob/master/analysis.py) creates the plot visualisations using processed data.

## Blog Post

Please read my [blog post](http://blog.nycdatascience.com/student-works/soccer-team-popularity-reddit/) for more detailed discussion

## License

Open sourced under the [MIT License](LICENSE.md).
