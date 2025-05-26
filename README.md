# 🕹Nodepay-Bot
> Forked from [**Jammer**](https://github.com/Jaammerr) 🌿

<div>
<p align="center">
  <img src="./image/image.png" alt="Nodepay-Bot Console" width="600"/>
  
  <p align="center">
    <a href="https://t.me/BargeCrypto"><img src="https://img.shields.io/badge/CryptoBarge_|_Subscribe_⚓-5B00FF?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram Channel"></a>
    <a href="https://t.me/+nbpTp74UTnVmMmM6"><img src="https://img.shields.io/badge/Crypto$БАРЖА_|_Chat_💬-5B00FF?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram Chat"></a>
</div>

---

## 🔓 Authorization Modes

The `authorization` setting in `settings.yaml` can be set to `"api"` or `"browser"`.

▫️ **`"api"`** – Authorization is performed via API requests.  
Requires selecting a `captcha_service` with a pre-funded balance.  
A reCAPTCHA token is used for login and is valid for **14 days**.  
Each new token consumes captcha balance.

▫️ **`"browser"`** – Authorization is performed by launching a Chromium-based browser on your device.  
No captcha cost — only proxy traffic is used.  
On average: **~2 GB per 2000 accounts**.

💡 `browser_threads` defines how many browser windows can run in parallel.  
Choose the value based on your system’s performance — powerful devices can handle **8 to 16** browsers simultaneously.

> 🔧 Note: `threads` and `browser_threads` can be configured independently.

> 📊 Farming 2000 accounts uses ~35 MB/s per hour.

---

## ⚙️ Settings (config/settings.yaml)

| Parameter            | Description                                           |
|---------------------|-------------------------------------------------------|
| threads             | Number of accounts to run simultaneously              |
| browser_threads     | Number of browser threads to run                      |
| authorization       | Authorization method ("api" or "browser")             |
| captcha_service     | Captcha solving service (capmonster/capsolver/twocaptcha) |
| keepalive_interval  | Delay between keepalive requests (in seconds)         |
| referral_code       | Your referral code                                   |
| delay_between_actions | Delay between actions (in seconds)                 |
| use_redirect_mode   | Enable/disable redirect mode for wallet binding      |
| use_proxies         | Enable/disable proxy usage                           |
| proxy_rotation      | Enable/disable proxy rotation                        |

---

**Note:**
- When `use_redirect_mode` is enabled, wallet binding will use a redirect-based approach  
- Proxy settings are only used when `use_proxies` is enabled  
- When `proxy_rotation` is enabled, a new proxy will be used for each account or action 
- **Proxies for rotation must be listed in `rotation_proxies.txt`**
- Choose the appropriate captcha service and provide its corresponding API key  
- Browser threads determine how many accounts can be processed simultaneously  
- Authorization method affects how the bot interacts with the service  

---

## 📁 Configuration Structure

All configuration files are located in the `config` folder:
- Bot settings: `config/settings.yaml`
- Account files: `config/data/`

---

### Account File Formats:

1. **register.txt** – **Accounts for registration**
```
email:password
```

2. **farm.txt** – **Accounts for farming**
```
email:password
```

3. **verify.txt** – **Accounts for verification**

*When `use_redirect_mode` is `false`:*
```
email:email_password:account_password
```
*When `use_redirect_mode` is `true`:*
```
email:account_password
```

4. **bind_wallet.txt** – **Accounts for wallet binding**

*When `use_redirect_mode` is `false`:*
```
email:email_password:account_password:sol_private_key
```
*When `use_redirect_mode` is `true`:*
```
email:email_password:account_password
```

5. **bind_discord.txt** – **Accounts for Discord binding**
```
email:account_password:discord_token
```

6. **bind_twitter.txt** – **Accounts for Twitter binding**
```
email:account_password:twitter_token
```

7. **claim_medals.txt** – **Accounts for claiming medals**
```
email:password
```

8. **complete_missions.txt** – **Accounts for completing missions**
```
email:password
```

### Proxy Configuration (data/proxies.txt and data/rotation_proxies.txt):
```
Supported formats:
- type://user:pass@ip:port
- type://user:pass:ip:port
- type://ip:port:user:pass
- type://ip:port@user:pass

Supported types: http, socks5
```
---

## 🧩 Modules

- Register  
- Farm  
- Exports stats  
- Verify email  
- Bind wallet
- Bind discord
- Bind Twitter  
- Claim medals
- Clomplete missions
- Change email  

---

## 🚀 Getting Started

1. **Clone the repository:**
```bash
git clone https://github.com/CryptoBarge/Nodepay-Bot.git
```

2. **Configure the bot:**
   - Fill in the settings in `config/settings.yaml`
   - Add your accounts to the appropriate files in `config/data/`
   - Add proxies to `config/data/proxies.txt`

3. **Run the bot:**
Simply double-click `run.exe` to start the bot.

---

## 📝 Notes
- Make sure all account files are properly formatted
- Monitor the bot's operation through the console output
- The bot will automatically handle retries for failed operations

---

## 🔒 Code Availability

The source code of **Nodepay-Bot** is closed.

This decision is intentional — the system includes unique technical solutions that took a lot of time and effort to develop. Opening the code would lead to uncontrolled resale and misuse of the software, which i aim to avoid in order to maintain quality and integrity.

Thank you for understanding.
