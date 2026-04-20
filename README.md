# CBZ → PDF Telegram Bot (Pyrogram)

Production-ready Telegram bot that accepts only `.cbz` files and returns only PDF files in strict FIFO order per user.

## Behavior

- One queue per user, one worker per user
- Multiple CBZ files are processed sequentially in exact receive order
- Non-CBZ messages/files are ignored silently
- Single progress message per file using edit updates:
  - Downloading
  - Extracting
  - Converting
  - Uploading
- Progress message is auto-deleted after successful PDF upload
- `/cancel` stops current processing, clears queue, and deletes progress message silently

## Setup

```bash
pip install -r requirements.txt
```

Set required environment variables:

```bash
export API_ID="your_api_id"
export API_HASH="your_api_hash"
export BOT_TOKEN="your_bot_token"
```

Optional:

```bash
export MAX_FILE_SIZE_MB="125"
```

Run:

```bash
python bot.py
```

## Docker

```bash
docker build -t cbz-pdf-bot .
docker run \
  -e API_ID="your_api_id" \
  -e API_HASH="your_api_hash" \
  -e BOT_TOKEN="your_bot_token" \
  -e MAX_FILE_SIZE_MB="125" \
  cbz-pdf-bot
```
