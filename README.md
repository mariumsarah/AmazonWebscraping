# Amazon Webscraping 2022

The focus of this project is to scrape product level information from Amazon Grocery categories
<br/>

Webscraping using beautifulsoup or selenium can be challenging on Amazon with frequent bot questions that can block access after a 10-20 requests to Amazon. ScraperAPI makes it easy to webscrape using their API.
### Click here to learn more about how to use scrapy [click here](https://www.scraperapi.com/blog/how-to-scrape-amazon-product-data/)

<img src="https://github.com/mariumsarah/AmazonWebscraping/blob/main/docs/categories.png" height="600" width="auto" alt="image-detection icon"/>


<br/>

## Installation
Make sure you have [Python 3](https://www.python.org/downloads/) installed, then sign up on [Scrapy](https://www.scraperapi.com/blog/how-to-scrape-amazon-product-data/) to recieve an API Key. In a month, you are allowed 5000 requests. Replace the ``API_KEY`` value in amazon.py to the API key you recieve once logged in.

Install ``scrapy`` to be able to start using scrapy.
```Python
pip install scrapy
```

## Instructions
Run the following commands to start a scrapy project.
```Python
scrapy startproject amazon_scraper # start a project
cd amazon_scraper # go to the created project
scrapy genspider amazon amazon.com #create a spider for this project
```

Running the last command will create an ``amazon.py`` file. Paste the code from amazon.py in this github rep to start scraping products.
The global variable ``queries`` consists of all the categories given under the Grocery Department on Amazon.
Use the following command to start the program and save results into a CSV files -
``scrapy crawl amazon -o babyfood_300.csv``

Adjust the limit of products per category by modifying the variable ``self.limit`` in the ``get_url()`` function.

<br/>
