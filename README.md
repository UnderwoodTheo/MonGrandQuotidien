
# Mon Grand Quotidien

News summary in French.

## Project explanation

The aim of this project was to scrape two or more sites and link the data together to study them.
We decided to work on a daily newspaper summarizing the french news. 

To do so first scraped data from Twitter and retrieved the first 10 trends. 
After that we were able to do research on Google News.

For each Twitter trend we downloaded the source page including the first 10 articles. 
We did it like this because the scraping time is long that Google News would refresh and the articles would change.

To select the best article among the 10 we established a based-readability ranking with 5 features:
- LIX
- RIX
- Flesch Reading Ease
- Flesch-Kincaid Grade Level
- Gunning Fog Index
These are measures evaluating the readability of a text based on the word and syllable length.
The readability scale is based on the American school system: the lower the value, the easier the text is to understand, except for the Flesch Reading Ease formula.

Each article is ranked among the others for each measure. 
We finally average the 5 ranks and we keep the article having the smallest value.

From there we scraped information for the best articles, namely their title, newspaper, link, picture and we summarize them.
We also added a special feature: the neutrality of the article. 
To do so we processed sentiment analysis on the text.

Finally we've created the structure of the HTML file and we generate it in the form of *MonGrandQuotidien_YYYY-MM-DD*.
## Authors

- [@Theo Underwood](https://github.com/UnderwoodTheo)

- [@Benjamin Toubiana](https://github.com/Btoubiana)
## Installation


First download the [requirements file](https://github.com/UnderwoodTheo/MonGrandQuotidien/blob/main/requirements.txt) file and run this command in your environment.

```shell
  pip install -r requirements.txt
```
    
Then download the [Jupyter Notebook file](https://github.com/UnderwoodTheo/MonGrandQuotidien/blob/main/project.ipynb) and run each cell.
Be sure the cells have output, if not run them again.
## Daily Newspaper


[Here is the daily from January 19, 2023](https://github.com/UnderwoodTheo/MonGrandQuotidien/blob/main/MonGrandQuotidien_2023-01-20.html)

You can download and open it to preview to have a preview of the rendering.

## Usage

![App Screenshot](https://raw.githubusercontent.com/UnderwoodTheo/MonGrandQuotidien/main/daily-usage.PNG)

Here is a preview of the daily consisting of several articles. Each article includes:
- a picture 
- the trend from which it comes
- its neutrality
- its title and link
- a summary



## Tech Stack

**Development:** Python

**Scraping:** Selenium, BeautifulSoup

**Render:** HTML, jinja

