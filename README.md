<h1 align="center">I build from the metal up — local-first, low-dependency, one binary each.</h1>

<p align="center">
  <em>A Bash debugger with no ptrace. An x86-64 disassembler with no capstone. A VPN with no server — and, lately, an edge stack that runs a greenhouse or a chicken coop offline and watches it for drift. Own the layer, run it local, sign into nothing.</em>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white" />
  <img src="https://img.shields.io/badge/C%2B%2B17-00599C?style=flat-square&logo=cplusplus&logoColor=white" />
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/MicroPython-2B2728?style=flat-square&logo=micropython&logoColor=white" />
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" />
  <img src="https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white" />
  <img src="https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black" />
</p>

---

### 🌐 HiddenGrid — a local-first edge stack

Real controllers on cheap ESP32s, and the hub that ties them together. The safety
logic lives **in firmware** — a closing coop door stops on an obstacle, on
overcurrent, on a move timeout — the whole thing runs with **no network**, and every
line of logic is tested on a desktop with **no hardware**, then gated by CI.

| Layer | Repo | What it is |
|---|---|---|
| Control | **[greenhouse](https://github.com/Makeph/greenhouse)** | ESP32/MicroPython greenhouse controller — light, aeration, heat and pulse irrigation with hysteresis; offline-first; a wrap-safe uptime clock so it survives a season unattended. |
| Control | **[coopilot](https://github.com/Makeph/coopilot)** | Connected chicken-coop controller — an autonomous pop-hole door with real safety interlocks (anti-pinch, overcurrent, timeout, limit switches) as a host-tested state machine. |
| Hub | **[plexus](https://github.com/Makeph/plexus)** | Ingests the controllers' MQTT into a Gorilla-compressed time-series, watches every stream for drift and stuck sensors, serves one dashboard — stdlib only, no database, no broker service. |

Three more repos take the **industrial** thesis further:
**[industrial-retrofit](https://github.com/Makeph/industrial-retrofit)** speaks real
Modbus-TCP (pure stdlib) to turn a legacy machine's registers into telemetry, anomalies
and live OEE — point it at a real PLC;
**[line-twin](https://github.com/Makeph/line-twin)** analyses a line from your *measured*
cycle times, validates its model against the line's real output, and quantifies the ROI
of fixing the bottleneck; and
**[gorilla-tsc](https://github.com/Makeph/gorilla-tsc)** is the time-series codec `plexus`
stores with.

---

### 🛠 Underneath it — the systems lab

I write tools the way I want to use them: **single binary, few or zero
dependencies, local-first.** No telemetry, no account, nothing that only works
while some SaaS is up. When a tool reimplements something from scratch — a
debugger without `ptrace`, a disassembler without a library, a mesh VPN without
a server — it's because owning the layer beats gluing over it. Most ship to
crates.io / PyPI so you can `pip install` a compiled binary and go.

| Repo | What it is | Lang |
|---|---|---|
| **[forgewatch](https://github.com/Makeph/forgewatch)** | Local-first CI runner — DAG-scheduled YAML pipelines, content-addressed job cache, live web dashboard. `pip install forgewatch-ci` | Rust |
| **[gravedigger](https://github.com/Makeph/gravedigger)** | From-scratch x86-64 disassembler + ELF/PE loader + emulator + debugger. No capstone, no objdump, no ptrace. `pip install gravedigger` | Rust |
| **[ghostwire](https://github.com/Makeph/ghostwire)** | Userspace mesh VPN — Noise-encrypted UDP tunnels, WireGuard-compatible config, zero servers. `pip install ghostwire` | Rust |
| **[trapdoor](https://github.com/Makeph/trapdoor)** | Interactive step-debugger for Bash — no patched bash, no ptrace, just the `DEBUG` trap and `/dev/tcp`. `pip install trapdoor-sh` | Rust |
| **[leakhound](https://github.com/Makeph/leakhound)** | Zero-dependency secret scanner — AWS/GitHub/Slack/Stripe keys, PEM, JWTs, entropy heuristics. CI-friendly. `pip install leakhound` | C++ |
| **[terrier](https://github.com/Makeph/terrier)** | Local-first memory for coding agents — one SQLite FTS5 index over sessions + notes. `pip install terrier-kb` | Python |
| **[slopkit](https://github.com/Makeph/vibe-tools)** | Three CLIs for coding with AI — `llmcost` (price a prompt), `ctxpack` (pack a repo to context), `slopcheck` (catch hallucinated deps). `pip install slopkit` | Python |
| **[dep-xray](https://github.com/Makeph/dep-xray)** | In-browser, zero-dependency npm supply-chain scanner for `package.json`. **[Live demo →](https://makeph.github.io/dep-xray/)** | JS |
| **[cinderwave](https://github.com/Makeph/cinderwave)** | Open-hardware acid groovebox — RP2040 firmware + a portable, host-testable C++17 DSP core. `pip install cinderwave` | C++ |
| **[rankforge](https://github.com/Makeph/rankforge)** | Local-first SEO autopilot — keyword research, content briefs, on-page optimization via pluggable LLM engines. `pip install rankforge` | Python |

### 📈 …and a quant loop on the side

Before the tools, I ran an end-to-end trading stack solo — pull the data, design
the strategy, build the live execution, and **stress-test the edge until it
survives or dies.** Most die; that's the job. Same engineering values, different
domain.

| Repo | What it is |
|---|---|
| **[honest-backtest](https://github.com/Makeph/honest-backtest)** | Edge-validation harness for CME micro futures & prop firms. It **debunked my own** in-sample "59% pass-rate" as a mirage once tested OOS. |
| **[prop-ev](https://github.com/Makeph/prop-ev)** | Monte Carlo for prop-firm challenges: *P(pass)* and whether the attempt is **+EV after the fee** (usually not). **[Live calculator →](https://makeph.github.io/prop-ev/)** |
| **[binance-fapi-ws](https://github.com/Makeph/binance-fapi-ws)** | Small, robust async reader for the Binance USDⓈ-M Futures WebSocket — auto-reconnect, dead-connection detection. |
| **[trading-bot-ops](https://github.com/Makeph/trading-bot-ops)** | No-Kubernetes 24/7 supervision kit — PowerShell watchdog + templated systemd unit & VPS bootstrap. |
| **[telegram-ctl](https://github.com/Makeph/telegram-ctl)** | Remote-control & alert any Python daemon from a Telegram chat. Zero deps. |

### 🧭 How I build

- **From scratch when it teaches me the layer.** A debugger, a disassembler, a
  VPN — reimplementing beats importing when the point is to *understand* it.
- **Zero dependencies is a feature.** Fewer moving parts, nothing to audit, one
  file to ship. Supply chain you don't pull is supply chain that can't bite you.
- **Local-first, no cloud.** If a job is local, it shouldn't need an account, a
  server, or a network. Offline is the default, not a fallback.
- **Evidence over optimism.** Test the logic without the hardware, flag the failure
  in plain words, and label a simulation a simulation. A tool that's down at 3am —
  or a benchmark that only works in-sample — isn't a tool.

<details>
<summary>📊 GitHub stats</summary>
<br/>
<p align="center">
  <img height="165" src="https://github-readme-stats.vercel.app/api?username=Makeph&show_icons=true&hide_border=true&theme=tokyonight&count_private=true" />
  <img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Makeph&layout=compact&hide_border=true&theme=tokyonight" />
</p>
</details>

<p align="center"><sub>Everything here is engineering & research, not financial advice. Most of it is free, MIT, and runs on your machine.</sub></p>
