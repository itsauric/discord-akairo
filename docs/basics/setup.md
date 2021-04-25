# Setting Up

## Installation

Before even doing anything else, you of course have to install the Discord.js and Akairo.  

`npm i discord.js`
`yarn add discord.js`
`npm install ItsAuric/discord-akairo`
`yarn add ItsAuric/discord-akairo`

Once everything has been installed, your working directory should look something like this:  

```markdown
mybot
|____ node_modules
      bot.js
```

### Main File

Inside `bot.js`, require `discord-akairo` and extend the `AkairoClient` class to customize your client.  
As your bot gets more complicated, you may want to separate this client class from your main file.  

```js
const { AkairoClient } = require('discord-akairo');

class MyClient extends AkairoClient {
    constructor() {
        super({
            // Options for Akairo go here.
        }, {
            // Options for discord.js goes here.
        });
    }
}

const client = new MyClient();
client.login('TOKEN');
```

There are some options you may want to setup first, for example, the owner of the bot.
If you would like to have multiple owners simply add those with an array.  
We want to use Discord.js's `disableMentions` option too.  

```js
const { AkairoClient } = require('discord-akairo');

class MyClient extends AkairoClient {
    constructor() {
        super({
            ownerID: '123992700587343872', // or ['123992700587343872', '86890631690977280']
        }, {
            disableMentions: 'everyone'
        });
    }
}

const client = new MyClient();
client.login('TOKEN');
```

Your bot should now login, and you are ready to make commands.  
