<h1 align="center">I build trading systems — then try to kill them honestly.</h1>

<p align="center">
  <em>Most "edges" are overfit ghosts. The interesting work is proving which ones survive real costs, out-of-sample, forward — and deleting the rest without flinching.</em>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/asyncio-1f6feb?style=flat-square&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/WebSockets-010101?style=flat-square&logo=socketdotio&logoColor=white" />
  <img src="https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white" />
  <img src="https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white" />
  <img src="https://img.shields.io/badge/systemd-FCC624?style=flat-square&logo=linux&logoColor=black" />
  <img src="https://img.shields.io/badge/PowerShell-5391FE?style=flat-square&logo=powershell&logoColor=white" />
  <img src="https://img.shields.io/badge/Hetzner-D50C2D?style=flat-square&logo=hetzner&logoColor=white" />
</p>

---

### 🔬 What I actually do

I run an end-to-end quant loop solo: pull the data, design the strategy, build
the live execution stack, ship it to a server, and — the part that matters —
**stress-test the edge until it either survives or dies.** Most die. That's not
failure, that's the job. A backtest that only ever produces good news is a bug.

My bias: **out-of-sample first, pre-register the hypothesis, walk forward, price
in real costs.** If a result can't survive that, it doesn't get capital.

### 📦 Pinned work

| Repo | What it is |
|---|---|
| **[honest-backtest](https://github.com/Makeph/honest-backtest)** | An edge-validation harness for CME micro futures & prop firms. Famous internal result: it **debunked my own** in-sample "59% pass-rate" as a mirage once tested OOS. Proves an edge or kills it. |
| **[prop-ev](https://github.com/Makeph/prop-ev)** | Monte Carlo for prop-firm challenges: *P(pass)* and whether the attempt is **+EV after the fee**. Spoiler — usually not. Includes a **[live browser calculator](https://makeph.github.io/prop-ev/)**. |
| **[binance-fapi-ws](https://github.com/Makeph/binance-fapi-ws)** | A small, robust async reader for the Binance USDⓈ-M Futures WebSocket. Auto-reconnect, dead-connection detection, and the streams that *actually deliver* (some aggregated ones silently send nothing). |
| **[trading-bot-ops](https://github.com/Makeph/trading-bot-ops)** | No-Kubernetes 24/7 supervision kit — PowerShell watchdog (Windows) + templated systemd unit & VPS bootstrap (Linux). Auto-restart, stall detection, alerts. |

### 🧭 How I think about strategy work

- **Kill your darlings.** The PF 2.5 backtest that made me richest on paper was
  fiction. Finding that out was worth more than the fiction.
- **Costs are the strategy.** Spread, slippage, funding and fees decide more
  edges than signal does. Model them first, not last.
- **Variance ≠ edge.** Passing a funded challenge with no alpha is a coin-flip
  against tight drawdown geometry. `prop-ev` exists to make that math visible.
- **Boring infra wins.** A strategy that's down because the WebSocket froze at
  3am isn't a strategy. Supervision, reconnection, and alerts are features.

<details>
<summary>📊 GitHub stats</summary>
<br/>
<p align="center">
  <img height="165" src="https://github-readme-stats.vercel.app/api?username=Makeph&show_icons=true&hide_border=true&theme=tokyonight&count_private=true" />
  <img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Makeph&layout=compact&hide_border=true&theme=tokyonight" />
</p>
</details>

<p align="center"><sub>Everything here is research & engineering, not financial advice. The honest verdict is usually "no edge" — and that's fine.</sub></p>
