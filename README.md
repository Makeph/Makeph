<h1 align="center">I build tools from scratch — local-first, low-dependency, one binary each.</h1>

<p align="center">
  <em>A Bash debugger with no ptrace. An x86-64 disassembler with no capstone. A VPN with no server. Most of what I ship reimplements a layer from the metal up and runs offline with nothing to sign into — because understanding the layer beats gluing over it.</em>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white" />
  <img src="https://img.shields.io/badge/C%2B%2B17-00599C?style=flat-square&logo=cplusplus&logoColor=white" />
  <img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white" />
  <img src="https://img.shields.io/badge/WebAssembly-654FF0?style=flat-square&logo=webassembly&logoColor=white" />
  <img src="https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white" />
  <img src="https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black" />
</p>

---

### 🛠 What I ship

I write tools the way I want to use them: **single binary, few or zero
dependencies, local-first.** No telemetry, no account, nothing that only works
while some SaaS is up. When a tool reimplements something from scratch — a
debugger without `ptrace`, a disassembler without a library, a mesh VPN without
a server — it's because owning the layer beats gluing over it. Most ship to
crates.io / PyPI so you can `pip install` a compiled binary and go.

### 📦 Tools

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
- **Boring infra wins.** Single binary, real tests, CI-friendly exit codes. A
  tool that's down at 3am isn't a tool.

<details>
<summary>📊 GitHub stats</summary>
<br/>
<p align="center">
  <img height="165" src="https://github-readme-stats.vercel.app/api?username=Makeph&show_icons=true&hide_border=true&theme=tokyonight&count_private=true" />
  <img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Makeph&layout=compact&hide_border=true&theme=tokyonight" />
</p>
</details>

<p align="center"><sub>Everything here is engineering & research, not financial advice. Most of it is free, MIT, and runs on your machine.</sub></p>
