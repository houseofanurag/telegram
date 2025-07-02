# 🤖 How to Create & Host a Telegram Bot on PythonAnywhere

A step-by-step guide to building a Telegram bot with Python and deploying it 24/7 for free.

![Telegram Bot Demo](https://i.imgur.com/3JQ0X2M.png)  
*(Example bot interaction)*

## 🌟 Features
- Reply to commands (`/start`, `/help`)
- Echo user messages
- Hosted permanently on PythonAnywhere
- Custom profile picture

## 🛠️ Prerequisites
- Python 3.8+
- Telegram account
- [PythonAnywhere](https://www.pythonanywhere.com/) account (free tier)

## 🚀 Quick Start

### 1. Create Your Bot
```bash
# Install required package
pip install python-telegram-bot
```

### 2. Save This Code as `bot.py`
```python
from telegram import Update
from telegram.ext import Application, CommandHandler, MessageHandler, filters, ContextTypes

TOKEN = "YOUR_BOT_TOKEN"  # From @BotFather

async def start(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text("Hello! I'm your bot. Try /help")

async def help(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text("Commands:\n/start - Welcome\n/help - This message")

async def echo(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text(f"You said: {update.message.text}")

def main():
    app = Application.builder().token(TOKEN).build()
    app.add_handler(CommandHandler("start", start))
    app.add_handler(CommandHandler("help", help))
    app.add_handler(MessageHandler(filters.TEXT & ~filters.COMMAND, echo))
    app.run_polling()

if __name__ == "__main__":
    main()
```

### 3. Run Locally
```bash
python bot.py
```
Test by messaging your bot on Telegram.

## ☁️ Host on PythonAnywhere
1. Upload `bot.py` to PythonAnywhere
2. In **Bash Console**:
```bash
pip install python-telegram-bot
python bot.py  # Test first
```
3. Set up 24/7 task:
   - Go to **Tasks** tab
   - Enter: `bash -c "python /home/yourusername/bot.py"`

## 🖼️ Set Profile Picture
1. Talk to [@BotFather](https://t.me/BotFather)
2. Send:
```
/setuserpic @YourBotUsername
```
3. Upload square image (512×512px)

## 📚 Next Steps
- Add [button menus](https://github.com/python-telegram-bot/python-telegram-bot/wiki/Code-snippets#inlinekeyboardbutton--inlinekeyboardmarkup)
- Connect to [Firebase database](https://firebase.google.com/docs/database)
- Implement [natural language processing](https://spacy.io/)

## 💡 Troubleshooting
| Issue | Solution |
|-------|----------|
| Bot not responding | Check PythonAnywhere task logs |
| "Invalid token" | Regenerate token via @BotFather |
| Import errors | Run `pip install --upgrade python-telegram-bot` |
