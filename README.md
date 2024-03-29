# dynamic-investor-sentiment
Indices from Bian, Burgess, Chen, Deng, and Zhang (2023), "Model risk in static aggregation of stock market sentiment".


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

Data for the following indices can be found in the repository [here](sentiment_index_data.csv).

### Dynamic and extended Baker-Wurgler (DE-BW) index
The main index used in the paper analysis, it follows Baker and Wurgler (2006)'s index methodology with the following changes:
- We extend the pool of sentiment indicators by adding:
  - VIX: CBOE market volatility index.
  - VOL: S\&P 500 Trading volume.
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

### The BW index, unorthogonalised 2018 edition, from Baker and Wurgler (2006).
We include the original BW index (the version fit from 1965-2018) to compare to our two indices. Throughout our paper, this index serves as a benchmark to which we compare the incremental impact of our methodological alterations.

### The BW index, orthogonalised 2018 edition, from Baker and Wurgler (2006).
We include the orthogonalised BW index (the version fit from 1965-2018) to compare to our two indices. This index has been orthgonalised to the five macro variables by orthgonalising each proxy which forms the BW index using a linear regression of the form
$$P_t = \alpha + \beta X_t + \varepsilon_t,$$
where $P_t$ is the respective proxy, and $X_t$ is a vector of business cycle variables including growth in industrial production; growth in consumer durables, non-durables, and services; growth in the consumer price index; and NBER recessions. Each orthgonalised proxy is extracted as the residual, $\varepsilon_t$.

## Visual comparison of the data
![DE-BW, DE-BW-PR, and BW indices](sentiment_index_comparison.png)

The above is a plot of the DE-BW index, alongside a ‘practical’ (DE-BW-PR) version, which uses only indicators which have been
identified in the literature by that time. The two versions are both scaled using the standard deviation of the
original DE-BW index, for simple comparison. Additionally, the BW and orthogonalised BW (O-BW) indices are included.
