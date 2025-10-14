# 1. Introduction
This project focuses on **financial risk management** using a diversified ETF portfolio of equities (SPY), bonds (IEF), and gold (GLD). The analysis evaluates the portfolio’s risk through historical simulation, parametric (Gaussian) Value-at-Risk (VaR), Expected Shortfall (ES), rolling backtests, and stress scenarios such as the COVID-19 crash and 2022 inflation selloff.  

The main goal is to demonstrate practical applications of quantitative risk metrics in portfolio management, while highlighting the limitations and potential improvements for future work.

---

# 2. Tools Used
- **Python (Google Colab)** for interactive coding and visualization  
- **yfinance** for market data (ETF adjusted close prices)  
- **pandas & numpy** for data handling and statistical calculations  
- **scipy.stats** for parametric VaR modeling  
- **matplotlib & plotly** for visualization  
- **rich** for styled tabular/console output  
- **tabulate** for tabular summaries  

---

# 3. Pros
- Easy access to financial data through free APIs (Yahoo Finance).  
- Demonstrates multiple risk measures: VaR, ES, max drawdown, rolling volatility.  
- Backtesting (Kupiec test) provides statistical validation of model performance.  
- Visualizations make interpretation intuitive.  
- Stress scenarios help connect quantitative results to real-world events.  

---

# 4. Cons
- ETF proxies may not perfectly replicate broader asset classes.  
- Historical methods assume the past will resemble the future.  
- Gaussian VaR underestimates fat-tail risks.  
- Daily returns ignore intraday volatility and tail dynamics.  
- Results are sensitive to window length and confidence level selection.  

---

# 5. Fusion of Methods
This project **fuses multiple approaches**:  
- **Historical VaR/ES** for nonparametric, data-driven risk.  
- **Gaussian VaR** for simplicity and parametric comparison.  
- **Kupiec backtest** to statistically validate VaR reliability.  
- **Drawdown analysis** to capture investor experience.  
- **Stress testing** to reflect known extreme market conditions.  

---

# 6. Limitations
- Reliance on Yahoo Finance data, which may contain adjustments or missing values.  
- VaR is not coherent (fails subadditivity); ES is more robust but harder to backtest.  
- Kupiec test only checks frequency, not clustering of exceptions.  
- Does not include volatility modeling (e.g., GARCH, EWMA).  
- Simplified portfolio weights (fixed, static allocation).  

---

# 7. What Could Be Done Better
- Use **cleaner institutional-grade datasets** (Bloomberg, Refinitiv).  
- Implement **volatility-adjusted VaR** (e.g., GARCH, EWMA).  
- Add **alternative distributions** (t-distribution, Cornish-Fisher expansion) for fatter tails.  
- Expand to **multi-asset portfolios** (commodities, FX, crypto).  
- Include **liquidity and transaction cost modeling**.  

---

# 8. Future Implementations
- **Basel-compliant ES backtesting** at 97.5% confidence.  
- **Scenario analysis & Monte Carlo simulation** for forward-looking stress tests.  
- **Dynamic portfolio weights** (momentum, risk-parity).  
- **Machine learning** for regime detection and tail-event prediction.  
- **Integration into a dashboard** (Plotly Dash/Streamlit) for interactive reporting.  

---

# 9. Conclusion
The portfolio (SPY 60%, IEF 30%, GLD 10%) shows annualized volatility of 10.28% and max drawdown of -23.13% over 2010-01-04→2025-09-10

At 95% confidence:  
Historical VaR ≈ 1.02% and ES ≈ 1.49% (daily).

Kupiec backtest indicated whether VaR coverage was statistically valid. Stress scenario analysis captured the magnitude of losses during critical events (e.g., COVID crash, 2022 inflation).  

Overall, this project demonstrates how quantitative risk measures can be applied to portfolio analysis. While VaR remains widely used, ES provides a more coherent measure of tail risk. The combination of statistical modeling, backtesting, and stress testing provides a more holistic framework for risk management.  

---

# 10. References
[1] Yahoo Finance historical data (via yfinance): https://finance.yahoo.com  
[2] yfinance documentation: https://ranaroussi.github.io/yfinance/  
[3] Kupiec, P.H. (1995). *Techniques for Verifying the Accuracy of Risk Measurement Models*. The Journal of Derivatives 3(2):73–84.  
[4] Basel Committee on Banking Supervision (1996). *Backtesting framework & traffic-light approach*. https://www.bis.org/publ/bcbs22.pdf  
[5] Artzner, Delbaen, Eber, Heath (1999). *Coherent Measures of Risk*. Mathematical Finance 9(3):203–228.  
[6] Acerbi & Tasche (2001). *Expected Shortfall: a natural coherent alternative to VaR*. https://arxiv.org/pdf/cond-mat/0104295  
[7] Additional overview of VaR backtesting methods: https://research.manchester.ac.uk/files/60673220/back4.pdf  

**Note:** Parts of this report were formatted and edited with the assistance of ChatGPT for clarity and presentation.
