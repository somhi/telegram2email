# telegram2email Node-RED Flow
This Node-RED flow acts as a gateway receiving telegram messages and sending them back as emails.

### Node-RED Flow
![NodeRed Flow image](screenshots/telegram2email-flow.png?raw=true "flow")

### Install
First you need to install node-red-contrib-telegrambot library into Node-RED for telegram integration.

Then import the flow file "telegram2email.json" to your Nodered server.

Finally configure nodes with your own data.

Configure telegram receiver node with your own bot. You need to entener Bot-Name and Token.
You can create your own bot in telegram sending the /newboot command to @botfather telegram bot.
I changed poll interval to 10000 ms instead of 300 ms as I don't need real time interaction.
See sample configuration in screenshots folder.

Check the template and function nodes if you want to change main text and/or subject of the email.

Configure email output node with your smtp server details for sending emails.
See sample configuration in screenshots folder.

### More information:
https://flows.nodered.org/node/node-red-contrib-telegrambot
https://flows.nodered.org/node/node-red-node-email
