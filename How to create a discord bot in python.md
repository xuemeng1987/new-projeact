# How to Create a Discord Bot Using Python

Hello there! My name is Miya253, but you can also call me Miya. If you're looking to create a Discord bot using Python, here's a complete guide including how to set up a virtual environment to manage your project dependencies.

## Step 1: Install Python

1. Visit the [Python official website](https://www.python.org/downloads/).
2. Click on the "Download" button and select the version suitable for your operating system.
3. Follow the installation instructions to complete the installation.

## Step 2: Set Up a Virtual Environment

A virtual environment helps you manage Python libraries in an isolated environment, avoiding conflicts between different projects.

1. Open your terminal or command prompt.
2. Create a new virtual environment using the following command:
   ```bash
   python -m venv myenv
   ```
This will create a folder named myenv for the virtual environment.

3. Activate the virtual environment:
   - Windows:
     ```bash
     mrenv\Scripts\activate
     ```
   - macOS/Linux
     ```bash
     source myenv/bin/activate
     ```
4. You should see the name of the virtual environment in your command prompt, indicating that it's activated.

## Step 3: Install Required Libraries

With the virtual environment activated, install the discord.py library:
```bash
pip install discord.py
```

## Step 4: Create a Discord Application

1. Go to the [Discord Developer Portal](https://discord.com/developers/applications).
2. Click on "New Application" and give it a name.
3. Navigate to the "Bot" tab and click "Add Bot."
4. Copy the **Bot Token**. You'll need this later to run your bot.

## Step 5: Write Your First Bot
Create a new file named **`bot.py`** and add the following code:
```python
import discord
from discord.ext import commands

intents = discord.Intents.default()
intents.message_content = True
bot = commands.Bot(command_prefix='!', intents=intents)

@bot.event
async def on_ready():
    print(f'Logged in as {bot.user}')

@bot.command()
async def hello(ctx):
    await ctx.send('Hello World!')

bot.run('YOUR_BOT_TOKEN')
```
Replace **`'YOUR_BOT_TOKEN'`** with the token you copied earlier.

## Step 6: Run Your Bot
1. Make sure your virtual environment is still activated.
2. Open your terminal or command prompt and navigate to the directory containing the **`bot.py`** file.
3. Run
   ```bash
   python bot.py
   ```
   Your bot should now be online and respond to the **`!hello`** command in your Discord server.

## Step 7: Deploy Your Bot
To keep your bot running 24/7, you need to deploy it to a cloud service such as Heroku, AWS, or Vercel. Follow their documentation for deployment instructions.
