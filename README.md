# MACD-based Trading Strategy Backtest

This project explores the performance of a simple MACD-based trading strategy compared to a Buy & Hold benchmark on Apple (AAPL). The motivation came from seeing claims of exceptionally high MACD returns online. I wanted to verify these claims by implementing and testing the strategy myself.

The project computes the MACD indicator, generates buy/sell signals, and performs a full daily backtest including equity curves and quantitative performance metrics.

---

## Features

- Computation of EMA(12), EMA(26), MACD line, and signal line  
- Visualization of price, MACD histogram, and buy/sell markers  
- Daily mark-to-market backtest (no lookahead bias)  
- Comparison against a Buy & Hold benchmark  
- Risk and performance metrics: CAGR, volatility, Sharpe, drawdown, win rate  
- Fully reproducible analysis using Python and pandas

---

## Dataset

- **Asset:** Apple (AAPL)  
- **Period:** 2010–2025  
- **Data source:** Yahoo Finance (`yfinance`)

---

## Results

### Performance Metrics

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

---

## Conclusion

This project compares a simple MACD crossover system against a Buy & Hold benchmark on AAPL over more than a decade of data.

**Buy & Hold clearly outperforms the MACD strategy**, both in absolute return and risk-adjusted return:

- Total return: ~28.7× vs ~12.6×  
- CAGR: 25.3% vs 18.9%  
- Sharpe Ratio: 0.94 vs 0.85  

The MACD strategy does, however, reduce risk in absolute terms:

- Lower annualized volatility (23.7% vs 28.3%)  
- Shallower max drawdown (–31.4% vs –43.8%)  
- High win rate (87.5%)  

This behavior is consistent with a **risk-reduction overlay**:  
the strategy exits the market during periods of negative momentum, reducing drawdowns and volatility, but missing significant portions of long upward trends.

For an asset with strong long-term performance like AAPL, this simple MACD implementation **does not outperform passive investing**, even on a risk-adjusted basis.  
This aligns with the initial hypothesis: if a simple indicator consistently produced exceptional returns, it would not be publicly available on YouTube.

---

## Tech Stack

- **Python**
- **Pandas**
- **NumPy**
- **Matplotlib**
- **yfinance**
- **Jupyter Notebook**

---

## Future Improvements

- Include transaction costs & slippage  
- Test different MACD parameter sets  
- Use walk-forward or rolling out-of-sample testing  
- Compare against other trend-following models  
- Evaluate performance on multiple assets and regimes  
