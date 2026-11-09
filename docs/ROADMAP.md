# Implementation roadmap

1. **Scaffold**: architecture docs, configuration placeholders, empty module directories (current phase).
2. **Discord foundation**: official bot, health checks, channel IDs, slash commands and permissions.
3. **Market data**: CCXT OHLCV ingestion, local persistence and quality checks for BTC/USDT and ETH/USDT.
4. **Signals**: EMA/RSI baseline, closed-candle evaluation, risk validation, duplicate prevention.
5. **Backtesting**: realistic fees/slippage, time splits, drawdown, buy-and-hold comparison.
6. **AI knowledge**: local Ollama, RAG with source attribution, bounded resource usage.
7. **Scheduled analyses**: automatic reports and interactive Discord analysis commands.
8. **Research**: optional LightGBM, walk-forward testing, paper-trading evaluation.

Each stage needs tests and documentation before merging into `main`. No live execution in this roadmap.
