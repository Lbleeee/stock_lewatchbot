# Investment news bot (Telegram)

Watches your stocks, alerts you when news touches the fundamentals, sends a weekly
summary, and answers your questions. It never trades and never tells you to buy or sell.

## Files
| File | What it is |
|---|---|
| `main.py` | The bot. You should not need to edit it. |
| `portfolio.md` | Your policy, holdings and theses. **Edit this one.** |
| `requirements.txt` | The libraries the host installs. |

## Settings (Railway > your service > Variables)
| Variable | Required | Default | Meaning |
|---|---|---|---|
| `TELEGRAM_BOT_TOKEN` | yes | | Token from @BotFather |
| `ANTHROPIC_API_KEY` | yes | | Key from console.anthropic.com |
| `ALLOWED_CHAT_ID` | yes (step 4) | | Your chat ID. The bot ignores everyone else |
| `WATCHLIST` | no | `AVGO:Broadcom,PLTR:Palantir,NVDA:Nvidia,AMZN:Amazon` | Stocks to follow, as `TICKER:Name` |
| `SCAN_MINUTES` | no | `180` | Minutes between news checks (180 = every 3 hours) |
| `WEEKLY_DAY` / `WEEKLY_HOUR` | no | `0` / `18` | Weekly summary: 0 = Sunday, 18 = 6pm |
| `TIMEZONE` | no | `America/Toronto` | |
| `MAX_CLAUDE_CALLS_PER_DAY` | no | `80` | Safety cap on spend |
| `MODEL_FAST` / `MODEL_SMART` | no | `claude-haiku-5-5` / `claude-sonnet-5-5` | Screening / questions and weekly |
| `SHEET_CSV_URL` | no | | Read your Google Sheet tab instead of `portfolio.md` (see below) |
| `WEB_SEARCH` | no | `0` | `1` lets Claude search the web for your questions (extra cost) |

Never put the token or API key in a file or a chat. They live only in Railway Variables.

## Commands
`/status` what it's watching · `/scan` check news now · `/weekly` summary now ·
`/news TICKER` latest headlines · `/help` · or just type a question.

## How the news filter works
Every 3 hours the bot collects new headlines and runs them through two steps:
1. **Sort (cheap model):** each headline is dropped (price moves, analyst targets, opinion pieces),
   kept for the weekly summary (real news that doesn't touch your thesis or rules), or sent to step 2.
2. **Check (smarter model):** reads your thesis and entry/exit rules and alerts you only if the news
   materially strengthens or weakens part of your thesis, triggers or moves toward an A, X or T rule,
   or is one of your R (review) events. Anything that doesn't pass goes to the weekly summary instead.

If step 2 fails, you still get the alert, marked "unverified". `/status` shows how many items are
waiting for the weekly summary. The kept list is cleared after each weekly summary is sent.

## Adding a stock
Change `WATCHLIST` in Railway (for example add `,ENVX:Enovix`) and add the stock and
your thesis to `portfolio.md`.

## Entry and exit rules
Write them in `portfolio.md` under "My entry and exit rules", one line per rule with a
code (A = add, X = exit, T = trim, P = position, R = review, W = warning), the threshold
and the latest value. Copy the PLTR block for a new stock. The bot then:
- adds an "Entry/exit rules" line to every urgent alert, naming the rules a headline touches;
- in the weekly summary, shows each news item with how many entry (A) and exit (X, T)
  conditions it triggers, naming them only when one is triggered; a price crossing one of
  your levels gets its own line;
- uses them when you ask a question.
Update the "Latest" values after each earnings report so the starting point stays right.
The bot reports rule status only. It never trades or tells you what to do.


## Limits to know
- Alerts are judged from **headlines only**. Always read the linked source.
- News comes from Google News and Yahoo Finance feeds. If both stop working, the bot
  tells you instead of going quiet.
- "Immediate" means within `SCAN_MINUTES` of the headline appearing in those feeds.
- After a restart or redeploy, only headlines from the last 3 hours can trigger alerts.
- The weekly price line uses an unofficial Yahoo endpoint and may say "price unavailable".

## Troubleshooting
- Bot silent: Railway > Deployments > View logs. A missing variable is named in the log.
- "Conflict" errors in the log: two copies are running with the same token. Keep one.
- Replies only with your chat ID: `ALLOWED_CHAT_ID` is not set yet.
- `/news AVGO` shows nothing: the host can't reach the news feeds; check the logs.
