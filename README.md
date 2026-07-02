# Flipkart Scraper

A Python scraper that extracts product data from [Flipkart](https://www.flipkart.com) search and category pages using `requests` and `BeautifulSoup`.

## Features

- Search Flipkart by keyword and scrape results across multiple pages
- Extract product title, price, rating, number of reviews, and product URL
- Export scraped data to CSV / JSON
- Configurable delay between requests to avoid rate-limiting

## Requirements

- Python 3.9+
- `requests`
- `beautifulsoup4`
- `pandas` (for CSV/JSON export)

## Installation

```bash
git clone <your-repo-url>
cd flipkart-scraper
python -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

## Usage

```bash
python scraper.py --query "wireless mouse" --pages 3 --output results.csv
```

### Arguments

| Argument | Description | Default |
|---|---|---|
| `--query` | Search keyword to scrape | required |
| `--pages` | Number of result pages to scrape | `1` |
| `--output` | Output file path (`.csv` or `.json`) | `output.csv` |
| `--delay` | Delay in seconds between requests | `2` |

## Output

Each row/record contains:

- `title` — Product name
- `price` — Current price
- `rating` — Average rating (out of 5)
- `reviews` — Number of ratings/reviews
- `url` — Direct link to the product page

## Notes

- Flipkart's HTML structure changes periodically — selectors in `scraper.py` may need updates if scraping breaks.
- This project is for educational/personal use. Respect Flipkart's [robots.txt](https://www.flipkart.com/robots.txt) and terms of service, and avoid sending high-frequency requests.

## License

MIT
