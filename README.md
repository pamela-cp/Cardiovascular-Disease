# Portfolio-Optimization

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](
https://colab.research.google.com/github/pamela-cp/Portfolio-Optimization/blob/main/notebooks/MV_Performance.ipynb)

Mean-Variance | Normalised Semi-Variance | Minimum-Information MV | Rolling Windows

This project compares three portfolio optimisation frameworks implemented over rolling estimation windows to evaluate their performance, stability, and allocation behaviour under realistic constraints.

**Optimisation Frameworks**

1️⃣ Mean-Variance (MV)

Classical Markowitz optimisation using expected returns and covariance matrix.

- Objective: maximise Sharpe ratio / minimise variance for target return
- Sensitive to estimation error
- Serves as the benchmark model

2️⃣ Normalised Semi-Variance (NSMV)

A downside-risk-aware alternative using semi-variance instead of total variance.

- Penalises negative returns only
- Captures asymmetric risk preferences
- Produces more conservative allocations during volatile regimes

3️⃣ Minimum-Information Mean-Variance (MIMV)

A robust framework that controls estimation error by minimising the information footprint of portfolio weights.

- Reduces extreme weight concentration
- Improves out-of-sample stability
- Ideal for noisy return environments

**Methodology**

1. Load six Fama–French portfolios (Size × Book-to-Market)
2. Clean & normalise the dataset
3. Implement optimisation frameworks:
   - Mean-Variance
   - Semi-Variance (downside only)
   - Information-Regularised MV

4. Use a rolling window (36, 60, 120 months) to compute:
   - Annualised return
   - Volatility
   - Sharpe ratio
   - Portfolio turnover
   - Weight stability

5. Compare strategies in a unified results dashboard

**Key Results (Summary)**

- MIMV delivers the most stable allocations and lowest turnover
- NSMV protects better during negative market regimes
- MV performs well in-sample but weakens out-of-sample
- 60-month window achieves best balance between responsiveness and estimation precision
