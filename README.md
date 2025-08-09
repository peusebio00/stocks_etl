## Yfinance-Excel-ETL
Extract data from yfinance, transform with pandas, and load to an Excel workbook
This Python script performs a daily ETL (Extract, Transform, Load) process to update an Excel workbook with the latest end-of-day stock market data. It uses the yfinance module to extract data for a predefined list of stock tickers, transforms the data using pandas, and then loads it into a multi-sheet Excel file.

## Features
__Automated Data Extraction__: Fetches end-of-day trading data (Open, High, Low, Close) for a list of stock tickers from the yfinance module.

__Robust Error Handling__: Integrates a safety mechanism to detect and handle extraction errors. If any data fails to extract, the script will stop and send an email notification to the user.

__Secure Credentials Management__: Utilizes a YAML file (credentials.yml) to securely store sensitive information like email addresses and passwords, preventing hardcoding in the script.

__Data Transformation__: The script cleans and restructures the raw data from yfinance into a clean, horizontal format, ensuring only yesterday's finalized market data is used.

__Targeted Data Loading__: Appends the transformed data to the correct rows in a multi-sheet Excel workbook without overwriting existing data. It dynamically identifies the correct row based on the date, ensuring accurate data placement.
