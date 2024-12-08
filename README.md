# Telegram Bot API server

```bash
curl -fsSL https://github.com/upsups/telegram-bot-api/releases/latest/download/telegram-bot-api-clang.tar.gz -o telegram-bot-api-clang.tar.gz
sudo mkdir -p /opt/telegram-bot-api
sudo tar -xzvf telegram-bot-api-clang.tar.gz -C /opt/telegram-bot-api
sudo chown -R root:root /opt/telegram-bot-api
sudo ln -sf /opt/telegram-bot-api/telegram-bot-api /usr/local/bin/telegram-bot-api

sudo curl -fsSL https://github.com/upsups/telegram-bot-api/raw/refs/heads/main/etc/systemd/system/telegram-bot-api.service -o /etc/systemd/system/telegram-bot-api.service
sudo systemctl daemon-reload
sudo systemctl enable telegram-bot-api
sudo systemctl start telegram-bot-api
```
