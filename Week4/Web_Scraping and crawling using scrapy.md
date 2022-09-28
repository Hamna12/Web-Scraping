# Python Web-Scraping:

## What is Web Scraping?
The idea of scraping data from website or multiple websites is known as web scraping.

## Which python program is used to scrap data?
Spider is used to scrap data from websites and sends data to json file.

## Web Scraping is also known as web scrapper.

# Robots.txt:
Robots.txt is a text file webmasters create to instruct web robots (typically search engine robots) how to crawl pages on their website.
A robots.txt file tells search engine crawlers which URLs the crawler can access on your site. A robots.txt file contains instructions for bots on which pages they can and cannot access.

# BOT...??
Automate the writing of code and automates some kind of action on the internet or website.

# Let's Start Scraping:

We start scraping from the quotes website.

```python
import scrapy

class QuoteSpider(scrapy.Spider):
      name = "quotes"
      start_urls = [ "http://quotes.toscrape.com/"]
      
      def parse(self, response):
           title = response.css('title').extract()
           yield('titletext': title)
```
  
