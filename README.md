# Amazon Price Tracker (Web Scraping)

A small Python tool that scrapes a product's title and price from Amazon on a schedule and logs each reading to a CSV file. Over time, this builds a price-history dataset that can be used for price monitoring or deal alerts.

## What it does

1. Sends an HTTP request with browser headers to an Amazon product page (`requests`)
2. Parses the product title and price from the HTML (`BeautifulSoup`)
3. Appends `Title, Price, Date` to `AmazonProduct.csv`
4. Repeats on a timer (`time.sleep`) so the price is tracked automatically
5. Loads the CSV with `pandas` for a quick check of the history

## Business use case

E-commerce teams track competitor prices in the same way to adjust their own pricing and promotions. Shoppers can also use it to buy when the price drops.

## Tools

Python · requests · BeautifulSoup4 · csv · pandas

## How to run

```bash
pip install requests beautifulsoup4 pandas
jupyter notebook WebScrapping.ipynb
```

Replace the `URL` in the notebook with any Amazon product link. Amazon may block frequent requests, so keep the interval reasonable.

## Next steps

- Clean the price into a numeric column and chart the price over time
- Send an email alert (`smtplib`) when the price falls below a target
- Track several products at once
