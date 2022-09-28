# Tool for Scrapping Complex Websites:

If you want to extract data from the websites and that website is too complex then we can use tool to find the particular CSS selector .

# How to get tool...??

Just go to google and search for the SELECTOR GADGET CHROME, this is chrome extension and then we added to our chrome.

## How this Extension works??

After adding this extension to chrome then go to the website from which you want to extract the data. Like if you want to select only Author's Name from the 
website(Quotes.com) then select the extension and click on Author's name and the selected author name colored green and other's authors names in the whole page 
returns to yellow color. It means all authors names selected at once.

# Let's Scrap data

```python
import scrapy

from ..items import QuotetutorialItem

class QuoteSpider(scrapy.Spider):
    name = "quotes"
    start_urls = [
        "http://quotes.toscrape.com/"
    ]

    def parse(self, response):
        items = QuotetutorialItem()
        all_div_quotes = response.css('div.quote')

        for quotes in all_div_quotes:
            title = quotes.css('span.text::text').extract()
            author = quotes.css('.author::text').extract()
            tag = quotes.css('.tag::text').extract()
            
            items['title'] = title
            items['author'] = author
            items['tag'] = tag
            yield items
   ```
