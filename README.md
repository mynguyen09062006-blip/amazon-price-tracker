# Amazon Price Tracker (Web Scraping)

## What this project does

A small Python script that visits an Amazon product page, reads the product title and price, and saves them with today's date to a CSV file. It can run on a loop, so over time it builds a price history for that product.

## Why it is useful

Price history helps shoppers buy at the right time and helps online sellers keep an eye on competitor prices. This was also my first web-scraping project, where I practised working with HTML, requests and CSV files.

## How I processed the data

**1. Requesting the page**
- Sent a request to the product URL with `requests`, adding browser-like headers (User-Agent, Accept-Language, Referer) so Amazon returns the normal page.

**2. Parsing the HTML**
- Parsed the page with BeautifulSoup and found the title by its element id (`productTitle`) and the price by its class.

**3. Cleaning the values**
- Removed extra spaces and line breaks with `strip()`, and trimmed the price text to keep only the price.
- Added the current date with `datetime.date.today()`.

**4. Saving to CSV**
- Created `AmazonProduct.csv` with the header `Title, Price, Date`, then appended a new row on every run.

**5. Automating**
- Wrapped the steps in a `check_price()` function and ran it in a loop with `time.sleep()`.
- Loaded the CSV back with pandas to check the collected data.

## Getting started

1. Clone the repository:
   ```bash
   git clone https://github.com/mynguyen09062006-blip/WebScrapping-v1-.git
   cd WebScrapping-v1-
   ```
2. Install the libraries:
   ```bash
   pip install requests beautifulsoup4 pandas jupyter
   ```
3. Open `WebScrapping.ipynb`, replace `URL` with the Amazon product you want to track, and run the cells. The CSV is saved to your Desktop.

> Amazon may block requests that are sent too often, so keep a reasonable interval between runs.

## Getting help

If you have a question or find a problem, please open an issue in this repository or contact me on [LinkedIn](https://www.linkedin.com/in/my-nguyen-anh/) or at mynguyen09062006@gmail.com.
