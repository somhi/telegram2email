# telegram2email
Nodered gateway that receives telegram messages and send them back as emails

Import the flow file "telegram2email.json" to your Nodered server.

Configure telegram node with your own bot. You need to entener Bot-Name and Token.
You can create your own bot in telegram talking to @botfather and releasing a /newboot command

Check the template and funcion nodes if you want to change composing of the email.

Configure smtp email server details for sending emails. 

More information:
https://flows.nodered.org/node/node-red-contrib-telegrambot
https://flows.nodered.org/node/node-red-node-email
