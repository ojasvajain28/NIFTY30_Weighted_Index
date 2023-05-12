


# NIFTY 30 Weighted Index

This repository contains a Jupyter Notebook file (`code.ipynb`) that demonstrates the calculation of the weighted index for the NIFTY 30 stocks.

## Overview

The NIFTY 30 is an index that represents the performance of the top 30 companies listed on the National Stock Exchange of India (NSE). This notebook retrieves historical stock data for these companies, calculates their standard deviations, selects the top 30 stocks with the lowest standard deviation, and assigns weights to them based on their reciprocal standard deviation values.

## Prerequisites

To run the notebook, you need the following libraries installed:

- yfinance
- pandas
- requests
- matplotlib
- seaborn
- plotly
- cufflinks

You can install these dependencies using pip:

```
pip install yfinance pandas requests matplotlib seaborn plotly cufflinks
```

## Usage

1. Clone the repository:

```
git clone https://github.com/your-username/NIFTY30_Weighted_Index.git
```

2. Open the Jupyter Notebook file `code.ipynb` in a Jupyter Notebook environment.

3. Execute the cells in the notebook to retrieve the data, calculate the weighted index, and visualize the results.



Feel free to explore the code, modify it, and adapt it to your needs.

## Explaination
The code you provided performs the following tasks:

1. Imports necessary libraries: `yfinance` for fetching stock data, `datetime` for working with dates, `pandas` for data manipulation, `requests` for making HTTP requests, `matplotlib.pyplot` and `seaborn` for data visualization.

2. Defines a list of stock symbols in the `stocks` variable. These symbols represent companies listed on the National Stock Exchange of India (NSE).

3. Sets the start and end dates for retrieving historical stock data. In this case, it sets the start date as 360 days before the current date and the end date as the current date.

4. Initializes two empty DataFrames: `close_price` and `ret_close_price`. These DataFrames will be used to store the closing prices and the percentage changes of the closing prices of the selected stocks, respectively.

5. Iterates over each stock symbol in the `stocks` list and downloads the adjusted closing prices using the `yf.download` function from the `yfinance` library. The retrieved data is then stored in the `close_price` DataFrame.

6. Calculates the percentage change of the closing prices for each stock using the `pct_change` function and stores the results in the `ret_close_price` DataFrame.

7. Computes the descriptive statistics (mean, standard deviation, etc.) of the percentage changes using the `describe` function and stores the results in the `describe` variable.

8. Selects the standard deviation values from the `describe` DataFrame and stores them in the `std_stocks` variable.

9. Sorts the `std_stocks` Series in ascending order and selects the top 30 stocks with the lowest standard deviation. Creates a new DataFrame called `top_30` to store these stocks and their corresponding reciprocals of standard deviation values.

10. Calculates the sum of the reciprocal of standard deviation values (`reci_vol`) from the `top_30` DataFrame and stores it in the variable `s`.

11. Computes the weight of each stock by dividing its reciprocal of standard deviation value by `s` and multiplying by 100. These weights are stored in the `weight` column of the `top_30` DataFrame.

12. Creates a plot using `matplotlib.pyplot` to visualize the weights of the top 30 stocks.

13. Imports additional libraries (`plotly`, `cufflinks`) for interactive visualization using Plotly.

14. Initializes Plotly for offline use.

15. Prints the version of Plotly.

Overall, this code retrieves historical stock data, calculates the standard deviation of stock returns, selects the top 30 stocks with the lowest standard deviation, and assigns weights to them based on their reciprocal standard deviation values. It then visualizes the weights of these stocks using both Matplotlib and Plotly libraries.

## Acknowledgments

- The [yfinance](https://pypi.org/project/yfinance/) library for providing an easy-to-use interface to fetch stock data from Yahoo Finance.
- The [Plotly](https://plotly.com/) library for interactive data visualization.
- The [National Stock Exchange of India (NSE)](https://www.nseindia.com/) for providing the NIFTY 30 stock data.

## Disclaimer

This project is for educational purposes only. The calculations and results presented in this repository may not reflect actual investment strategies or financial advice. Please use it responsibly and do your own research before making any investment decisions.

```
