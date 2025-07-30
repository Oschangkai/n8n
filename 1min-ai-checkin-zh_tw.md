# 1min.ai checkin

## 使用方式

1. 新增環境變數 (以 docker compose 為例)

- 新增檔案 `oneminai.env`，內容如下：
```ini
# 1min.ai 帳號密碼
ONEMINAI_EMAIL=
ONEMINAI_PASS=
# 傳送 Telegram 通知的 Chat ID
ONEMINAI_NOTIFY_TELEGRAM_CHATID= 
```

- 在 `docker-compose.yml` 中，新增環境變數
```yaml
env_file:
  - oneminai.env
```

- 重新啟動 n8n
```bash
docker compose down && docker compose up -d
```

2. 在 n8n 介面新增 credentials

- TOTP API
  - Secret: 填入 OTP Secret
  - Label: 填入 `1min.AI:(<login_account>)`
- Telegram API

3. 匯入 workflow

- Create Workflow > Import from URL > `https://raw.githubusercontent.com/Oschangkai/n8n/refs/heads/main/1min-ai-checkin.json`
- 點開有驚嘆號的 node，填入 credentials

## 參考來源
[7a6163/1min-checkin - GitHub](https://github.com/7a6163/1min-checkin)