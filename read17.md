# [reading-note-401](https://mohammadsilwadi.github.io/reading-note-401/)
## Web scraping
Web scraping is a technique to automatically access and extract large amounts of information from a website, which can save a huge amount of time and effort.

Python Code

`import requests
import urllib.request
import time
from bs4 import BeautifulSoup`

next 

`url = 'http://web.mta.info/developers/turnstile.html'
response = requests.get(url)`


## How to scrape websites without getting blocked 

+ Respect Robots.txt 

+ Make the crawling slower, do not slam the server, treat websites nicely


+ Do not follow the same crawling pattern


+ Make requests through Proxies and rotate them as needed


+ Rotate User Agents and corresponding HTTP Request Headers between requests

+ Use a headless browser like Puppeteer, Selenium or Playwright

+ Check if Website is Changing Layouts

+ Avoid scraping data behind a login

+ Use Captcha Solving Services