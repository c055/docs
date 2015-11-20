
| **Constants** | Things that might eventually get a permanent value. |
| --- | --- | 
| **Buy&burn interval** | Currently I think daily blind auction is best suited for this. Multiple parties can coordinate through smart contracts. |
| **Forced inflation interval** | Daily blind auction best solution similar to above. |
| **Forced inflation rate** | Arbitrary, should be set to something marketing friendly, such as 100% per year or 1% per week. |


| **Exogenous variables** | Variables that can be changed externally, includes monetary policy levers. |
| --- | --- | 
| **Insurance Rate** | The proportional increase in debt of CDPs over time. The insurance debt (= total debt - initial debt) is added to the Vault rather than burned when a CDP is covered or redeemed. |
| **Collateral Redemption Curve** | A function that defines the bounty when a CDP is redeemed.|
| **Dai Ideal Price** | Variable defining the zero-point in the Collateral Redemption Curve. Acts as the market signal for the target price below which monetary policy tools are deployed to defend the market price. Set to trail the market price by a delay that depends on the long term volatility of the Dai, with the goal of a steady, permanent increase. Setting delay to 1 year might have some marketing advantages, overall depends on what kind of long term volatility is observed. |
| **Insurance Drain** | Determines the rate of buy&burn in daily blind auctions, targeting a policy determined half life.

| **Endogenous variables:** |  |
| --- | --- | 
| **Dai Market price** | Current Dai trading price. Impacted by everything but most interestingly by insurance rate (positive impact) and price floor (positive impact). |
| **Dai Unrealized Yield** | The current difference between Ideal Price and Market Price. Approximates the expected deflationary yield. |
| **Aggregate Price Floor** | total of all CDP asks arranged as an order book that shows how the dai will absorb irrational volatility. Controlled through the Collateral Redemption Curve and the Dai Ideal Price. Direct positive impact on market price. |
| **Aggregate Collateral** | Total value of the collateral backing outstanding Dai. Indirect positive impact on market price. Direct positive impact on resilience. |
| **Vault Value** | Market cap of the insurance vault. Positively impacted by Insurance Rate and negatively impacted by Insurance Drain. Direct positive impact on resilience. |
| **Insurance Shares market cap** | Market cap of the system’s Insurance Shares (MKR/MakerShares). Direct positive impact on resilience. Controlled through Insurance Rate and Insurance Drain. Positively impacted by vault and insurance drain. Negatively impacted by emergency debt. |


