## AI Use Disclosure

### Tools Used
- **Claude Sonnet** (Anthropic)
- **Perplexity AI**

---

### How It Was Used

#### Code Generation and Debugging (Claude)

Claude was used to debug functions (e.g. Tronscan and Binance P2P API, statistical tests) and to write functions for visualizations across the notebook.

Representative prompts included:

- *"Debug this function to fetch USDT-TRC20 transfer fees from the Tronscan API and convert SUN to USD via CoinGecko"*
- *"Fix the stacked bar chart so Layer 3 uses php_spread_best, php_spread_pct, and php_spread_worst instead of the same value for all three scenarios"*

---

#### Fee and Pricing Research (Perplexity + Claude)

Perplexity and Claude were used to attempt to retrieve current fee schedules and live transfer quotes for traditional payment providers. 

- **Wise** - The fee break down tool from Wise was provided as a source in Perplexity. 

- **Western Union** - The flat transfer fee was sourced via Perplexity and verified against the Western Union quote tool. The FX rate reflects the rate quoted at the time of the exercise and is used to compute the FX markup against the mid-market rate.

- **Remitly** - Perplexity was unable to return a reliable, current fee quote for Remitly on the US-Philippines corridor. A central estimate of 2.0% was assumed based on the general range cited in industry sources (1-3% FX markup)


### Quality Assurance and Troubleshooting

- **PHP spread scenario modelling:** Claude initially suggested using 0.5x/1x/2x multipliers of the median spread to define best/central/worst cases. This was identified as methodologically unsound and replaced with percentiles (75th, 50th, 25th). 

- **Wise cost inconsistency:** Claude initially retrieved 1.10% for Wise, inconsistent with the verified live quote of 1.325%. 

- **Western Union recipient table:** Claude retrieved 4.5% for Western Union in the PHP received table rather than using the live-computed `wu_total_pct` variable. This was corrected for consistency.
