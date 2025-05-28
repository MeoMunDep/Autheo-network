# 🤖 Autheo Network Faucet Automation Script

This script automates token claiming from the Autheo Network testnet faucet and tx using private keys and optional proxy support. CAPTCHA solving is handled automatically via the 2Captcha service.

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
  "faucet": {
    "2captchaApiKey": "YOUR_2CAPTCHA_API_KEY",
    "maxCaptchaAttempts": 5
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
