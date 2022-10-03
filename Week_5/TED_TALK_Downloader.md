# How to build TED Talk video downloader? 

# In this we see how to install packages:

* Installation and introduction to requests package
* Building the basic script to download the video
* Generalizing the script to get arguments
* Packaging the script as CLI tool

# Request:
It is the package that help us to get the web content. Request as name suggest HTTP request how the communication between a server and client happens in HTTP protocol.
The client request the server and server response back. 

# BeautifulSoup::
It is another important package that we are going to use. It is the package that is used to extract data out of HTML XML. Primarily it is used for web scrapping.
It extract what we want from HTML and XML.

# Basic Script to download the Video:

```python
import requests # getting content of TED Talk page

from bs4 import BeautifulSoup #web scrapping

import re # Regular expression pattern matching

#from urllib.request import url retrieve # downloading mp4

import sys #for argument parsing

#Exception Handling
if len(sys.argv) > 1:
    url = sys.argv[1]
else:
    sys.exit("Error: Please enter the TED Talk URL")

#url = "https://www.ted.com/talks/sir_ken_robinson_do_schools_kill_creativity"

r = requests.get(url)

print("Download about to start")

soup = BeautifulSoup(r.content, features="lxml")

for val in soup.findAll("script"):
    if(re.search("talkPage.init", str(val))) is not None:
        result = str(val)
        
result_mp4 = re.search("(?P<url>https?://[^\s]+)(mp4)", result).group("url")

mp4_url = result_mp4.split('"')[0]
print("Downloading video from ....." + file_name)

r = requests.get(mp4_url)

with open(file_name, 'wb') as f:
     f.writer(r.content)
```
