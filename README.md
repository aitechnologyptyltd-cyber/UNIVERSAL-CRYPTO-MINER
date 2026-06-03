# ⛏ UNIVERSAL MINER PRO — ULTIMATE EDITION v4.0

> 100% real. No gatekeeping. Mine crypto from any device you currently own.

[![MIT License](https://img.shields.io/badge/license-MIT-green)](LICENSE)
[![Platform](https://img.shields.io/badge/platform-Android%20%7C%20Linux%20%7C%20macOS%20%7C%20Windows-blue)]()
[![Architecture](https://img.shields.io/badge/arch-armv7l%20%7C%20aarch64%20%7C%20x86__64-yellow)]()

---

## What is this?

Universal Miner Pro is a self-contained cryptocurrency mining management platform that
runs on **any device** — an old Android phone, a Raspberry Pi, a laptop, or a
high-end server. It gives you a real browser-based dashboard, a built-in HD blockchain
wallet, multi-pool support, and automatic profit switching.

No subscription. No ads. No middleman. MIT licensed and open source.

---

## Who is this for?

Anyone who wants to start mining cryptocurrency without expensive hardware.

- Start today on whatever device you have
- A phone today, a PC next month, a multi-GPU rig next year
- Every device you add increases your earnings
- Funds go directly to your own wallet — no platform takes a cut

**Built in South Africa. Built for people who need real tools, not promises.**

---

## Honest Earnings Expectations

**Your earnings depend entirely on your hashrate.** The dashboard has a built-in
earnings calculator — enter your actual hashrate from the miner log and it will
show you real daily/weekly/monthly/yearly estimates based on current coin prices.

Real observed hashrates from actual phone testing (X11/DASH, 3 threads):

| Device | Algorithm | Observed Hashrate | Notes |
|--------|-----------|-------------------|-------|
| Android / Userland Ubuntu (3 threads) | X11 / DASH | 4–13 kH/s | Real observed — varies by chip |
| Android / Userland Ubuntu (3 threads) | RandomX / XMR | 50–300 H/s | Steady on ARM |

| Mid-range laptop (4 threads) | X11 | 50–200 kH/s | Depends on CPU |
| Mid-range laptop (4 threads) | RandomX | 500–2000 H/s | Depends on CPU |
| Desktop PC (8+ threads) | RandomX | 2000–8000 H/s | Scales with core count |
| Server (32+ threads) | RandomX | 10000–25000+ H/s | High-end hardware |

**Important:** The earnings calculator in the dashboard uses live coin prices from
CoinGecko. Cryptocurrency prices are volatile — your actual earnings in fiat currency
will change as prices move. The hashrate number is what your hardware produces.
The dollar value of that hashrate changes daily.

**The real strategy:**
1. Start mining on what you have right now
2. Check your actual hashrate in the miner log
3. Enter it into the earnings calculator for a realistic estimate
4. Reinvest earnings into more or better hardware over time
5. Scale up gradually — more devices = more earnings

This is not a get-rich-quick scheme. It is a legitimate, transparent way to generate
income from hardware you already own.

---

## Features

- **41-node swarm mining** — up to 40 parallel miner processes + 1 master
- **Multi-pool support** — Kryptex, ViaBTC, Unmineable, MoneroOcean, Mining Pool Hub, Binance Pool
- **30+ coins** — XMR, DASH, BTC, LTC, ETH, DOGE, ADA, SOL, RVN, ETC, and more
- **Dual algorithm** — RandomX (XMRig) and X11 (cpuminer-multi), switchable live
- **HD Blockchain Wallet** — BIP39/BIP44 real wallet for BTC, LTC, DASH, ETH, XMR
- **Profit auto-switching** — automatically mines the most profitable coin every 5 min
- **Pre-flight validator** — checks all credentials before mining starts
- **Binance integration** — fetch deposit addresses, initiate withdrawals via API
- **Hardware detection** — auto-detects CPU, GPU, arch, and sets optimal config
- **Live dashboard** — real-time hashrate, earnings calculator, log tail, SSE stream
- **REST API** — full API for all operations (50+ endpoints)
- **Gunicorn WSGI** — production-ready, ARM-tuned, SSE-compatible

---

## Supported Platforms

| Platform | Architecture | Notes |
|----------|-------------|-------|
| Android / Userland Ubuntu | armv7l, aarch64 | **Recommended** — full Ubuntu environment |
| Android / Termux | armv7l, aarch64 | Alternative — install from F-Droid only |
| Linux Desktop/Server | x86_64, arm64 | Full feature set |
| Raspberry Pi | armv7l, arm64 | Low hashrate but fully functional |
| macOS | x86_64, M-chip | Homebrew required for build deps |
| Windows | x86_64 | WSL2 Ubuntu recommended |

---

## Quick Start

### Android / Userland Ubuntu (Recommended)

Userland Ubuntu gives you a full Ubuntu Linux environment on Android —
more stable, better package support, and better performance than Termux
for running UMP.

```bash
# 1. Install Userland from the Play Store
# 2. Launch Ubuntu session
# 3. Run:
apt-get update && apt-get upgrade -y
apt-get install -y git python3 python3-pip cmake make gcc     libssl-dev libuv1-dev build-essential

# 4. Clone and install
git clone https://github.com/aitechnologyptyltd-cyber/UNIVERSAL-CRYPTO-MINER.git
cd UNIVERSAL-CRYPTO-MINER
chmod +x install_universal_miner.sh
./install_universal_miner.sh

# Build takes 15-25 minutes on ARM.
# Keep screen on and device plugged in during build.

# 5. Start mining
./start.sh

# 6. Open dashboard
# From phone:          http://localhost:8080
# From PC (same WiFi): http://YOUR_PHONE_IP:8080
```

### Android / Termux (Alternative)

```bash
# Install Termux from F-Droid only (NOT the Play Store version)
pkg update && pkg upgrade -y
pkg install git python cmake make gcc openssl libuv

git clone https://github.com/aitechnologyptyltd-cyber/UNIVERSAL-CRYPTO-MINER.git
cd UNIVERSAL-CRYPTO-MINER
chmod +x install_universal_miner.sh
./install_universal_miner.sh

./start.sh
```

### Linux / macOS

```bash
git clone https://github.com/aitechnologyptyltd-cyber/UNIVERSAL-CRYPTO-MINER.git
cd UNIVERSAL-CRYPTO-MINER
chmod +x install_universal_miner.sh
./install_universal_miner.sh

./start.sh             # Foreground
./start_screen.sh      # Background (persists after terminal close)
./start_gunicorn.sh    # Production (Gunicorn)
```

### Python dependencies only

```bash
pip install -r requirements.txt --break-system-packages
python3 universal_miner.py
```

---

## Setup (First Time)

1. Open `http://localhost:8080` in your browser
2. Click **Setup** in the navigation bar
3. Choose your coin and pool
4. Enter your wallet address or Binance account
5. Click **Save Profile**
6. Return to Dashboard → click **START MINING**
7. Watch the miner log — your per-CPU hashrate will appear within 30 seconds
8. Enter your hashrate into the **Earnings Calculator** for a real estimate

The pre-flight validator runs automatically and warns you if anything is
misconfigured before mining starts.

---

## Understanding Your Hashrate

Once mining starts, the miner log will show lines like:

```
[2026-05-28 16:07:09] CPU #0: 3.19 kH/s
[2026-05-28 16:07:09] CPU #1: 3.20 kH/s
[2026-05-28 16:07:09] CPU #2: 3.09 kH/s
```

Add those together — that is your total hashrate. Enter it in the
**Earnings Calculator** on the dashboard to see your real earning estimate
at current market prices.

**Your hashrate will vary** based on:
- CPU model and number of cores
- Device temperature (phones throttle when hot)
- Number of threads configured
- Background apps using CPU

---

## Supported Mining Pools

| Pool | Coins | Notes |
|------|-------|-------|
| **Kryptex** | XMR, ZEC, RVN, ETC, BTC, LTC, KAS, ERG, ALPH | Auto-converts to BTC |
| **ViaBTC** | BTC, BCH, LTC, ZEC, DASH, XMR, ETC, KAS | PPS+ payouts |
| **Unmineable** | Mine XMR, receive any 100+ coin | Great for DOGE, ADA, SOL payouts |
| **MoneroOcean** | XMR + variants | Auto-switches algo for max XMR profit |
| **Mining Pool Hub** | Multi-coin auto-switch | Requires registration + API key |
| **Binance Pool** | DASH (X11) | Direct payout to Binance account |
| **Custom / Direct** | Any coin | Enter any stratum URL manually |

---

## HD Wallet

UMP includes a real self-custodial blockchain wallet:

- Generates a **BIP39 12-word mnemonic** (write it down — this is your backup)
- Derives real addresses for **BTC, LTC, DASH, ETH, XMR**
- Signs and broadcasts real on-chain transactions
- Fetches live balances from public blockchain explorers
- Connects to Binance API to fetch deposit addresses and initiate withdrawals
- All private keys encrypted with **AES-256-GCM** and stored locally

**Security rules:**
- Write your mnemonic phrase on paper. Never store it digitally.
- Use **read-only** Binance API keys only. Never enable trading or withdrawal permissions.
- Never share your private keys or mnemonic with anyone.
- Your keys never leave your device.

---

## Wallet & API Key Setup

### Binance API Keys (read-only)

1. Log in to Binance.com
2. Profile → API Management → Create API
3. Label: `UMP Monitor`
4. Enable ONLY: **[x] Enable Reading**
5. Disable everything else: Trading, Withdrawals, Futures
6. Copy both the 64-character API Key and Secret into UMP Setup

### Binance Pool (DASH mining)

- Miner username format: `BINANCE_ACCOUNT.WORKER_NAME`
- Example: `john_doe.rig1`
- No minimum payout threshold for DASH
- Payouts credited to your Binance account daily

---

## Stop Mining

```bash
./stop.sh      # Stop everything cleanly
./restart.sh   # Stop then start again
```

---

## Logs

```
logs/ump.log                  Main application log
logs/PROFILE_xmrig.log        XMRig output per profile
logs/PROFILE_cpuminer.log     cpuminer-multi output (X11/DASH)
logs/profit_switch.log        Automatic profit switching events
logs/gunicorn_access.log      HTTP access log
logs/gunicorn_error.log       Gunicorn errors
```

---

## Troubleshooting

| Problem | Fix |
|---------|-----|
| Dashboard won't load | Run `python3 universal_miner.py` to see startup errors |
| XMRig not found | Re-run `./install_universal_miner.sh` |
| 0.00 H/s hashrate | Check pool URL and credentials in Setup |
| Build fails on armv7l | Need 1GB+ free RAM. Enable swap: `fallocate -l 1G /swapfile && chmod 600 /swapfile && mkswap /swapfile && swapon /swapfile` |
| Port 8080 in use | Edit `universal_miner.py` and change `port=8080` to `port=5002` |
| Payout not arriving | Wait 24h — pools pay daily. Run validator to check credentials. |
| Swarm nodes dying | Reduce `TOTAL_NODES` in `miner_config.py` for low-RAM devices |
| Phone getting hot | Normal during mining. Reduce threads in Setup if it throttles badly. |

---

## API Reference (key endpoints)

```
GET  /api/stats              Live miner stats
GET  /stream                 SSE real-time stream
POST /mine/start             Start mining
POST /mine/stop              Stop mining
GET  /api/profiles           List profiles
GET  /api/coins              Coin registry
GET  /api/validate           Pre-flight validation result
GET  /wallet/api/portfolio   Wallet portfolio summary
GET  /wallet/api/balances    Live blockchain balances
POST /wallet/api/transfer    Send a transaction
GET  /health                 Health check
```

Full API reference: see `UMP_ULTIMATE_v4_0_Documentation.pdf`

---

## Requirements

```
Python 3.6+
flask >= 2.0
requests >= 2.28
psutil >= 5.9
apscheduler >= 3.10
gunicorn >= 20.1
cryptography >= 41.0
```

---

## License

MIT License — free to use, modify, and distribute.
See [LICENSE](LICENSE) for full terms.

---

## Built by

**Francois Nel — AI Technology PTY LTD**
South Africa 🇿🇦

*Built on a Hisense Y82 Pro. Built for everyone.*

> "Why let people suffer when any device can generate real income?"

---

## Disclaimer

Cryptocurrency mining profitability depends on your hashrate, electricity costs,
coin prices, and network difficulty — all of which change constantly. Use the
built-in earnings calculator with your actual observed hashrate to get a realistic
estimate. This software makes no guarantees about earnings. Mine responsibly and
understand your costs before scaling up hardware.
