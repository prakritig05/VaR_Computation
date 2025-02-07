**Value at Risk (VaR) of AAPL in 2023**

1. **Introduction**

The purpose of this analysis is to calculate and analyze the **Value at Risk (VaR)** of Apple Inc.'s (AAPL) stock using daily returns data for the year 2023. VaR is a measure of the potential loss in the value of an asset or portfolio over a specified period for a given confidence interval. This analysis also includes an assessment of the stock's daily returns, their distribution, and key statistics to better understand the behavior and risk of AAPL during the specified period.

The analysis was carried out using the following key components:

- **Historical Price Data** for AAPL obtained from Yahoo Finance.
- **VaR Calculation** using the 95% and 99% confidence intervals based on daily percentage changes.
- **Interactive Visualization** of AAPL's adjusted closing prices and daily returns using Plotly.![ref1]
2. **Data Acquisition and Preprocessing**

The data was sourced from Yahoo Finance, and the following steps were undertaken:

1. **Historical Data**: Downloaded the adjusted closing prices of AAPL from January 1, 2023, to December 31, 2023.
1. **Data Cleaning**: The adjusted closing prices were extracted, and daily percentage changes (returns) were calculated.
1. **Return Calculation**: The daily returns were computed by taking the percentage change in the adjusted closing prices between consecutive trading days.

The first few rows of the data are as follows:



|**DATE**|**Adjusted Closing Price (USD)**|
| - | - |
|2023-01-03|123\.77|
|2023-01-04|125\.05|
|2023-01-05|123\.72|
|2023-01-06|128\.27|
|2023-01-09|128\.80|

3. **Visualization of AAPL Data![ref1]**
1. **Adjusted Closing Prices of AAPL (2023)**

The first visualization illustrates the **adjusted closing prices** of AAPL throughout 2023. This time series graph provides a clear view of AAPL's price movements over the year.

line\_chart = go.Figure()

line\_chart.add\_trace(go.Scatter(

x=prices.index,

y=prices.values,

mode='lines',

line=dict(color='purple', width=2),

name='Adjusted Closing Prices'

))

line\_chart.update\_layout(

title="Adjusted Closing Prices of AAPL (2023)", title\_font=dict(size=20, color='black', family='Arial'), xaxis\_title="Date",

yaxis\_title="Adjusted Closing Price (USD)", xaxis=dict(showgrid=True, gridcolor='lightgray', zeroline=False), yaxis=dict(showgrid=True, gridcolor='lightgray', zeroline=False), template="plotly\_white",

margin=dict(l=50, r=50, t=50, b=50)

)

line\_chart.show()![ref1]

2. **Histogram of Daily Returns with VaR Thresholds**

The second visualization provides a histogram of AAPL's daily returns for 2023. The **95% VaR** and **99% VaR** thresholds are shown as vertical lines on the histogram to illustrate potential losses at the respective confidence levels.

hist\_chart = px.histogram(

returns,

nbins=50,

opacity=0.75,

title="Histogram of Daily Returns with VaR Thresholds (2023)",

labels={'value': 'Daily Returns (%)', 'count': 'Frequency'}, color\_discrete\_sequence=['pink']

)

- Adding 95% VaR line

hist\_chart.add\_vline(

x=var\_95,

line=dict(color="purple", width=4, dash="dash"), annotation\_text=f"95% VaR: {-var\_95:.2%}", annotation\_position="top right", annotation=dict(font\_size=12, font\_color="purple")

)

- Adding 99% VaR line

hist\_chart.add\_vline(

x=var\_99,

line=dict(color="orange", width=4, dash="dash"), annotation\_text=f"99% VaR: {-var\_99:.2%}", annotation\_position="top right", annotation=dict(font\_size=12, font\_color="orange")

)

hist\_chart.update\_layout(

xaxis\_title="Daily Returns (%)",

yaxis\_title="Frequency",

title\_font=dict(size=20, color='black', family='Arial'), xaxis=dict(showgrid=True, gridcolor='lightgray', zeroline=False), yaxis=dict(showgrid=True, gridcolor='lightgray', zeroline=False), template="plotly\_white",

margin=dict(l=50, r=50, t=50, b=50),

legend=dict(yanchor="top", y=0.99, xanchor="left", x=0.01)

) hist\_chart.show()

4. **Summary Statistics of Daily Returns![ref1]**

To better understand the characteristics of the daily returns for AAPL in 2023, we calculated several key statistical metrics. These metrics provide insights into the overall behavior and risk associated with the stock's price movements over the year.

The summary statistics of the daily returns are as follows:



|**METRIC**|**VALUE**|
| - | - |
|**Mean Return**|0\.00064|
|**Standard Deviation**|0\.0189|
|**Minimum Return**|-0.1202|
|**Maximum Return**|0\.1150|

**4.1 Interpretation of the Summary Statistics**

- **Mean Return (0.00064)**: The average daily return for AAPL in 2023 was approximately 0.064%. This indicates that, on average, AAPL's price increased slightly each day during this period.
- **Standard Deviation (0.0189)**: The standard deviation of 0.0189 (or 1.89%) indicates the degree of volatility or risk in the daily returns. A higher standard deviation suggests more price fluctuations, while a lower value indicates more stable prices.
- **Minimum Return (-0.1201)**: The minimum return of -12.01% represents the largest negative return observed in a single day during 2023. This figure highlights the risk of experiencing significant losses in extreme market conditions.
- **Maximum Return (0.1150)**: The maximum return of 11.50% indicates the largest positive return in a single day. This shows the potential for large gains, but as with the minimum return, this is an extreme value and not representative of typical daily movements.

These statistics are essential for assessing the risk and potential return of holding AAPL stock. Investors can use these metrics to understand the stock's performance and the likelihood of experiencing significant gains or losses.

5. **VaR Calculation![ref1]**

The **Value at Risk (VaR)** for AAPL's stock was calculated for both the **95%** and **99%** confidence intervals based on the daily returns for 2023. These quantiles represent the loss levels that are expected to be exceeded with a 5% and 1% probability, respectively.

- **95% VaR**: The 95% VaR represents the loss that is expected to be exceeded on 5% of the days. It was calculated as the 5th percentile of the returns distribution.
- **99% VaR**: The 99% VaR represents the loss that is expected to be exceeded on 1% of the days. It was calculated as the 1st percentile of the returns distribution.
1. **VaR Values**

The Value at Risk was calculated for AAPL based on its daily returns using both the 95% and 99% confidence intervals:

- **95% VaR in USD**: $3.35 (₹283.08)
- **99% VaR in USD**: $6.24 (₹527.94)
- **95% VaR Percentage**: -1.75%
- **99% VaR Percentage**: -3.26%
2. **Monetary VaR**

The potential loss is expressed in INR using the current USD/INR exchange rate (84.56 INR to 1 USD):

- **95% VaR in INR**: ₹283.08
- **99% VaR in INR**: ₹527.94

These values represent the potential daily losses in INR for an equivalent investment in AAPL.![ref1]

6. **Results**

The following results were obtained from the analysis of AAPL's adjusted closing prices and daily returns in 2023:

- **Mean Return**: 0.00064 (or 0.064%) per day.
- **Standard Deviation**: 0.0189 (or 1.89%), indicating moderate volatility in AAPL's daily returns.
- **Minimum Return**: -12.01%, representing the largest daily loss during the year.
- **Maximum Return**: 11.50%, representing the largest daily gain during the year.
- **95% VaR**: -1.75% (Expected loss not exceeded 95% of the time)
- **99% VaR**: -3.26% (Expected loss not exceeded 99% of the time)![ref1]
7. **Conclusion**

This analysis provides a comprehensive view of the risk associated with holding AAPL stock in 2023 through the calculation of Value at Risk (VaR) and other key risk metrics. The VaR estimates suggest that the potential downside risk of holding AAPL is substantial but not extreme, with a maximum expected loss of 3.26% on the worst days. However, the stock also showed significant potential for gains, with positive returns reaching up to 11.50% in a single day.

Understanding VaR and other risk metrics is essential for investors who wish to gauge the potential losses from holding a particular stock. By using these tools, investors can make more informed decisions about their portfolios, particularly in volatile market conditions.![ref1]

8. **References**
1. Hull, J. C. (2022). **"Options, Futures, and Other Derivatives" (11th Edition)**.
1. **Yahoo Finance**. (2023). Apple Inc. (AAPL) Stock Data. Retrieved from <https://finance.yahoo.com>.
1. Jorion, P. (2007). **Value at Risk: The New Benchmark for Managing Financial Risk** (3rd ed.). McGraw-Hill.
1. McNeil, A. J., Frey, R., & Embrechts, P. (2015). **Quantitative Risk Management: Concepts, Techniques, and Tools** (2nd ed.). Princeton University Press.
1. **Plotly**. (2023). Interactive Data Visualization with Plotly. Retrieved from <https://plotly.com>.![ref1]

This concludes the comprehensive analysis of **Value at Risk (VaR)** for AAPL in 2023. The findings are valuable for risk management in financial portfolios, offering key insights into potential loss levels under different market conditions.![ref1]

PRAKRITI GUPTA **SE22UCAM008** VRISHKETU SINGHANIA **SE22UCAM012** UTKARSH MANGAL **SE22UCAM015![ref1]**

[ref1]: Aspose.Words.f76190b6-89d8-4e36-b97d-b84cb718da22.001.png
