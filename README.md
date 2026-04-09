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
 
- Data:
  + Historical monthly return from 01/2027 to 12/2024.
  + Risk-free rate = 0.
  + No transaction cost.
  + Assumed current date: 1/1/2025.

## Objective: 
- Evaluate the performance of the current portfolio and assess whether a diversified allocation across the six ETFs can enhance returns and reduce overall portfolio risk.

## Current Allocation Performance:
<p align="center">
  <img width="272" height="183" alt="image" src="https://github.com/user-attachments/assets/3bd6f372-63b8-448d-97ae-fea0a3f0266d" />
  <img width="276" height="183" alt="image" src="https://github.com/user-attachments/assets/af57926b-8f11-47de-8f59-c312191b0bca" />
</p>

- Let's called the current allocation is P0. Portfolio P0 has an average monthly return of 0.73%, which is higher than VGK (0.61%) and USO (0.59%), but still lower than VOO (1.02%). In terms of risk, P0’s standard deviation is 5.71%, slightly higher than VGK and VOO but much lower than the highly volatile USO (12.82%). The Sharpe ratio of P0 (12.72%) is also higher than VGK and USO, suggesting that combining these assets improves risk-adjusted performance through diversification. Overall, while VOO performs best as a single asset, the portfolio provides a more balanced outcome by reducing the impact of USO’s high volatility while still achieving a reasonable level of return.

## Should UF expanding investment universe with suggested ETFs?
- The analysis suggests that UF should consider expanding its investment universe. When the portfolio includes only three ETFs, the efficient frontier is relatively limited and the portfolio is heavily concentrated in VOO, which reduces diversification benefits. However, when the investment universe expands to six ETFs, the efficient frontier shifts outward, providing a wider range of risk–return combinations and more efficient investment opportunities. In particular, the GMVP standard deviation decreases from 4.90% to 3.11%, indicating that the additional assets help reduce portfolio volatility.

<p align="center">
  <img src="https://github.com/user-attachments/assets/22488fe4-bb20-45ba-8e1a-c9734a7e1e1b" width="45%">
  <img src="https://github.com/user-attachments/assets/9d6d2369-01d2-4909-97d0-5d3bf67b6c29" width="45%">
</p>

- The efficient frontier also shows that the portfolio can achieve higher expected returns for different levels of risk, allowing the fund to better balance risk and return. Overall, including additional asset classes such as gold, real estate, and cryptocurrency improves diversification and enables the fund to construct more efficient portfolios.

## OPTIMAL RISKY 6 ETFs PORTFOLIO:
- As the efficient frontier suggest EF should expand the portfolio to 6 ETFs, this stage will dive into how to contruct such portfolio. The chosen method is optimal risky portfolio.
- Alternative methods are less suitable:
  + Global minimum variance focuses only on risk and may lead to low-return allocations.
  + Equal-weighted portfolios ignore differences in risk, return, and correlation, resulting in inefficiency.
  + Risk parity balances risk but tends to underweight higher-return assets, potentially limiting performance.
- Compared to other method, the optimal risky portfolio directly maximises the Sharpe ratio, making it more aligned with the objective of enhancing risk-adjusted returns. This aligns with an endowment fund’s objective of achieving both capital preservation and long-term growth, while fully incorporating diversification benefits.
- Additionally, Endowment funds typically avoid short selling due to their long-term investment horizon, as well as regulatory and reputational considerations. Although this is not a strict rule, a no short-selling constraint is imposed to better reflect realistic investment behaviour. Therefore, both unconstrained and constrained optimal risky portfolios are constructed, referred to as P1 and P2, respectively. The allocations and performance of P1 and P2 are presented below.
  
<p align="center">
  <img width="180" height="157" alt="image" src="https://github.com/user-attachments/assets/1a501a48-2164-4a3b-aa47-66011e8fded3" />
  <img width="177" height="183" alt="image" src="https://github.com/user-attachments/assets/2456118e-7c61-49b8-a441-85d210b30971" />
</p>
<p align="center">
  <img width="180" height="131" alt="image" src="https://github.com/user-attachments/assets/a27ac2e7-bd07-40d9-8e03-88b9edb6a9c5" />
  <img width="177" height="157" alt="image" src="https://github.com/user-attachments/assets/9fe090fd-9526-4729-8baf-3bad9f8e1b8b" />
</p>

- P1 weights are economically intuitive, allocating to high Sharpe assets (VOO, GLD) and shorting less efficient ones (VGK, IYR), with a small allocation to GBTC for its high return. This leads to higher returns and Sharpe ratio. However, it relies on leverage and short selling, increasing downside and reputational risk. In contrast, P2 provides more realistic and implementable weights, focusing on VOO and GLD while limiting exposure to high-risk assets. Although it delivers slightly lower performance than P1, it avoids leverage and short selling, making it more consistent with the fund’s constraints and long-term objectives

## Black-Litterman Portfolio:
- Another approach to portfolio allocation is the Black–Litterman model, which incorporates investor views. Before applying the model, a prior (equilibrium) return must be derived, typically based on market capitalisation weights representing a passive portfolio. These implied returns reflect the market’s consensus: 

$$
E(r)_{\text{implied}} = \lambda \Sigma w^* + r_f
\quad \text{where} \quad
\lambda = \frac{E(r_M) - r_f}{\sigma_M^2}
$$

- Investor views are then used to adjust these implied returns, resulting in adjusted expected returns, which are used for portfolio optimisation:

$$ E(r)_{\text{adjusted}} = E(r)_{\text{implied}} + \theta \delta $$

- In practice, it is not always possible to find a vector 𝛿 that exactly reproduces the investor’s views, particularly when multiple views are imposed simultaneously. In such cases, solver in Excel is used to minimise the difference between the model-implied returns and the investor’s specified views, ensuring the best possible fit.
Once the  $E(r)_{\text{adjusted}}$ are obtained, the Black–Litterman portfolio weights can be constructed as follows:

$$ w = \frac{\Sigma^{-1}\big(E(r)_{\text{adjusted}} - r_f\big)}{\mathbf{1}^T \Sigma^{-1}\big(E(r)_{\text{adjusted}} - r_f\big)} $$

- Note:
  + $E(r)_{\text{implied}}$ is an N×1 vector of implied equilibrium returns
  + $\lambda$ is the market risk aversion coefficient
  + $\Sigma$ is N×N variance–covariance matrix of asset returns
  + $w^*$ is N×1 vector of market (equilibrium) portfolio weights
  + $r_f$ is the risk-free rate  
  + $E(r_M)$ is the expected return of the market portfolio
  + $\sigma_M$ is the variance of the market portfolio
  + $E(r)_{\text{adjusted}}$ is an $N \times 1$ vector of adjusted expected returns
  + $\delta$ is an Nx1 vector representing the adjustments  
  + $\theta$ is an NxN matrix with elements: $$\theta_{i,j} = \frac{\mathrm{Cov}(r_i, r_j)}{\mathrm{Var}(r_j)} $$
  + $w$ is an $N \times 1$ vector representing the portfolio weights   
  + $\Sigma^{-1}$ is the inverse of the $N \times N$ covariance matrix
  + $\mathbf{1}^T$ is a $1 \times N$ row vector of ones  

- Denoting the market capitalisation-weighted portfolio and the Black–Litterman portfolio as 
P3 and  P4, respectively, the asset weight allocations for the two portfolios are as follows:

<p align="center">
  <img width="176" height="183" alt="image" src="https://github.com/user-attachments/assets/6a9288f8-eabc-4611-9a3d-c8351349aa47" />
  <img width="177" height="183" alt="image" src="https://github.com/user-attachments/assets/73b843e8-79fc-4a60-ad96-849a12e7f1d4" />
  <img width="111" height="183" alt="image" src="https://github.com/user-attachments/assets/ebb2e5e8-8a36-406a-b65f-d101dfc299bd" />
</p>

<img width="804" height="183" alt="image" src="https://github.com/user-attachments/assets/3b59924e-8cc6-41aa-83c7-4130345c17f4" />

- GLD sees the largest reallocation (+10.99%) despite only a modest +0.07% upward revision, as its low correlations with the rest of the portfolio (0.13–0.34 with equities, slightly negative with USO) mean the optimiser can improve risk-adjusted returns efficiently with even a small nudge to its expected return, whih is consistent with gold's real-world role as a geopolitical hedge. As the dominant market cap weight with no explicit view imposed, VOO is the path of least resistance for reallocation toward defensive assets, explaining its significant reduction of -8.54%. GBTC's weight increases only marginally (+0.15%) despite a +0.15% view, reflecting its extreme volatility and erratic correlation structure, which causes the BL framework to dampen the tilt. USO's reduction is similarly muted (−0.13pp) due to its already small initial weight, limiting further cuts, and its high correlations with VOO and VGK (0.97 and 1.20), meaning the bearish view is partially expressed indirectly through those equity reductions. IYR and VGK decline modestly as collateral rebalancing effects. Overall, compared to P3, P4 is a risk-off and hedge-tilted portfolio where the magnitude of each shift is driven not just by the views themselves, but by each asset's volatility and correlation structure, which is precisely the value BL adds over a naive return adjustment.

## Combining Optimal Risky with Risk Free Bond:
- Having constructed the optimal risky portfolio P2, the next idea is to build a complete portfolio P5, which combines P2 with a risk-free asset, specifically, a zero-coupon government bond. This combination is motivated by the two-fund separation theorem, which states that any investor, regardless of their risk preference, can achieve their optimal allocation by holding a combination of the single optimal risky portfolio and the risk-free asset.
- Additionally, the zero-coupon structure guarantees a known return over the full holding period with no intermediate cash flow uncertainty, providing a clean and unambiguous risk-free rate for constructing the Capital Market Line. Incorporating the risk-free bond also introduces a capital preservation mechanism that pure equity or alternative asset portfolios cannot provide, particularly important given UE's fiduciary responsibility to protect the endowment's principal during periods of market stress.
- Data:
  + Bond market data as of 31/12/2024.
  + Semi-annually.

## Reference:
