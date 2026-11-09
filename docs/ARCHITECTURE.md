# TraDex architecture v1.0

## Runtime
A local-first Python application running on a laptop with 16 GB system RAM and 8 GB NVIDIA VRAM. Discord is the primary user interface. No cloud LLM is required.

## Modules
- `core`: scheduling, event coordination and bounded task queue.
- `market`: exchange adapters, closed OHLCV candles, timestamps and data quality.
- `indicators`: deterministic features and technical indicators.
- `strategies`: versioned and testable trading hypotheses.
- `signals`: signal lifecycle, IDs, deduplication and audit trail.
- `risk`: reject stale/invalid data, position and risk checks.
- `backtesting`: fees, slippage, chronological evaluation and benchmarks.
- `ai`: local Ollama model, structured prompts, source-grounded explanations.
- `knowledge`: licensed document ingestion, retrieval and provenance.
- `learning`: optional small ML models, separate from LLM.
- `storage`: SQLite metadata and Parquet market history.
- `discord`: official bot, slash commands, embeds, channel routing and permissions.
- `api`: optional future interface, not required for first Discord release.

## Event flow
Exchange data -> data validation -> indicators -> strategy -> risk gate -> persisted signal -> Discord publisher. AI explanations may enrich output but cannot override the risk gate. Manual Discord commands use the same services as scheduled jobs.

## Discord channels
`#signale`: new validated signals; `#marktanalysen`: scheduled AI reports; `#trade-updates`: lifecycle changes; `#backtesting`: research results; `#ki-chat`: questions; `#bot-status`: health; `#system-logs`: restricted technical events.

## Operating constraints
- One quantized small LLM loaded on demand; CPU-first market processing.
- Single bounded LLM worker and timeouts; Discord remains responsive.
- No real-money execution in initial scope.
- If laptop sleeps or shuts down, Discord bot is offline.
- Discord credentials only in ignored local `.env`; never in repository.

## Data integrity
Closed candles only, UTC timestamps, missing-data checks, strategy versioning, unique signal IDs, and reproducible test runs. No invented confidence scores or backtest results.
