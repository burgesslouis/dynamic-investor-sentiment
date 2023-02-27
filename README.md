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
### Dynamic and extended Baker-Wurgler (DE-BW) index
The main index used in the paper analysis, it follows Baker and Wurgler (2006)'s index methodology with the following changes:
- We extend the pool of sentiment indicators by adding:
  - VIX: CBOE market volatility index.
  - VOL: S\&P500 Trading volume.
  - NHNL: New highs to new lows. 
  - DEBT: Change in margin borrowing.
  - AD: Advances to declines ratio. 
  - TRIN: Trading (Arms) index.
- Instead of using each variable and its twelve-month lag, the variable and its one-month lag is used for the PCA.
- The PCA is conducted in a ten-year rolling-window, the data in each window is standardised before any decomposition is performed.

### Look-ahead free, or practical (DE-BW-PR) index
A check on the main index, with the knowledge that only certain sentiment indicators are known to researchers and practitioners alike at any one time. So, we create the index which could have practically been constructed following the DE-BW index methodology, but only including each sentiment indicator from when they have been mentioned in publications as representing sentiment.
- Number of IPOs (NIPO) and Return on IPOs (RIPO): 1991
- Closed-end fund discount (CEFD): 1991
- Advance to declines (AD), New highs to new lows (NHNL), and Trading index (TRIN): 1999
- Volatility index (VIX) and Equity share in new issues (ESNI): 2000
- Dividend premium (DIVP): 2004
- Trading volume (VOL): 2004
