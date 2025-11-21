# 🤖 Autheo Network Faucet Automation Script

This script automates token claiming from the Autheo Network testnet faucet and tx using private keys and optional proxy support. CAPTCHA solving is handled automatically via the 2Captcha service.

---

## 📦 Requirements

Before running the script, make sure you have the following installed:

### ✅ Node.js (v20 or later)

Download from: [https://nodejs.org/en/download](https://nodejs.org/en/download)

### ✅ Git

Download from: [https://git-scm.com/downloads](https://git-scm.com/downloads)

---

## 🧬 Installation

### 1. Clone this repository

Open your terminal (or Command Prompt on Windows) and run:

```bash
git clone https://github.com/meomundep/autheo-network.git
cd autheo-network
```
---

## 📁 Project Structure

```
.
├── configs.json          # Configuration file
├── privateKeys.txt       # List of private keys (one per line)
├── proxies.txt           # List of proxies (optional)
├── faucet_meomundep.js             # Faucet automation script
├── tx_meomundep.js             # Tx automation script
├── run.bat             # Windows startup script
├── run.sh              # Unix-based startup script
```

---

## 🛠️ Setup

### 1. `configs.json`

Create a `configs.json` file with the following structure:

```json
{
  "proxyMode": "static",
  "skipInvalidProxy": false,
  "delayEachAccount": [1, 1],
  "timeToRestartAllAccounts": 300,
  "howManyAccountsRunInOneTime": 1,

  "faucet": {
    "enable": true,
    "maxCaptchaAttempts": 20,
    "2captchaApiKey": ""
  },

  "deployToken": {
    "enable": true,
    "amount": [1, 3],
    "transferTokens": true
  },

  "deployNFT": {
    "enable": true,
    "amount": [1, 3],
    "transferNFTs": true
  },

  "transferNativeTokens": {
    "enable": false,
    "amount": [1, 3]
  }
}
```

* `2captchaApiKey`: Your API key from [2captcha.com](https://2captcha.com).
* `maxCaptchaAttempts`: Number of retries to poll the solved CAPTCHA.

---

### 2. `privateKeys.txt`

Create a file named `privateKeys.txt` with one **Ethereum-compatible private key** per line:

```
0xabc123...def
0x456789...012
...
```

These wallets will receive the Autheo testnet tokens.

---

### 3. `proxies.txt` (Optional)

To avoid IP rate limits, you can use proxies. Add one proxy per line in the format:

```
host:port:username:password
```

Supported proxy types:

* HTTP(S)
* SOCKS (if `.onion` domain is detected)

If fewer proxies than wallets are provided, remaining wallets will use your local IP.

---

## ▶️ Running the Script

* For **Windows**, double-click `run.bat`.
* For **macOS/Linux**, run `chmod +x run.sh && ./run.sh`.

No need to manually install Node.js modules — they are pre-handled in the startup scripts.

---

## 📢 Notes

* CAPTCHA solving can take **15–45 seconds** per wallet.
* Script waits **30 seconds** between wallet claims to avoid rate limits.
* Results will be logged in real-time with shortened wallet addresses.

---

## 📎 Credits

- **Support me via Donate** [Here](https://t.me/KeoAirDropFreeNe/312/27801)
- **Contact for work:** [Telegram](https://t.me/MeoMunDep)
- **Join the support group:** [Join here](https://t.me/KeoAirDropFreeNe)
- **Updates Channel:** [View channel](https://t.me/KeoAirDropFreeNee)
- **YouTube Channel:** [Watch here](https://www.youtube.com/@keoairdropfreene)
- **Instagram:** [Follow me](https://www.instagram.com/meomundep)
- **Tiktok:** [Follow me](https://www.tiktok.com/@meomundep)

⚠️ **Disclaimer**

This project was created solely as a **personal educational exercise**.  
It is **not an official product**, website, or service of any company or brand referenced in this repository.  
The creator is **not affiliated, associated, endorsed by, or connected** with any such company or brand in any way.

The code is provided **"as is"** without any warranties or guarantees.  
Certain parts of the source are intentionally **obfuscated** to protect personal research, custom logic, and implementation techniques developed during learning and experimentation.

Use this project responsibly and at your own risk.  
**Redistribution, resale, or commercial use** of any part of this code—whether original or modified—is **not permitted**.
