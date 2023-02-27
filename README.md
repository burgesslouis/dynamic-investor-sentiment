# dynamic-investor-sentiment
Indices from Burgess, Chen, and Zhang (2023), "A dynamic model of investor sentiment".


## Abstract 
We propose a dynamic measure of market sentiment, extending Baker and Wurgler
(2006)’s index on the basis that aggregate sentiment must cover a wide range of investors
or investment activities; such aggregation must adapt to changes in how different sen-
timent indicators reflecting sentiment; and the aggregation must not be informed by
future information. We demonstrate that each basis has a specific impact. Ignoring
these points when constructing models of sentiment can cause empirical effects to be
over- or under-estimated and constrain the usability of the modelled sentiment in prac-
tical applications. We test our index against fourteen anomaly portfolio returns and
confirm the classic sentiment-induced mispricing effect on short or hard-to-value legs,
while observing increasing sentiment-induced mispricing on the long or easier-to-value
legs post-2000.

## Included data
### DE-BW Index
The main index used in the paper analysis, it follows Baker and Wurgler (2006)'s index methodology with the following changes:
- Added to the pool of sentiment indicators used to fit the PCA are
  - VIX: CBOE market volatility index.
  - VOL: S\&P500 Trading volume.
  - NHNL: New highs to new lows. 
  - DEBT: Change in margin borrowing.
  - AD: Advances to declines ratio. 
  - TRIN: Trading (Arms) index.
- Instead of using each variable and its twelve-month lag, the variable and its one-month lag is used for the PCA.
- The PCA is conducted in a ten-year rolling-window.
