# Literature Review

The relationship between stock market crises and rising correlation among
constituent stocks is a well-established phenomenon in financial econophysics
and quantitative finance literature. This project builds on, rather than
extends, this existing body of work — applying established clustering and
correlation techniques to a focused 20-stock US large-cap universe across the
2008 Global Financial Crisis and 2020 COVID crash.

Gao and Mei (2019) analyzed correlation structure between US and Asian stock
markets around the 2008 financial crisis, using linear correlation, mutual
information, and transfer entropy to quantify how market dependence shifted
between pre- and post-crisis periods. Their approach of comparing distinct
crisis and non-crisis windows directly parallels the methodology in this
project: stocks (particularly BAC, JPM, and WFC) that showed no distinct
grouping in the calm 2007 period separated into a clearly defined,
high-volatility cluster by the peak of the 2008 crisis.

More broadly, Sandoval and Franca (2012) demonstrated, using eigenvalue and
eigenvector analysis of correlation matrices across major global market
indices, that periods of high market volatility are directly linked with
strengthening correlations between assets — markets effectively "behave as
one" during major crashes, a pattern they confirmed across four historical
crises from 1987 to 2008. This project's central metric, average pairwise
correlation across all 20 stocks, is a direct operationalization of that
finding, and its validation against the VIX (a 0.604 correlation across
3,967 trading days) provides independent support for the same conclusion.

Jaroonchokanan, Termsaithong, and Suwanna (2022) extended this line of
research using Fisher information distance alongside correlation on Thai
stock market data across crises from 2008 to 2020, finding that Fisher
information provided earlier and more robust crisis signals than correlation
alone. This represents a meaningful limitation of the present project's
approach: correlation-based signals, while intuitive and easy to interpret,
are not necessarily the most statistically robust or earliest available
indicator, and future extensions of this work could incorporate
information-theoretic measures for comparison.

Where this project differs methodologically from most of the cited
literature is its use of K-means clustering on engineered rolling features
(volatility, mean return, correlation) rather than hierarchical or
network-based clustering directly on correlation matrices, as is more common
in this literature. This was a deliberate choice for interpretability and
computational simplicity given the project's scope, though it means the
results here should be read as a proof-of-concept replication of known
phenomena using an accessible method, rather than a methodological
contribution in its own right.

## Future Work

This project is scoped as a proof-of-concept portfolio piece, not a novel
research contribution. Possible extensions that would push it toward
genuine research-level rigor include:

- **Benchmarking against alternative clustering methods** (e.g. hierarchical
  clustering, or the Fisher information distance approach used by
  Jaroonchokanan et al.) rather than relying on K-means alone.
- **Statistical significance testing** of the correlation spikes observed
  (e.g. bootstrapped confidence intervals, or comparison against a null
  model of randomly shuffled returns) rather than relying on descriptive
  statistics alone.
- **Broader dataset**: more markets (not just US large-caps), and more
  crisis events (e.g. 2011 European sovereign debt crisis / US debt ceiling
  crisis, which shows a clear unexplained spike in this project's own
  correlation timeline — see `outputs/figures/crisis_signal_timeline.png`).
- **Predictive framing**: testing whether the correlation signal could have
  flagged crises before they were obvious in headlines or the VIX, via
  out-of-sample or early-warning-style evaluation, rather than only
  describing known crisis windows retrospectively.

## References

Gao, H.-L. and Mei, D.-C. (2019). The correlation structure in the
international stock markets during global financial crisis. *Physica A:
Statistical Mechanics and its Applications*, 534.

Jaroonchokanan, N., Termsaithong, T., and Suwanna, S. (2022). Dynamics of
hierarchical clustering in stocks market during financial crises. *Physica
A: Statistical Mechanics and its Applications*, 607.

Sandoval, L. and Franca, I. De P. (2012). Correlation of financial markets
in times of crisis. *Physica A: Statistical Mechanics and its Applications*,
391(1), 187-208.
