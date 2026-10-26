# Zied-backtest

This repository owns the independent, sequential historical backtest cycle.

## Required behavior
- Discover every eligible OKX Spot USDT pair; exclude stablecoin base assets and never use Futures.
- Process exactly one pair per workflow run.
- When one pair finishes successfully, immediately dispatch the next eligible pair; resume from a persisted checkpoint after interruption.
- Use 10,000 candles and six walk-forward windows, with causal feature generation and no train/test leakage.
- Retry a failed pair a bounded number of times; never mark a failed/empty result as completed.
- Start a new full-universe cycle only after the prior universe has completed.

The workflow is intentionally not active in this rebuild commit pending validation of fresh state and credentials.
