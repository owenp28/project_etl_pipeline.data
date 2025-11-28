
Project Description:
Simple ETL Pipeline project to extract fashion product data from Fashion Studio website, transform the data, and load it to various output formats (CSV, Google Sheets, PostgreSQL).

Main Features:
1. Extract: Extract product data from HTML using BeautifulSoup
2. Transform: Clean and format product data
3. Load: Save data to CSV, Google Sheets, and PostgreSQL

Technologies Used:
- Python
- BeautifulSoup for web scraping
- Pandas for data manipulation
- Google Sheets API
- SQLAlchemy for database

Website URL being scraped:
https://fashion-studio.dicoding.dev/

Extracted Data Structure:
- Title: Page title
- Brand: Brand name (Fashion Studio)
- Products: Array containing product data with fields:
  - name: Product name
  - price: Product price
  - rating: Product rating
  - size: Product size
  - gender: Target gender

=== HOW TO RUN THE SCRIPT ===

1. How to Run ETL Pipeline:
   python main.py

2. How to Run Unit Tests:
   python -m pytest tests/ -v

3. How to Run Test Coverage:
   python -m pytest tests/ --cov=utils --cov-report=html
   or
   python -m pytest tests/ --cov=utils --cov-report=term-missing

4. Google Sheets URL: https://docs.google.com/spreadsheets/d/1BxiMVs0XRA5nFMdKvBdBZjgmUUqptlbs74OgvE2upms/edit?usp=sharing
   
   NOTES: 
   - Google Sheets contains 867 products from Fashion Studio scraping
   - Data has been cleaned according to criteria (no "Unknown Product", rating > 0, price > 0)
   - Access is set to PUBLIC (Anyone with the link can view)
   
   Data structure in Google Sheets:
   - title: Product name (string)
   - Price: Price in IDR (float, USD × 16000)
   - Rating: Product rating (float, 3.0-5.0)
   - Colors: Number of colors (integer, 3)
   - Size: Product size (string: S, M, L, XL, XXL)
   - Gender: Target gender (string: Men, Women, Unisex)
   - timestamp: Data processing time
   
   Total data: 867 rows of cleaned products
   Price range: 805,600 - 8,794,880 IDR
   
   PUBLIC ACCESS: Spreadsheet can be accessed without login

=== DEPENDENCIES INSTALLATION ===

1. Install requirements:
   pip install -r requirements.txt

2. Google Sheets Setup (REQUIRED for submission):
   - UPLOAD_TO_GOOGLE_SHEETS.csv file has been created automatically
   - Upload the file to Google Sheets manually
   - Set permission to "Anyone with the link can view"
   - Update URL in the "Google Sheets URL" section above

=== PROJECT STRUCTURE ===

submission/
├── tests/
│   ├── test_extract.py
│   ├── test_load.py
│   └── test_transform.py
├── utils/
│   ├── __init__.py
│   ├── extract.py
│   ├── load.py
│   └── transform.py
├── .coverage
├── .env
├── google-sheets-api.json
├── main.py
├── product.csv
├── requirements.txt
└── submission.txt