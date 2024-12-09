# Telegram Bot API server

### Systemd
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

### OpenRC
```bash
sudo apk update
sudo apk upgrade --available
sudo apk add alpine-sdk linux-headers git zlib-dev openssl-dev gperf cmake

mkdir -p ~/.local/src
rm -rf ~/.local/src/telegram-bot-api
git clone --depth 1 --recursive https://github.com/tdlib/telegram-bot-api ~/.local/src/telegram-bot-api
cd ~/.local/src/telegram-bot-api
rm -rf build
mkdir build
cd build
cmake -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX:PATH=.. ..
cmake --build .

sudo mkdir -p /opt/telegram-bot-api
sudo cp -rf telegram-bot-api /opt/telegram-bot-api/
sudo chmod 0755 /opt/telegram-bot-api/telegram-bot-api
sudo ln -sf /opt/telegram-bot-api/telegram-bot-api /usr/local/bin/telegram-bot-api

sudo curl -fsSL https://github.com/upsups/telegram-bot-api/raw/refs/heads/main/etc/init.d/telegram-bot-api -o /etc/init.d/telegram-bot-api
sudo chmod +x /etc/init.d/telegram-bot-api
sudo rc-update add telegram-bot-api
sudo rc-service telegram-bot-api start
```
