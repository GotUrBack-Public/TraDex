# TraDex

Local-first crypto trading research and signal platform with an official Discord bot.

## Goals
- Research BTC/USDT and ETH/USDT using reproducible market data and strategies.
- Validate signals with risk checks and historical backtests before publishing.
- Publish automatic analyses and signals to dedicated Discord channels and answer slash commands.
- Run on an MSI laptop (13th-gen Intel Core i5, NVIDIA RTX 8 GB VRAM, 16 GB RAM).

## Status
**Architecture scaffold only.** No trading logic, live signals, Discord integration, or live-order execution is implemented.

## Design principles
- Deterministic signal generation; the LLM explains but does not independently authorize signals.
- Local storage and local LLM via Ollama, with bounded memory use.
- Closed-candle data only; explicit timestamps, data quality checks, deduplication, and audit logs.
- Research and backtesting before paper trading; no real-money orders in the initial scope.
- No API keys, tokens, private data, downloaded models, or large datasets in Git.

See `docs/ARCHITECTURE.md` and `docs/ROADMAP.md` for the proposed design.
