# Algorithmic Trading API

Backtest, forward tests and deploy trading algorithms and strategies on binance spot, futures and nft markets and other cryptocurrency exchanges, including arbitrage.

- Daily Close Prices
- Daily Logarithmic Returns, Mean Returns
- Tangency Portfolio with optimal weights
- Market Capitalisation
- Annualised Risk σ, Variance and Return
- Correlation Matrix and Covariance
- Systematic & Unsystematic Variance
- Sharpe, beta, CAPM, alpha

## Installation 
```sh
pip install atapi 
```

Run:
```sh
python -m atapi
```
```
Welcome to the Algorithmic Trading API. Type help/? for commands.

atf🖖
```

## Examples (See Wiki for More)
```
atf🖖 help

Documented commands (type help <topic>):
========================================
algorithmic_factory  correlation  marketcap_summary  returns      stats_mcap
assets_close         covariance   mean_returns       servertime   weights_cwi
bye                  help         normalized         stats        weights_ewi
circulating_supply   marketcap    optimal_weights    stats_index  weights_pwi
```
```
atf🖖 help stats
Return, risk, sharpe, variance, systematic variance,
unsystematic variance, beta, CAPM, alpha.
```
```sh
atf🖖 returns
┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃ Log Returns                                                              ┃
┡━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┩
│             BTCUSDT  ETHUSDT  BNBUSDT  XRPUSDT  TRXUSDT  LTCUSDT      TP │
│ Date                                                                     │
│ 2021-02-06   0.0231  -0.0252   0.0731  -0.0204  -0.0328   0.0033  0.0731 │
│ 2021-02-07  -0.0100  -0.0394  -0.0635  -0.0571   0.0253  -0.0314 -0.0635 │
│ 2021-02-08   0.1784   0.0825   0.1553   0.0748   0.1166   0.1040  0.1553 │
│ 2021-02-09   0.0010   0.0108   0.2961   0.0547   0.1311   0.0815  0.2961 │
│ 2021-02-10  -0.0354  -0.0162   0.1835   0.0570   0.0045   0.0004  0.1835 │
    ...          ...      ...     ...      ...      ...      ...      ...
│ 2022-06-15   0.0200   0.0234   0.0464   0.0668   0.1254   0.0930  0.0464 │
│ 2022-06-16  -0.1016  -0.1469  -0.1056  -0.0926  -0.0620  -0.1232 -0.1056 │
│ 2022-06-17   0.0033   0.0171   0.0263   0.0246   0.0111   0.0611  0.0263 │
│ 2022-06-18  -0.0760  -0.0882  -0.0911  -0.0430   0.0166  -0.0089 -0.0911 │
│ 2022-06-19  -0.0455  -0.0516  -0.0325  -0.0240  -0.0116  -0.0411 -0.0325 │
└──────────────────────────────────────────────────────────────────────────┘
```
```sh
atf🖖 correlation
┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃ Correlation Coefficient                                              ┃
┡━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┩
│          BTCUSDT  ETHUSDT  BNBUSDT  XRPUSDT  TRXUSDT  LTCUSDT     TP │
│ BTCUSDT   1.0000   0.8287   0.6883   0.6735   0.6770   0.7961 0.6883 │
│ ETHUSDT   0.8287   1.0000   0.7156   0.7074   0.6884   0.8253 0.7156 │
│ BNBUSDT   0.6883   0.7156   1.0000   0.6458   0.6091   0.7018 1.0000 │
│ XRPUSDT   0.6735   0.7074   0.6458   1.0000   0.7022   0.7758 0.6458 │
│ TRXUSDT   0.6770   0.6884   0.6091   0.7022   1.0000   0.7182 0.6091 │
│ LTCUSDT   0.7961   0.8253   0.7018   0.7758   0.7182   1.0000 0.7018 │
│ TP        0.6883   0.7156   1.0000   0.6458   0.6091   0.7018 1.0000 │
└──────────────────────────────────────────────────────────────────────┘
```
```sh
atf🖖 stats
┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃ Modern Portfolio Theory                                                       ┃
┡━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┩
│          Return   Risk  Sharpe    Var  SysVar  UnsysVar   beta   CAPM   alpha │
│ BTCUSDT -0.5474 0.7652 -0.7559 0.5855  0.6688   -0.0833 0.4148 0.3326 -0.8799 │
│ ETHUSDT -0.4380 0.9741 -0.4815 0.9488  0.8851    0.0637 0.5489 0.4301 -0.8680 │
│ BNBUSDT  0.7580 1.2698  0.5726 1.6124  1.6124    0.0000 1.0000 0.7580  0.0000 │
│ XRPUSDT -0.2999 1.2533 -0.2640 1.5707  1.0277    0.5429 0.6374 0.4944 -0.7943 │
│ TRXUSDT  0.3714 1.1682  0.2913 1.3647  0.9036    0.4611 0.5604 0.4384 -0.0671 │
│ LTCUSDT -0.9010 1.1213 -0.8311 1.2574  0.9993    0.2581 0.6198 0.4816 -1.3826 │
│ TP       0.7580 1.2698  0.5726 1.6124  1.6124    0.0000 1.0000 0.7580  0.0000 │
└───────────────────────────────────────────────────────────────────────────────┘
```
## Development

Run:
```sh
cd atapi
pip install .[dev]
```

## Project 

https://github.com/streetyoga/atapi

## License

[MIT](LICENSE.txt)
