# MACD-based Trading Strategy
I did this backtest after seeing a video youtube of someone claiming huge returns using a MACD trading strategy.
I did not believe this worked, because if it worked it would not be on youtube.

This project demonstrates how to compute and visualize the MACD indicator
and evaluate buy/sell signals using Python (Pandas, Matplotlib, yfinance).

### Features
- Clean calculation of EMA(12), EMA(26), and MACD signal line
- Visualization of price, trend, and MACD histogram
- Simple rule-based strategy and backtest performance
- Focus on clear, reproducible data analysis


### results
Apple stock from 2010 until 2025

| Metric              | Buy & Hold | MACD Strategy |
|---------------------|------------|----------------|
| **Total Return**     | 28.666832  | 12.575612      |
| **CAGR**             | 0.253475   | 0.189843       |
| **Volatility (ann)** | 0.282718   | 0.237167       |
| **Sharpe Ratio**     | 0.942718   | 0.853566       |
| **Max Drawdown**     | -0.437972  | -0.314272      |
| **Win Rate**         | NaN        | 0.875000       |
| **Average Win**      | NaN        | 0.535927       |
| **Average Loss**     | NaN        | -0.124497      |


### Conclusion

This project compares a simple MACD crossover strategy to a Buy & Hold benchmark on AAPL over a multi-year period.

The results show that Buy & Hold clearly outperforms the MACD strategy in terms of absolute and risk-adjusted returns. Buy & Hold achieves a higher total return (≈ 28.7× vs 12.6×) and a higher CAGR (25.3% vs 18.9%), while also delivering a slightly better Sharpe ratio (0.94 vs 0.85).

The MACD strategy does, however, offer lower risk in absolute terms:

- lower annualized volatility (23.7% vs 28.3%), and  
- a smaller maximum drawdown (–31.4% vs –43.8%).


In summary:

- Buy & Hold: higher return, deeper drawdowns, better risk-adjusted performance (higher Sharpe).  
- MACD strategy: lower volatility and drawdowns, but significantly lower long-term growth.

For a strong long-term uptrend like AAPL, this simple MACD implementation behaves more like a risk-reduction overlay than a return-enhancing strategy, and it does not outperform passive investing on a risk-adjusted basis.
This conclusion is in line with my hypothesis

### Tech stack
Python · Pandas · NumPy · Matplotlib · Jupyter