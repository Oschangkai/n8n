# 1min.ai checkin

## Usage

1. Add environment variables (using docker compose as an example)

- Create file `oneminai.env` with the following content:
```ini
# 1min.ai account credentials
ONEMINAI_EMAIL=
ONEMINAI_PASS=
# Chat ID for sending Telegram notifications
ONEMINAI_NOTIFY_TELEGRAM_CHATID= 
```

- In `docker-compose.yml`, add environment variables
```yaml
env_file:
  - oneminai.env
```

- Restart n8n
```bash
docker compose down && docker compose up -d
```

2. Add credentials in n8n interface

- TOTP API
  - Secret: Enter OTP Secret
  - Label: Enter `1min.AI:(<login_account>)`
- Telegram API

3. Import workflow

## Reference
[7a6163/1min-checkin - GitHub](https://github.com/7a6163/1min-checkin)