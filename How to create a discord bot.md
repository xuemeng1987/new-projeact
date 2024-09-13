# How to Create a Discord Bot

Hello there! My name is Miya253, but you can also call me Miya. If you're looking to create a Discord bot or just curious about making one, you've come to the right place.

## Step 1: Choose Your Development Environment

There are many platforms and tools available for creating Discord bots. For this guide, we'll focus on using Node.js. You can also explore other options based on your preferences.

## Step 2: Install Node.js

1. Visit the [Node.js website](https://nodejs.org/).
2. Click on the "Download" button.
3. Follow the installation instructions for your operating system.

## Step 3: Set Up Your Development Environment

1. **Install a Code Editor**: Download and install [Visual Studio Code](https://code.visualstudio.com/), which is a powerful and versatile code editor.

2. **Install Required Libraries**:
   - Open your terminal or command prompt.
   - Install the `discord.js` library by running the following command:
     ```bash
     npm install discord.js
     ```

## Step 4: Create a Discord Application

1. Go to the [Discord Developer Portal](https://discord.com/developers/applications).
2. Click on "New Application" and give it a name.
3. Navigate to the "Bot" tab and click "Add Bot."
4. Copy the **Bot Token**. You'll need this later to run your bot.

## Step 5: Write Your First Bot

Create a new file named `bot.js` and add the following code:

```javascript
const { Client, GatewayIntentBits } = require('discord.js');
const client = new Client({ intents: [GatewayIntentBits.Guilds, GatewayIntentBits.GuildMessages, GatewayIntentBits.MessageContent] });

client.once('ready', () => {
  console.log(`Logged in as ${client.user.tag}`);
});

client.on('messageCreate', message => {
  if (message.content === '!hello') {
    message.channel.send('Hello World!');
  }
});

client.login('YOUR_BOT_TOKEN');
```

Replace **`'YOUR_BOT_TOKEN'`** with the token you copied earlier.

## Step 6: Run Your Bot
1. Open your terminal or command prompt.
2. Navigate to the directory where your **`bot.js`** file is located.
3. Run the following command to start your bot:
```bash
node bot.js
```
Your bot should now be online and responsive to the **`!hello`** command in your Discord server.

## Step 7: Deploy Your Bot
To keep your bot running 24/7, you need to deploy it to a cloud service like Heroku, AWS, or Vercel. Follow their documentation for deployment instructions.
