# ICT Sniper X — Adaptive Trading Strategy

> **Precision. Discipline. Execution.**

ICT Sniper X is a TradingView Pine Script strategy built around Inner Circle Trader (ICT) concepts and Smart Money Concepts (SMC). It combines market structure, liquidity analysis, price imbalances, higher-timeframe context, and configurable risk management into a structured trading framework.

The project aims to make ICT/SMC-based trading rules systematic, testable, and easier to evaluate through historical market data.

**Project status:** Under development and validation. Profitability, execution reliability, and repainting behavior must be independently tested before live use.

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Strategy Concepts](#strategy-concepts)
- [How It Works](#how-it-works)
- [Getting Started](#getting-started)
- [Using TradingView](#using-tradingview)
- [Backtesting and Validation](#backtesting-and-validation)
- [Risk Management](#risk-management)
- [Project Structure](#project-structure)
- [Roadmap](#roadmap)
- [Limitations](#limitations)
- [Disclaimer](#disclaimer)
- [Author](#author)

## Overview

ICT Sniper X is designed to bring multiple ICT/SMC concepts into one configurable strategy rather than relying on a single indicator or isolated price pattern.

The strategy evaluates market structure, liquidity events, imbalances, order-block areas, and higher-timeframe context to identify potential trading opportunities. It also incorporates configurable trade management and risk controls.

The project is intended for:

- Traders researching systematic ICT/SMC strategies.
- Pine Script developers interested in strategy design and backtesting.
- Quantitative trading enthusiasts exploring rule-based market analysis.
- Developers looking to extend a TradingView strategy into a larger research or execution system.

## Features

### Market Structure and Price Action

- Break of Structure (BOS) detection.
- Change of Character (CHoCH) analysis.
- Liquidity sweep identification.
- Fair Value Gap (FVG) and Inverse Fair Value Gap (IFVG) analysis.
- Order-block identification.
- Premium and discount zone analysis.

### Multi-Timeframe Analysis

- Higher-timeframe market context.
- Daily and four-hour reference data.
- Configurable analysis and execution parameters.
- Historical-data handling designed to reduce lookahead bias.

### Trade Management

- Long and short strategy conditions.
- Stop-loss and take-profit orders.
- Risk-based position-sizing logic.
- Maximum position-quantity controls.
- Configurable trade and loss limits.
- Cooldown controls.
- Optional breakeven and trailing-stop management.

*Feature behavior depends on the implementation and the selected inputs. Each feature should be verified in TradingView before being relied upon.*

## Strategy Concepts

| Concept | Purpose |
|---|---|
| BOS | Identifies a break of a relevant market-structure level. |
| CHoCH | Highlights a potential change in market behavior. |
| Liquidity sweeps | Detects price movement through relevant liquidity levels. |
| FVG / IFVG | Identifies price imbalances and related zones. |
| Order blocks | Marks potential reaction areas associated with price displacement. |
| Premium / discount | Provides context for price location within a range. |
| Higher-timeframe analysis | Adds broader market context to lower-timeframe setups. |
| Risk management | Defines position sizing and trade-exit parameters. |

These concepts are analytical frameworks, not guarantees of institutional order flow or future price movement.

## How It Works

The intended strategy workflow is:

1. **Market data:** Read the chart's OHLCV data.
2. **Market context:** Evaluate relevant structure and higher-timeframe information.
3. **Liquidity and imbalance analysis:** Identify potential sweeps, FVGs, and order-block areas.
4. **Setup evaluation:** Assess the configured entry conditions and filters.
5. **Risk calculation:** Determine trade parameters and intended position size.
6. **Order simulation:** Submit strategy orders for historical or real-time chart evaluation.
7. **Trade management:** Apply configured stop-loss, take-profit, and optional trade-management rules.
8. **Performance evaluation:** Review results in TradingView Strategy Tester.

A detected setup is not a guarantee that an order will execute at the expected price.

## Getting Started

### Requirements

- A TradingView account with access to Pine Editor and Strategy Tester.
- The ICT Sniper X `.pine` source file from this repository.
- A chart symbol and timeframe appropriate for your research.
- Familiarity with strategy settings, order simulation, and risk management.

### Installation

1. Open the [ICT Sniper X repository](https://github.com/shagarithvik/ICT-Sniper-X).
2. Open the Pine Script source file.
3. Copy the complete script.
4. Open [TradingView](https://www.tradingview.com/chart/).
5. Open **Pine Editor**.
6. Paste the script into the editor.
7. Save the script.
8. Select **Add to chart**.
9. Resolve any compilation errors before evaluating the strategy.

Alternatively, clone the repository:

```bash
git clone https://github.com/shagarithvik/ICT-Sniper-X.git
cd ICT-Sniper-X
```

Open the `.pine` file in your preferred code editor.

## Using TradingView

After adding the script to a chart:

1. Open the strategy's settings.
2. Review every available input and risk parameter.
3. Confirm the chart symbol, timeframe, and data feed.
4. Open **Strategy Tester**.
5. Review the trade list, equity curve, drawdown, and performance statistics.
6. Repeat the evaluation across different historical periods and market conditions.

Start with historical testing and paper trading. Do not assume that a successful backtest guarantees equivalent live results.

## Backtesting and Validation

A strategy should be evaluated using repeatable tests rather than selected profitable examples.

### Metrics to Record

| Metric | What it measures |
|---|---|
| Net profit | Total simulated profit or loss after configured costs. |
| Profit factor | Gross profit divided by gross loss. |
| Maximum drawdown | Largest peak-to-trough decline in the equity curve. |
| Win rate | Percentage of closed trades that were profitable. |
| Expectancy | Average expected result per trade. |
| Number of trades | Size of the sample supporting the results. |
| Average win/loss | Typical magnitude of profitable and losing trades. |

### Recommended Testing Process

- **Compilation:** Confirm that the script compiles without errors.
- **Historical testing:** Evaluate a sufficiently broad period.
- **Out-of-sample testing:** Reserve unseen data for evaluation.
- **Market variation:** Test different volatility and trend conditions.
- **Execution costs:** Configure realistic commissions and slippage.
- **Robustness:** Check whether results depend heavily on a particular input value.
- **Repainting checks:** Compare historical signals with signals observed in real time.
- **Paper trading:** Validate behavior without risking real capital.

Record the symbol, timeframe, date range, configuration, and test results for every experiment. No performance figures are claimed in this README.

## Risk Management

ICT Sniper X includes configurable risk-management mechanisms, but their presence does not eliminate trading risk.

Before using the strategy, verify:

- Position sizing against the instrument's contract specifications and account currency.
- Stop-loss and take-profit behavior on gaps and rapid price movements.
- Maximum trade quantity and exposure.
- Daily or session-based loss limits, where configured.
- Commission, spread, and slippage assumptions.
- Whether simulated order fills resemble the intended execution environment.

Risk percentages, quantities, and thresholds should be configured deliberately. Never assume a default setting is suitable for your account.

## Project Structure

The repository's Pine Script file is the primary strategy implementation.

```text
ICT-Sniper-X/
├── ICT_Sniper_Pro_fixed_claude_1.pine
└── README.md
```

The tree above is illustrative; update it to match the actual repository contents if filenames or supporting files change.

## Roadmap

The following are development and validation goals, not claims that every item is already complete.

- [ ] Verify compilation in TradingView Pine Editor.
- [ ] Validate all entry and exit conditions.
- [ ] Audit alert behavior and order-fill notifications.
- [ ] Test multi-timeframe logic for repainting and lookahead issues.
- [ ] Validate position sizing across supported instrument types.
- [ ] Produce reproducible Strategy Tester reports.
- [ ] Perform out-of-sample and parameter-sensitivity testing.
- [ ] Improve chart annotations and debugging visibility.
- [ ] Expand documentation with verified examples and screenshots.
- [ ] Evaluate external execution integration only after strategy validation.

## Limitations

- ICT/SMC concepts can be subjective and may behave differently across markets.
- Backtest results depend on the data feed, timeframe, strategy settings, and fill assumptions.
- Historical performance does not establish future profitability.
- Pine Script strategy execution is not equivalent to a fully autonomous broker-connected trading service.
- Alerts, webhook delivery, broker integration, and live order execution require separate configuration and validation where applicable.

## Disclaimer

ICT Sniper X is provided for educational, research, and software-development purposes only.

This project does not provide financial, investment, or trading advice. It does not guarantee profits or prevent losses. Trading financial instruments, including leveraged products and cryptocurrencies, involves substantial risk and may result in the loss of some or all of your capital.

Always conduct independent testing, understand the strategy's limitations, and use a simulated environment before considering live trading. You are responsible for your trading decisions and any use of this software.

## Author

**Rithvik Shaga**

- GitHub: [@shagarithvik](https://github.com/shagarithvik)
- Repository: [ICT Sniper X](https://github.com/shagarithvik/ICT-Sniper-X)

---

**ICT Sniper X — Precision. Discipline. Execution.**
