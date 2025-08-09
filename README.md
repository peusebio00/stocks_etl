## Yfinance-Excel ETL
This is a script I built to help a very special stakeholder optimise a process they carry out manually and on a daily basis... my dad :)
* For years now, my dad has kept up with the stock market due to personal interest and for his own personal endeavours - almost every single day, he gets up earlier than he has to so he can sit down and dedicate some time to manually extract OHLC (Open, High, Low, Close) values from the previous day and for 20 distinct stock tickers of his own choosing. He then uses this information to drive his decision-making - e.g. buying/selling stocks.
* In setting out to build this project, I aimed to fully automate this process for him so he has to do absolutely no manual work. As such, the overarching goal(s) for this project were to cover a full ETL project where data would be extracted from Yahoo Finance, transformed using Python/Pandas, and then loaded to a target Excel file - the very file my dad uses and adds the data to manually on a daily basis

## Automation
This script was stored in this repository as a Jupyter Notebook, e.g. a file with the .ipynb extension. 
However, to allow for maximum automation and efficiency, this script was later __converted to a .py file__, and a trigger was set using __Windows' Task Scheduler__ (which supports .py but not .ipynb files), to ensure it is __executed every single day at the same time__, and thus eliminates any and all manual workload my dad would have to do - even simply executing the file!

## Summary
Extract data from yfinance, transform with pandas, and load to an Excel workbook
This Python script performs a daily ETL (Extract, Transform, Load) process to update an Excel workbook with the latest end-of-day stock market data. It uses the yfinance module to extract data for a predefined list of stock tickers, transforms the data using pandas, and then loads it into a multi-sheet Excel file.

## Features
__Automated Data Extraction__: Fetches end-of-day trading data (Open, High, Low, Close) for a list of stock tickers from the yfinance module.

__Robust Error Handling__: Integrates a safety mechanism to detect and handle extraction errors. If any data fails to extract, the script will stop and send an email notification to the user.

__Secure Credentials Management__: Utilizes a YAML file (credentials.yml) to securely store sensitive information like email addresses and passwords, preventing hardcoding in the script.

__Data Transformation__: The script cleans and restructures the raw data from yfinance into a clean, horizontal format, ensuring only yesterday's finalized market data is used.

__Targeted Data Loading__: Appends the transformed data to the correct rows in a multi-sheet Excel workbook without overwriting existing data. It dynamically identifies the correct row based on the date, ensuring accurate data placement.
