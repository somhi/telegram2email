# telegram2email Node-RED Flow
This Node-RED flow acts as a gateway receiving telegram messages and sending them back as emails.

### Use cases
* Send a note/remainder email to yourself through telegram app faster than using email app.
* Send message/email to a friend who is not on telegram yet without loosing time opening e.g. gmail website to compose a new email. 

### Node-RED Flow
![NodeRed Flow image](screenshots/telegram2email-flow.png?raw=true "flow")

### What it does and what needs to be improved
Each telegram received message is first classified in a switch node as text message or others, assuming others will be an image or sticker.  

In each case a template node formats accordingly the body text of the email as HTML: 
* Text template includes "user_first_name: text message".  
* Image template includes "user_first_name: caption message", followed by the image itself.  

You can adapt those templates to suit your needs.

After that, a compose email function generates the subject of the email (msg.topic) and adds the HTML template to the body of the email (msg.payload). Subject has two variants:
* If the message comes from a private user, the subject is "TG-user_first_name".
* If the message comes from a group chat,  the subject is "TG-group_name".  

You can adapt the subject to suit your needs.

Finally the output email node sends the email.

**Improvements to be done**  
* Add support for other message types: audio, video, document, voice, ...
* For chat group messages, it would be interesting to generate hourly or daily summary messages for a better reading of the chat conversation in the email app.

**Collaboration is very welcome to this project.**

### Install
First you need to install node-red-contrib-telegrambot library into Node-RED for telegram integration [1].

Then import the flow file "telegram2email.json" to your Nodered server.

Finally, configure nodes with your own data.  

**Nodes configuration**

Configure telegram receiver node with your own bot. You need to enter Bot-Name and Token.  
You can create your own bot in telegram sending the /newboot command to @botfather telegram bot.  
I changed poll interval to 10000 ms instead of 300 ms as I don't need real time interaction.  
See sample configuration in screenshots folder.

Check the template and function nodes if you want to change main text and/or subject of the email.

Configure email output node with your SMTP server details for sending emails [2].  
See sample configuration in screenshots folder.

### More information:
[1] https://flows.nodered.org/node/node-red-contrib-telegrambot  
[2] https://flows.nodered.org/node/node-red-node-email  
