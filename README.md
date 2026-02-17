# Trader-Performance-vs-Market-Sentiment

Analyze how market sentiment (Fear/Greed) relates to trader behavior and performance on Hyperliquid. Your goal is to uncover patterns that could inform smarter trading strategies.

## How to run the project

1. Clone the repository and create a new virtual environment.
2. Activate their new environment.
3. Install the required dependencies using the command:
   bash'''
   pip install -r requirements.txt
   '''

## Summary

#### Methodology

I combined two datasets:

- Bitcoin Fear & Greed Index (daily sentiment classification)
- Historical trader data from Hyperliquid

Both datasets were aligned at a daily level using trade timestamps.

From the merged dataset, I calculated:

- Total PnL per sentiment
- Win rate
- Maximum drawdown (using cumulative PnL peaks as a proxy)
- Trade frequency
- Average position size (USD notional per opening trade)
- Total capital deployed per sentiment
- Long/Short bias (using only Open Long and Open Short trades)

#### Key Insights

Traders behave differently depending on market sentiment.

- Trade frequency is highest during Fear and Greed, and lower during Extreme Fear. This suggests traders are more active when markets are moving but not in extreme panic.

- Average position size is highest during Fear, which indicates traders take larger bets during pullbacks compared to extreme panic or extreme euphoria.

- Extreme Fear shows the strongest long bias, suggesting dip-buying behavior during panic conditions.

- Greed regimes show much larger drawdowns compared to Fear, even though profitability is still strong. This suggests higher risk-taking during Greed periods.

- Extreme Greed has almost neutral long-short bias, which may indicate profit-taking or more balanced positioning.

Overall, trader participation, sizing, and directional bias all change depending on sentiment.

#### Strategy Recommendations

- Increase exposure selectively during Fear regimes since traders show strong conviction and relatively controlled drawdowns.

- Reduce leverage or tighten risk controls during Greed regimes because drawdowns are significantly larger.

- Consider structured dip-buying strategies during Extreme Fear, as long bias and profitability improve in panic-driven markets.
