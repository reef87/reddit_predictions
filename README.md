## Web Scraping for Reddit & Predicting Comments

#### Introduction
In this notebook, we dive into the world of reddit, "The Front Page of the Internet". Using beautiful soup we extract data from the homepage of reddit. By comparing variables such as title, subreddit, or age of the post we attempt to make predictions of the main factors of post virality.

#### Notebook outline
1) Webscraping reddit with BeautifulSoup
2) Cleaning the data and EDA
3) Model Building
4) Conclusion

#### 1) Webscraping reddit with BeautifulSoup
I scraped 2000 posts from the homepage of reddit using the python requests. The Data was scraped in a single day. In order to not be timed out by reddit, A delay was put into effect after every 500 posts were gathered. The raw html was passed through BeautifulSoup. Four functions were defined in order to extract title, comment number, age of post, and subreddit of post. Each of these functions returned a list of lists of their output, so each of these 4 compound lists were converted to a single list using a list comprehension.

#### 2) Cleaning the data and EDA
The decision to gather the data in a single day led to a lot of duplicate posts. The first step was to get rid of the duplicate titles, only keeping posts that were "cross posted" into two seperate subreddits. Next step was to verify we had the correct data types. Number of comments and age of post were converted to numeric. Since our target was number of comments, we engineered a new column based on "high" or "low" comments. This was a binary value based on the median number of comments, anything higher was a 1 and anything lower was 0.

#### 3) Model Building
Our baseline accuracy was 50.3%. Using a random forest classifier model and setting our independent variable as the subreddit, we were able to produce a model that was 10.3% more accurate. Through this model, we were able to see that /rFacepalm was the most important feature in the model, with a coefficient of 0.0245.

#### 4) Conclusion
Much more data needs to be gathered to truely make any claims about a reddit post. The sample size of 2000 (most of which were duplicates) was way too small. I would suggest scraping data over months, perhaps limiting how many pages back you scrape as well. 







