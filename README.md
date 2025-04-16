# Sansevieria Scraper

A Python-based web scraper specifically designed to extract Sansevieria product information from the Fermosa Plants website.

## Overview

This tool scrapes detailed information about Sansevieria plants available on [fermosaplants.com](https://fermosaplants.com), including product names, prices, whether plants are variegated, listing types, and more. The data is then organized and exported to an Excel spreadsheet for easy reference and analysis.

## Features

- Extracts comprehensive plant information including:
  - Product names
  - Pricing
  - Variegation status
  - Number of plants in combo listings
  - Listing types (plant, leaf, clump, etc.)
  - Product URLs
- Supports multi-threaded scraping for improved performance
- Automatically organizes data into Excel spreadsheets
- Identifies and extracts individual plant names from combo listings
- Tracks unique plant varieties

## Prerequisites

The script requires the following Python libraries:
- BeautifulSoup4
- Requests
- OpenPyXL
- Re (Regular Expressions) - built into Python
- Threading - built into Python
- Time - built into Python

Install dependencies:
```bash
pip install beautifulsoup4 requests openpyxl
```

## Usage

The script offers two main execution methods:

### Single-Threaded Mode
```python
python sansevieria_scraper.py --no-threading
```

### Multi-Threaded Mode (Default)
```python
python sansevieria_scraper.py
```

The multi-threaded mode significantly improves performance by scraping multiple pages concurrently.

## Output

The script generates an Excel file named `plantbook.xlsx` containing:
- A worksheet with all scraped Sansevieria listings
- Detailed information organized in columns with appropriate headers
- Individual plant names extracted from combo listings

## How It Works

1. The `Sansevierias` class initializes with base URLs and regex patterns for data extraction
2. Pages are scraped sequentially or using multiple threads
3. For each product listing:
   - Basic information is extracted from the listing card
   - The full product page is visited to extract additional details
   - Regular expressions identify plant names and characteristics
   - Data is organized and stored
4. All unique plant varieties are identified and tracked
5. Data is exported to Excel with appropriate headers

## Customization

You can modify the base URL in the main functions to scrape other plant collections:

```python
base_url = "https://fermosaplants.com/collections/your_plant_category?page="
```

## Performance

The multi-threaded implementation offers significant performance improvements:
- For the full Sansevieria collection (7 pages), execution time is typically reduced by 70-80%

---

## 👨‍💻 Author
Developed by [epicboi-deepubhai](https://github.com/epicboi-deepubhai)