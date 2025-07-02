How to Create a Telegram Bot & Host It on PythonAnywhere
In this guide, you’ll learn how to:
✅ Create a Telegram bot using Python
✅ Add commands & replies
✅ Host it 24/7 for free on PythonAnywhere

#Step 1: Create a Telegram Bot
Open Telegram, search for @BotFather, and start a chat.

Send /newbot and follow the instructions:

Choose a name (e.g., MyTestBot).

Pick a username ending with bot (e.g., MyTest123_bot).

Copy the API token (you’ll need it later).

#Step 2: Set Up the Bot in Python
Install Required Libraries
Run in Terminal:

bash
pip install python-telegram-bot

Create telegram_bot.py

Test Locally:

bash
python telegram_bot.py
Open Telegram, search for your bot, and send /start.

#Step 3: Host on PythonAnywhere (Free)
Sign up at PythonAnywhere.

Go to Dashboard → Files, upload telegram_bot.py.

Open a Bash Console and run:

bash
pip install python-telegram-bot
python telegram_bot.py
(Press Ctrl+C to stop it.)


Run 24/7:

Go to Tasks, enter:

bash
bash -c "python /home/yourusername/telegram_bot.py"
Click Create.

#Step 4: Add a Profile Picture
Talk to @BotFather, send:

text
/setuserpic @YourBotUsername
Upload a square image (512x512 px).

