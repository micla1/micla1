# Clara Mihailescu

Quantitative research, ENSAE Paris — quantitative macro research intern (multi-asset), currently
on a gap year. Interested in quantitative research / trading roles in rates, FX, and systematic
strategies.

## What's in this profile

Four independent projects, each following the same discipline: **replicate a published model or
methodology from scratch and public data → validate it numerically against an official benchmark
or a rigorous protocol → build a trading signal or extension on top → report what does and
doesn't work, honestly.** No project claims a result it can't defend.

---

### [hlw-rstar-python](https://github.com/micla1/hlw-rstar-python)
**Replicating the natural rate of interest (r\*), Holston-Laubach-Williams (2023).**
A from-scratch Python port of the Fed's three-stage Kalman-filter state-space model, including
the Stock-Watson median-unbiased estimator that fixes the "pile-up problem" in estimating the
model's signal-to-noise ratios. Validated to within 0.03pp of the officially published λg, λz,
and log-likelihood. Extended with the FRBNY's real-time (vintage) data to quantify r\*'s
end-of-sample instability (~0.9pp average revision), and a no-hindsight rate-gap trading signal
backtested against a duration benchmark.

### [term-premium-python](https://github.com/micla1/term-premium-python)
**Decomposing Treasury yields: ACM and Kim-Wright term premium models.**
Two no-arbitrage affine term-structure models sharing one pricing engine, estimated two different
ways — ACM's closed-form regression on realized excess returns matches the official NY Fed series
almost exactly (correlation ≈ 0.99); Kim-Wright's NLS fit on yield levels alone reproduces the
yield curve just as well but a much weaker term-premium decomposition — an empirical
demonstration of exactly the identification problem the original paper's survey-data anchor
exists to solve. Extended with a recession-prediction test (raw vs. expectations-only yield
spread) and a term-premium mean-reversion signal.

### [cac40-portfolio-python](https://github.com/micla1/cac40-portfolio-python)
**Isolating Σ and μ in mean-variance portfolio construction, CAC 40 equities.**
Companion implementation to a Stat'App research report: comparing four covariance estimators
(empirical, Ledoit-Wolf shrinkage — statistical and economic targets, GARCH) via the Minimum
Variance Portfolio, and four expected-return estimators (empirical, EWMA, Black-Litterman with a
CAPM equilibrium prior, LightGBM) via the tangency portfolio, across four market regimes
(2019 bull / 2020 COVID / 2021 rebound / 2022 rate-stress), both statically and via monthly
walk-forward. Extended with correlation-based clustering that recovers France's banking sector
from price data alone, and an LSTM-vs-GARCH volatility comparison.

### [fx-nlp-black-litterman](https://github.com/micla1/fx-nlp-black-litterman)
**FinBERT sentiment as systematic Black-Litterman views, G10 FX.**
News headlines tagged by currency via central-bank keyword matching, scored with FinBERT,
aggregated into weekly views with confidence proportional to signal strength — no hand-picked
views. Stress-tested three ways: against a Loughran-McDonald lexicon baseline (which turned out
to win — a real, reported finding, not the one I expected); against a block-bootstrap
significance test on the Sharpe differential; and against price momentum, to check the signal
isn't just a lagged restatement of the price.

---

## Notes on how these were built

Every repo's README states plainly which simplifications were made to work with public data (e.g.
an annual instead of monthly holding period where the data didn't support monthly), and every
"doesn't fully match the official benchmark" result is reported and explained rather than hidden.
Where a result contradicted my working hypothesis — the yield-curve recession test, the
FinBERT-vs-lexicon comparison — I've kept and reported it as found.

clara.mihailescu@ensae.fr
