# Telegram Bot API Server

This repository contains automated builds for the [official Telegram Bot API server](https://github.com/tdlib/telegram-bot-api).

## Automated Builds

The builds are automatically generated on the first day of each month at 03:00 UTC using GitHub Actions. Each release includes:

- GCC build (`telegram-bot-api-gcc.tar.gz`)
- Clang build (`telegram-bot-api-clang.tar.gz`)

### Build Configuration

- Build type: Release
- Platform: Ubuntu Latest
- Compilers:
  - GCC (g++)
  - Clang

### How to Download

1. Go to the [Releases](../../releases) page
2. Download the desired compiler variant
3. Extract the archive:
   ```bash
   tar xzf telegram-bot-api-[compiler].tar.gz
   ```

### Manual Build Trigger

The build workflow can also be triggered manually through GitHub Actions if needed.