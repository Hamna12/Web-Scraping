# How to Automate Bunch of things Using Python:

# What is Python Automation:
Python is often used in workplaces to automate and schedule the sending/receiving of emails and texts.

* Python packages – email, smtplib, are used for sending emails using just Python.
* We can turn a time-consuming task into an automated/scheduled task.

Emails and texts are usually automated or scheduled, among other tasks within a team, to focus on further development tasks. This increases productivity and encourages better time management in a group.

# We will Automate:
* Web Scraping
* Automating downloads
* Extracting From Pdfs
* Automated Image Processing
* Building an Automated news summarizer

# Hacker News Headline Email:

* Introduction to web scraping
* Setting Up the Enviroment
* Project Architecture Overview
* Building the Hacker News Scraper
* Sending Email From Python
* Building the Headline Email Module

# Project Architecture:

This architecture starts with the content of hacker news website front page
To get content of website:

* GET HN website front page
* Scrape Required content (Title/link)
* Build Email Body/ content
* Email Authentication
* Email Sent

# Packages that will used in this project:

* request ( this package is used for http request)
* bs4  (this is used for web scrapping)
* smtplib (default) (This is used for Email Authentication)
* email.mime default (this is used for creating email body)
* datetime (default) (For accessing and manipulating date and time)

# Import Packages
``` python
import requests # http requests

from bs4 import BeautifulSoup #web scraping
#send mail
import smtplib
# email body
from email.mime.multipart import MIMEMultipart
from email.mime.text import MIMEText
# system date and time manipulation
import datetime
```

# Python Script:

```python
import datetime

now = datetime.datetime.now()


# email content placeholder

content = ''
```
