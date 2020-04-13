# Disclyssia
A personal JavaScript Discord library made for my bot

# Installation
Disclyssia was made with [Node.js](https://nodejs.org/) v12.16.2, you should preferably use this version 

GitHub: `npm i --save github:Sworder71/Disclyssia`

# Information
This module has currently:
- Client support
- No voice support 
- Message support
- No full channel support
- No full server support
- No full user support

# Example usage
```js
'use strict';

const Discord = require('disclyssia');
const client = new Discord.Client();

client.on('ready', async (client) => {
    const self = await client.getSelf();
    console.log(`${self.username}#${self.discriminator} is online !`);
    await client.setPresence({ game: { name: 'Hello, World!' } });
});

client.on('message', (message) => {
    if (message.content.startsWith('!ping')) {
        client.sendMessage(message.channel_id, {
            content: 'Pong!'
        }).catch(console.error);
    }
});

client.login(''); // put your bot token here
```
