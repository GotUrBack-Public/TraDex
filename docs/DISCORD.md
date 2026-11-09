# Discord integration plan

Use an official Discord application/bot account, not a self-bot. Configure token and channel IDs through local environment variables. Never commit secrets.

## Publishing
- Automatic signal posts to `#signale` only after validation.
- Scheduled market reports to `#marktanalysen`.
- Signal lifecycle messages to `#trade-updates`.
- Health and error messages to `#bot-status`; restricted diagnostics to `#system-logs`.

## Commands (planned)
`/analyse`, `/signals`, `/signalinfo`, `/backtest`, `/ask`, `/status`.

## Safety
Permission-check administrative commands; rate-limit requests; keep logs free of secrets; never present simulated prices as live prices. Bot only runs while the laptop and app are active.
