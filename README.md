# tradeSteward for Claude Code

Review, build and backtest your tradeSteward options bots from Claude Code.

This plugin adds the tradeSteward connector (a remote MCP server at `https://api.tradesteward.com/mcp`) and eight skills: `build-bot`, `review-bot-performance`, `analyze-stop-fills`, `analyze-fill-slippage`, `backtest-strategy`, `backtest-to-bot`, `build-report` and `build-portfolio`.

## Install

```
/plugin marketplace add tradesteward/claude-plugin
/plugin install tradesteward@tradesteward
```

Then run `/mcp`, choose `tradesteward` and sign in to your tradeSteward account. On the consent page you choose exactly what Claude may do.

## What it can and cannot do

- It can read your bots, their performance, trades and logs, and your Backticks.
- On Trader Unlimited it can also create bots and edit bots that are not live, turn a bot off and pause all trading. The trading engine takes a short time to observe a pause or a bot being turned off, and an order already at the broker may still fill. On the other Trader plans it can only read bots.
- With Backtick Professional it can create and run Backticks.
- It can never turn a bot on, resume trading or change a bot that is live. Bots it creates are saved switched off. You turn them on from the tradeSteward website after reviewing them.

You need a tradeSteward plan that includes API access: a Trader plan for bots (the other Trader plans below Trader Unlimited can only view them), or Backtick Professional for backtesting.

Help: https://www.tradesteward.com/kb/account-billing/connect-ai-assistants
