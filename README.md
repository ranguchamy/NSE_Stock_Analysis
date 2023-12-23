This script is a Python program that fetches historical stock price data using the yfinance library, calculates the weekly Relative Strength Index (RSI) for a given stock, and sends an email alert if the calculated RSI surpasses a specified threshold.

Here's a breakdown of the script:

## Importing Libraries:

  ```python
  import yfinance as yf
  import pandas as pd
  from datetime import datetime, timedelta
  import smtplib
  from email.mime.text import MIMEText
  ```
These lines import necessary libraries for handling financial data (yfinance), data manipulation (pandas), working with dates (datetime and timedelta), and sending emails (smtplib and email.mime.text).

## Defining the calculate_weekly_rsi Function:

```python
def calculate_weekly_rsi(symbol):
    # ... (see details below)
    return weekly_rsi

```
This function takes a stock symbol as input, downloads historical price data, calculates daily RSI, and then converts it to weekly RSI. The result, weekly_rsi, is returned.


## Defining the send_email Function:

```python
def send_email(subject, body):
    # ... (see details below)

```
This function configures email settings (sender email, receiver email, and password), creates an email message with the specified subject and body, and sends the email using Gmail's SMTP server.
## Calculating Weekly RSI and Sending Email:
```python
weekly_rsi = calculate_weekly_rsi(ticker)

print(weekly_rsi)
print("Weekly RSI Value:", weekly_rsi.iloc[-1])
print("Threshold Value:", threshold)

if weekly_rsi.iloc[-1] > threshold:
    print("Condition is True")
    send_email(f"{ticker} Weekly RSI Alert", f"The weekly RSI for {ticker} is above {weekly_rsi.iloc[-1]}.")
else:
    print("Condition is False")

```
For each ticker, it calculates the weekly RSI, prints the RSI value and the threshold, and checks if the RSI is above the threshold. If it is, an email alert is sent; otherwise, a message is printed indicating that the condition is false.


