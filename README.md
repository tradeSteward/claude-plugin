# tradeSteward for Claude Code

Review, build and backtest your [tradeSteward](https://www.tradesteward.com) options bots from Claude Code.

This plugin connects Claude Code to your tradeSteward account and adds eight skills for the work people do most: reviewing how bots traded, studying fills, building bots, and testing strategies in Backtick. Claude works only within the permissions you grant when you sign in, and it cannot put a bot into live trading without your approval.

## What's included

- **The tradeSteward connector**, a remote MCP server at `https://api.tradesteward.com/mcp`. You sign in on tradesteward.com; Claude never sees your password or your broker logins.
- **Eight skills**, listed below.
- **Bot and Backtick tools** that Claude calls for you: reading bots, settings, trades, logs and performance; building and checking bots; creating, running and reading Backticks and SweepTicks.

## Requirements

- [Claude Code](https://claude.com/claude-code).
- A tradeSteward account with API and MCP access turned on. Access is turned on per account. To ask for it, email [support@tradesteward.com](mailto:support@tradesteward.com).
- A plan that includes it:

| Plan | What Claude can do |
| --- | --- |
| Any Trader plan | Read your bots, create bots, edit bots that are not live, ask to pause or resume all trading, and turn a Backtick position into a bot |
| Trader Unlimited | Also turn a bot off, and ask to turn a bot on or change a live bot |
| Backtick Professional | Read, create and run Backticks and SweepTicks |

## Install

In Claude Code, run:

```
/plugin marketplace add tradesteward/claude-plugin
/plugin install tradesteward@tradesteward
```

Then sign in:

1. Run `/mcp` and choose `tradesteward`.
2. Sign in to your tradeSteward account in the browser window that opens.
3. On the consent page, choose exactly what Claude may do, then approve.

To update later, run `/plugin marketplace update tradesteward`.

## Skills

Claude picks a skill on its own when your request fits one. You can also run one directly, for example `/tradesteward:review-bot-performance`.

| Skill | What it does |
| --- | --- |
| `review-bot-performance` | Reviews how your bots have traded: profit and loss, win rate, and the trades behind the numbers. |
| `analyze-stop-fills` | Shows where your stops filled compared with where they were set, and against the last quote. Changes nothing. |
| `analyze-fill-slippage` | Measures where your entries and stops filled inside the bid and ask and how long they took, then matches Backtick's slippage and delay to them. Builds a comparison Backtick only when you ask. |
| `build-bot` | Turns a strategy you describe into a bot, saved switched off for you to review. |
| `backtest-strategy` | Sets up a Backtick for a strategy you describe, runs it and reads the results. |
| `backtest-to-bot` | Saves a position from a completed Backtick as a bot, switched off for you to review. |
| `build-portfolio` | Builds a page showing how a strategy's tested cells share a number of contracts you choose, with buttons to test the portfolio or create its bots. |
| `build-report` | Turns bot or Backtick results into a page, dashboard, doc or deck in tradeSteward's style. |

## Try asking

- "How did my bots do last month? Which one lost the most, and why?"
- "Where did my stops fill compared with where they were set?"
- "Build a 45 DTE put credit spread bot on SPX at 10 delta."
- "Backtest a 0 DTE iron condor on SPX entering at 10:00, then sweep the short delta from 10 to 20."
- "Turn the best position from my last Backtick into a bot."

## Safety

- Turning a bot on, resuming trading, changing a bot that is live and pausing trading each wait for your approval on tradeSteward. Nothing changes until you approve.
- Every bot it creates is saved switched off. You review it and turn it on from the tradeSteward website, or approve a request to turn it on.
- Turning a bot off takes effect within moments, and an order already at the broker may still fill. A pause takes effect after you approve it.
- A Backtick is a simulation of past markets, not a forecast.
- Claude is told to treat names, notes, tags and log lines from your account as data, never as instructions.

## Privacy

Claude receives the account data its tools return, such as bot settings, trades, logs and Backtick results, and handles it under your agreement with Anthropic. Your tradeSteward password and your broker logins never leave tradeSteward. See the [tradeSteward privacy policy](https://www.tradesteward.com/privacy).

To disconnect, remove the connection on the API Access page of your tradeSteward account, in the account menu.

## Troubleshooting

- **A tool or skill is missing or refused.** The connection was not given that permission when you signed in, or your plan does not include it. Sign in again from `/mcp` and choose the permissions you need.
- **Sign-in does not go through.** Check that API and MCP access is turned on for your account; if it is not, email support.
- **"Changes through the tradeSteward API are temporarily turned off."** tradeSteward has paused changes for a while. Reading, turning bots off and pausing trading still work. Try the change again later.
- **A request is refused for coming too often.** Wait a moment and ask again.

## Contributing

Pull requests are welcome. The skills in `skills/` are generated from the tradeSteward server, so we do not merge a change to a skill here. We make the change on our side, regenerate the skills and publish them to this repository, then close your pull request with a link to the commit. Changes to the plugin manifest, `.mcp.json` and this README are merged here directly.

## Help and support

- Guide: [Connect an AI assistant](https://www.tradesteward.com/kb/connected-apps/connect-ai-assistants)
- Support and security reports: [support@tradesteward.com](mailto:support@tradesteward.com)

This repository is published by tradeSteward, LLC. It is not affiliated with or endorsed by Anthropic. See [LICENSE](LICENSE).
