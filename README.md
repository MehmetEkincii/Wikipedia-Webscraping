# Wikipedia-Webscraping
A Python project that scrapes the list of largest companies in the United States by revenue from Wikipedia and structures the data using pandas.
# Overview
This project uses requests and BeautifulSoup to pull a live HTML table from Wikipedia, parse it, and load it into a pandas DataFrame for analysis.
Data Source: https://en.wikipedia.org/wiki/List_of_largest_companies_in_the_United_States_by_revenue

# How It Works
Fetch the page — requests.get() sends an HTTP GET request to the Wikipedia URL. A custom User-Agent header is included to avoid being blocked by Wikipedia's server.

Parse the HTML — BeautifulSoup reads the raw HTML and makes it easy to navigate and search for specific elements like table headers and rows.

Extract the data — The table headers and row values are pulled out using BeautifulSoup's find methods.

Structure with pandas — The extracted data is loaded into a DataFrame, giving you a clean, readable table.

from bs4 import BeautifulSoup
import requests
import pandas as pd

url = 'https://en.wikipedia.org/wiki/List_of_largest_companies_in_the_United_States_by_revenue'
headers = {"User-Agent": "Mozilla/5.0"}

page = requests.get(url, headers=headers)
soup = BeautifulSoup(page.text, 'html.parser')

Open Scraping a Table from a Website.ipynb and run the cells in order.

# What i learned 
How HTTP requests work and how Python fetches web pages

Why servers require a User-Agent header and how to set one

How to navigate and extract data from HTML using BeautifulSoup

How to load unstructured scraped data into a structured pandas DataFrame

How to debug and fix common environment errors like missing modules
