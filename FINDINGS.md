# Stablecoin Remittance Cost vs. World Bank RPW: US → Philippines

## Best Estimate and RPW Comparison

The end-to-end cost of sending \$200 via USDT-TRC20 from the US to the Philippines is estimated to be **1.18% in the best case, 2.27% in the central case, and 6.93% in the worst case** of the transfer amount. The central case represents a sender using Coinbase Advanced to buy USDT and a median Binance P2P seller on the Philippine side has a fee of approximately **\$4.54** on a $200 transfer.

The RPW database states that the US-Philippines corridor cost was **5.27%** as of Q4 2025. This value represents a weighted average across banks and money transfer operators (MTOs) while the historical average across all available data (2011-2020) is **6.01%**.

The stablecoin central estimate therefore **undercuts the RPW corridor average by ~3 percent**, meeting the UN Sustainable Development Goal target of ≤ 3%. However, this comparison comes with some asterisks. The RPW figure includes the FX spread in the exchange rate, a cost often unseen by the sender. On the other hand, the stablecoin estimate was made using a bottom-up approach using live data. This inherently brings uncertainty, especially on the off-ramp leg. But, the best digital money transfer services tell a different story: Wise charges approximately 1.33% all-in on this corridor, which means the stablecoin central case is actually **more expensive than Wise**, and only competitive in the best-case scenario.

---

## What Was Measured and What Was Not

**Measured components:**

- **On-ramp cost (Layer 1):** CEX trading fees were sourced from published Kraken and Coinbase fee schedules. The range of 0.41% - 3.99% reflects variation in how a US sender might acquire USDT.
- **Network fee (Layer 2):** Gas fees were fetched live from the Tronscan API across 20 recent USDT-TRC20 transactions. Fees are near-zero on TRON (~\$0.00 - $0.01), which is essentially negligible.
- **Off-ramp spread (Layer 3):** The USDT/PHP spread was estimated from live Binance P2P order book data, anchored to the mid-market rate from the Frankfurter FX API. Best, central, and worst cases were calculated from the 75th, 50th, and 25th percentiles of observed seller prices respectively.
- **Cash-out fee (Layer 4):** A range of 0% - 1% was applied, which modeled scenarios from a recipient already having a crypto wallet to one requiring a third party service to disburse funds.

**Unmeasured/Poorly measured components:**

- **Recipient-side liquidity risk:** The Binance P2P spread is observed at a point in time. However, it is important to note that P2P order books are dependent on time of day. For instance, a sender initiating a transfer at off-peak hours may experience a greater spread than the median. This was partially addressed through scenario analysis but not formally quantified.
- **Counterparty and settlement risk:** As with any monetary transaction, there is always the risk of delays, dispute, or fraud. The impacts of failed transfers (e.g. time, resubmission fees, etc.) were not found in datasets. 
- **Wallet acquisition and KYC cost:** Setting up a compliant crypto wallet in the Philippines may require security measures, which requires wait time as well as stable internet connection. While there are economic implications to this, there is no market price.
- **FX timing risk:** USDT is pegged to \$1.00 but trades at a small discount/premium on secondary markets. In real time, this deviation is unobserved.

---

## Data Sources to Fill Gaps

**Household + demand-side surveys** could be used to measure the end to end user experience. The World Bank's Global Findex database and GSMA's Mobile Money consumer surveys capture remittance behaviour, but do not track crypto usage. A targeted survey of workers of Filipino origin in the US, potentially conducted alongside employment agencies (ex. Philippine Overseas Employment Administration) could shed light on the actual share using stablecoin rails, the spread they observe, and the time cost of the off-ramp process.

**Central bank and regulatory data** could complement gaps but through the supply side. The Philippines Central Bank (Bangko Sentral ng Pilipinas. BSP) publishes quarterly remittance inflow statistics disaggregated by channel. If crypto-based inflows were classified and reported separately, this change could provide a baseline for volume and implied costs. However, this would require regulatory approval.

**Payment system statistics from P2P platforms** are the most proximate gap-filler. Binance and other exchanges hold the full distribution of P2P transaction prices, volumes, and settlement times. This data is not publicly available, but an agreement similar to that made with the Bank for International Settlements could be made in order to investigate interchange fees more thoroughly.   

By combining survey-measured user cost, regulator-reported channel volumes, and platform-level transaction data, the study would go from a bottom-up into a more statistically rigorous and reproducible corridor cost series comparable to that of the RPW methodology. 
