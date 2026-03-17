## Motivation: 
- To analyse and simulate the investment characteristics of an endowment fund portfolio.

## Scenario: 
- Assume an endowment fund (EF) is evaluating opportunities to enhance its portfolio by considering six exchange-traded funds (ETFs):
  + Vanguard FTSE Europe ETF (VGK).
  + Vanguard S&P 500 ETF (VOO).
  + SPDR Gold Shares (GLD).
  + United States Oil Fund LP (USO).
  + iShares U.S. Real Estate ETF (IYR).
  + Grayscale Bitcoin Trust (GBTC).

- The fund’s current allocation is concentrated in three assets:
  + 50% VGK (European equities).
  + 30% VOO (U.S. equities).
  + 20% USO (oil exposure).

## Objective: 
- Evaluate the performance of the current portfolio and assess whether a diversified allocation across the six ETFs can enhance returns and reduce overall portfolio risk.

## Data:
- Historical monthly retrn from 01/2027 to 12/2024.
- Risk-free rate = 0.
- No transaction cost.
- Assumed current date: 1/1/2025.
  
## Current Allocation Performance:
<img width="272" height="183" alt="image" src="https://github.com/user-attachments/assets/3bd6f372-63b8-448d-97ae-fea0a3f0266d" />
<img width="276" height="183" alt="image" src="https://github.com/user-attachments/assets/af57926b-8f11-47de-8f59-c312191b0bca" />

Let's called the current allocation is P0. Portfolio P0 has an average monthly return of 0.73%, which is higher than VGK (0.61%) and USO (0.59%), but still lower than VOO (1.02%). In terms of risk, P0’s standard deviation is 5.71%, slightly higher than VGK and VOO but much lower than the highly volatile USO (12.82%). The Sharpe ratio of P0 (12.72%) is also higher than VGK and USO, suggesting that combining these assets improves risk-adjusted performance through diversification. Overall, while VOO performs best as a single asset, the portfolio provides a more balanced outcome by reducing the impact of USO’s high volatility while still achieving a reasonable level of return.

## Should UF expanding investment universe with suggested ETFs?
  The analysis suggests that UF should consider expanding its investment universe. When the portfolio includes only three ETFs, the efficient frontier is relatively limited and the portfolio is heavily concentrated in VOO, which reduces diversification benefits. However, when the investment universe expands to six ETFs, the efficient frontier shifts outward, providing a wider range of risk–return combinations and more efficient investment opportunities. In particular, the GMVP standard deviation decreases from 4.90% to 3.11%, indicating that the additional assets help reduce portfolio volatility.
<p align="center">
  <img src="https://github.com/user-attachments/assets/22488fe4-bb20-45ba-8e1a-c9734a7e1e1b" width="45%">
  <img src="https://github.com/user-attachments/assets/9d6d2369-01d2-4909-97d0-5d3bf67b6c29" width="45%">
</p>

  The efficient frontier also shows that the portfolio can achieve higher expected returns for different levels of risk, allowing the fund to better balance risk and return. Overall, including additional asset classes such as gold, real estate, and cryptocurrency improves diversification and enables the fund to construct more efficient portfolios.

