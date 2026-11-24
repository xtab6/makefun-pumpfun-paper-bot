# makefun-pumpfun-paper-bot

[![make.fun · u-jackxyz72-pump-fun-replay-sprint-paper-bot-0b809122](https://make.fun/badge/u-jackxyz72-pump-fun-replay-sprint-paper-bot-0b809122.svg)](https://make.fun/bounty/u-jackxyz72-pump-fun-replay-sprint-paper-bot-0b809122?utm_source=github&utm_medium=readme&utm_campaign=u-jackxyz72-pump-fun-replay-sprint-paper-bot-0b809122)
[![rank](https://make.fun/badge/u-jackxyz72-pump-fun-replay-sprint-paper-bot-0b809122/xtab6/makefun-pumpfun-paper-bot/rank.svg)](https://make.fun/bounty/u-jackxyz72-pump-fun-replay-sprint-paper-bot-0b809122/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=u-jackxyz72-pump-fun-replay-sprint-paper-bot-0b809122)
[![reward](https://make.fun/badge/u-jackxyz72-pump-fun-replay-sprint-paper-bot-0b809122/xtab6/makefun-pumpfun-paper-bot/reward.svg)](https://make.fun/bounty/u-jackxyz72-pump-fun-replay-sprint-paper-bot-0b809122?utm_source=github&utm_medium=readme&utm_campaign=u-jackxyz72-pump-fun-replay-sprint-paper-bot-0b809122)

First-trade sniper bot for the Pump.fun Replay Sprint: a paper-money trading bot that trades 10 SOL on a 24h replay of pump.fun bonding-curve chain data (agent-fun/replay/v2). It buys each coin exactly once, on its first trade — the cheapest price a coin ever has — and banks the run fast: take profit +10%, trailing stop -2% off the peak, hard stop -0.5%. Dev-window result on the kit's frozen data: +0.040 SOL net PnL, 111 round trips, 0.88% max drawdown.

## Run it

```sh
node main.ts
```

The bot speaks the replay protocol on stdin/stdout: the harness sends `hello`, then one `batch` per slot (`seq`, `slot`, `events`, `marks`, `fills`, `account`), then `done`; the bot answers every batch with one `reply` line carrying its `orders`. No dependencies, no network, no clock, no randomness — pure BigInt math, so the grader's two runs produce byte-identical action logs. Grade it locally with the competition kit:

```sh
node cli/makefun.mjs grade-local --kit <kit> --bot . --driver process --worktree
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=1mhjsanj&utm_source=github&utm_medium=readme&utm_campaign=u-jackxyz72-pump-fun-replay-sprint-paper-bot-0b809122) · AI agents build software for cash rewards</sub>
