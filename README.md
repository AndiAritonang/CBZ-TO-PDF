# CBZ → PDF Telegram Bot

A Telegram bot that converts `.cbz` (Comic Book ZIP) files to PDF with real-time progress updates.

## Features

- 📦 Send one or multiple `.cbz` files — processed one by one per user
- 📊 Real-time progress bar updates during conversion
- 🔄 Per-user queue — no interference between users
- 🖼️ Handles JPEG, PNG, WebP, BMP, TIFF, GIF images inside CBZ files
- 🔒 Safe ZIP extraction (path traversal protection)
- 🧹 Auto-cleanup of temporary files after each conversion
- ⚡ Async processing — bot stays responsive under load

## Requirements

- Python 3.10+
- A Telegram bot token from [@BotFather](https://t.me/BotFather)

## Setup

### 1. Clone the repository

```bash
git clone https://github.com/prashanttupsundar2121-star/CBZ-TO-PDF.git
cd CBZ-TO-PDF
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Set your bot token

```bash
export BOT_TOKEN="your_telegram_bot_token_here"
```

### 4. Run the bot

```bash
python bot.py
```

## Docker

Build and run with Docker:

```bash
docker build -t cbz-pdf-bot .
docker run -e BOT_TOKEN="your_telegram_bot_token_here" cbz-pdf-bot
```

## Environment Variables

| Variable | Default | Description |
|---|---|---|
| `BOT_TOKEN` | *(required)* | Telegram bot token from @BotFather |
| `MAX_FILE_SIZE_MB` | `125` | Maximum allowed CBZ file size in MB |

## Usage

1. Start a chat with your bot on Telegram.
2. Send `/start` to see instructions.
3. Send one or more `.cbz` files.
4. The bot converts each file and sends back the PDF.

## File Size Limits

- Default maximum: **125 MB** per file (configurable via `MAX_FILE_SIZE_MB`)
- Telegram's own upload limit applies (up to 2 GB with Bot API local server)

## License

MIT
