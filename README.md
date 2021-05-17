# Discord Status Checker And Role Adder
Check Status Of a Discord User and Give Them Roles!

If you use this for your server then please join Rainbow Studios- https://discord.gg/yPN49wdqMc

# Contents
<a href="https://github.com/TeamRainbowDevs/discord-status-checker-and-role-adder#config">config.json</a> <br>
<a href="https://github.com/TeamRainbowDevs/discord-status-checker-and-role-adder#you-must-have-the-presence-intent-enabled">Intents</a> <br>
<a href="https://github.com/TeamRainbowDevs/discord-status-checker-and-role-adder#credits">Credits</a> <br>
<a href="https://github.com/TeamRainbowDevs/discord-status-checker-and-role-adder#advanced-code-for-your-bot-if-you-dont-wanna-make-a-serperate-bot">Advanced code for your bot</a> <br>

# Config

config.json Example:
```json
{
  "token": "",  token of your discord bot
  "statustext": "",  check for this status
  "roletogiveid": "",  role id to add to the user if the user had the statustext
  "serverid": "",  serverid (the role id must be in the server)
  "consolelogwhenrolegiven": true,  console log every user that has the status ( HAD TO BE REMOVED WILL BE BACK IN THE NEXT UPDATE! )
  "checkeveryseconds": 5  check statuses every () seconds 
}
```

# YOU MUST HAVE THE PRESENCE INTENT ENABLED!


![discord.dev](https://cdn.discordapp.com/attachments/628197645537771530/843545696245252136/unknown.png)

# Credits

Rainbow Studios- https://discord.gg/yPN49wdqMc

# Advanced code for your bot if you dont wanna make a serperate bot!

```js
client.on('presenceUpdate', async (oldPresence, newPresence) => {
    if(oldPresence.member.user.bot || newPresence.member.user.bot) return;
    
    let oldState = oldPresence.activities[0]?.state
    let newState = newPresence.activities[0]?.state
    if(oldState === newState) return;
    if(newState.includes("content")) {
        newPresence.member.roles.add('role id')
    }
})
```
