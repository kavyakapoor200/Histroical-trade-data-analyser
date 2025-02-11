# Histroical-trade-data-analyser
Binance Trading Data Analysis Report 

1. Methodology 

Data Preprocessing & Cleaning 

The dataset contains Port_IDs (unique account identifiers) and Trade_History (detailed trade records). 

Missing values were handled by removing incomplete records to maintain accuracy which removed only 1 as there were only one missing value in trade history. 

Trade_History was converted from a string format into structured data for easier analysis. 

Feature Engineering & Metrics Calculation 

Return on Investment (ROI) – Measured by profit/investment *100 

Profit and Loss (PnL) – Net profit over 90 days. 

Sharpe Ratio – Expected Returns/ standard deviation of returns. 

Maximum Drawdown (MDD) – peak value-lowest value/peak value * 100 so that we can analyze the worst case. 

Win Rate – No. of win trades/ total trades*100. 

Win Positions – Number of trades that ended with a profit. 

Total Positions – Total number of trades executed. 

Ranking Algorithm 

A weighted scoring system was developed to ensure fair rankings: 

ROI (40%) – Profitability is the primary factor and best for traders if positive returns. 

Win Rate (30%) – Accounts with a higher percentage of profitable trades rank higher. 

Sharpe Ratio (20%) – Encourages consistency and stable profits. 

MDD (-10%) – negative factor accounts with excessive losses. 

Formula 

Ranking Score=(ROI×0.4)+(WinRate×0.3)+(SharpeRatio×0.2)−(MDD×0.1) 

The accounts were sorted based on the final ranking score, and the top 20 were selected. 

 

2. Findings 

The top-ranked accounts showed a balance between profitability and risk management. 

Some accounts had a high ROI but poor Sharpe Ratio, indicating high-risk strategies. 

Accounts with a low MDD and high Win Rate ranked better due to consistent performance and profitable traders. 

A few accounts had a negative ROI, indicating losses over the 90-days. 

 

3. Assumptions 

The dataset accurately represents 90 days of trading activity for each account. 

All trades are executed and settled as recorded, with no missing transactions. 

Realized profit values are correct and account for fees, slippage, and execution prices. 

Sharpe Ratio calculations assume normal return distributions, which may not always hold in real trading. 

 
