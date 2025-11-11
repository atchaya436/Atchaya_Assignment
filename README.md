# Atchaya_Assignment
## Analyzing Historical Stock/Revenue Data and Building a Dashboard

### Project Overview
This project demonstrates how to extract, clean, and visualize real-world financial data using Python. The analysis focuses on two well-known companies Tesla (TSLA) and GameStop (GME). By leveraging APIs and web scraping techniques, this project retrieves historical stock price data and revenue reports, processes them, and creates interactive visualizations for insightful analysis. The objective is to understand how stock performance correlates with company revenues over time and to showcase practical skills in data extraction, cleaning, and visualization all key components of modern data science workflows.

### Objectives
  The main goal of this project is to:
* Extract historical stock price data using the yfinance library.
* Scrape revenue data for Tesla and GameStop using BeautifulSoup.
* Clean and organize the extracted data into structured Pandas DataFrames.
* Visualize the relationship between stock prices and revenues using Plotly.
* Build an understanding of how data pipelines can be created and automated for financial analysis.

### Learning Outcomes
* This project reinforces essential data science concepts including:
* Data extraction using APIs and web scraping.
* Data cleaning and preprocessing for analytical readiness.
* Creating interactive visualizations for storytelling and insights.
* Integrating multiple data sources to form a complete financial analysis pipeline.

### Tools and Technologies Used

* *Python*: Core programming language for data processing and visualization.
* *yfinance*: Used to fetch historical stock price data directly from Yahoo Finance.
* *BeautifulSoup (bs4)*: For web scraping quarterly revenue data from HTML web pages.
* *pandas*: For data cleaning, manipulation, and analysis.
* *Plotly*: For creating interactive, high-quality visualizations.
* *requests*: To send HTTP requests and download web page content.
* *Jupyter Notebook*: For developing and displaying code, results, and graphs in an interactive format.

### Process and Workflow
1. **Extracting Stock Data**

    The yfinance library is used to extract the historical stock data of Tesla (TSLA) and GameStop (GME). The Ticker function retrieves stock details, and the history(period="max") method fetches the complete stock price data from inception to the present. The resulting data includes columns such as Date, Open, High, Low, Close, Volume, and more.

2. **Web Scraping Revenue Data**

   The requests and BeautifulSoup libraries are employed to scrape revenue data from HTML tables on provided URLs. The project extracts quarterly revenue tables for Tesla and GameStop, parsing the HTML to locate and collect relevant rows and columns. Unwanted characters such as $ and , are removed to convert the revenue data into a numeric format suitable for analysis.

3. **Data Cleaning and Preparation**

    After extraction, both stock and revenue data are cleaned and formatted. The Date column is standardized, and the Revenue column is stripped of symbols and converted to float values. Missing or empty data entries are removed to ensure consistency and reliability before visualization.

4. **Data Visualization**

    A custom function named make_graph() is defined to visualize the extracted data. Using Plotly, the function creates two subplots:

      The first subplot displays the historical share prices.

      The second subplot shows the historical revenue.
      Both graphs share the same x-axis (Date) for comparison, enabling users to observe patterns and correlations between stock performance and revenue growth over time.

### Results and Insights
  The resulting interactive dashboard visually represents how Tesla’s and GameStop’s stock prices evolved in relation to their revenues. The charts highlight key financial trends, periods of rapid growth, and fluctuations that may correspond to real-world events or business milestones. The visualization helps users easily interpret data, identify relationships, and draw informed insights from complex financial datasets.
