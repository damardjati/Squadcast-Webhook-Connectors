![image](assets/SQ.svg)
# Squadcast Webhook Connectors

This repository contains the code for the Squadcast Webhook Connectors and is intended to be used along with Event Hooks.
The repository supports : 
1. Slack
2. Discord
3. Trello
4. Click Up
5. Linear
6. Telegram
7. MatterMost
8. Zulip
9. Service Now
10. Email


## Prerequisites
- git
- NodeJs | npm
- nodemon
### Tip : For Linux Users, just execute the command below to install all the NodeJS prerequisites
```
bash dependencies.sh
```

## Authentication

Squadcast Webhook Connectors has authentication built-in. Users can choose between a user defined authKey or an automatically generated authKey.

* User Defined authKey :-
Inside the .env file, users need to define the `authKey` and change the `useAuthKey` variable’s value to “yes”.
![image](assets/auth-env.png)

* Auto generated authKey :-
Once the Node Server is up and running, an `authKey` will be provided.
![image](assets/auth.png)

    ***Note** : Make sure that inside the .env file, `useAuthKey` variable’s value is “no”*

Users need to add `authKey` in the headers section of the Squadcast's Outgoing Webhooks. Eg. :
![image](assets/auth-sq.png)

## Getting Started
 - Clone this repo
```sh
git clone https://github.com/highlyUnderrated/Squadcast-Webhook-Connectors
```
- Install dependencies
```sh
npm install
```
- Run
```sh
nodemon start
```
----
----
----
## Use Cases

### Slack
----

> URL : https://Server-IP-Address:5000/squadcast/connector/slack

Request Headers :- 
* Slack URL can support multiple channels. To notify channels, just put integers as name of Key value pair & value should be the Slack Webhook. Eg. :
![image](assets/slack.png)

### Discord
----

> URL : https://Server-IP-Address:5000/squadcast/connector/discord

Request Headers :- 
* Discord URL can support multiple channels. To notify channels, just put integers as name of Key value pair & value should be the Discord Webhook. Eg. :
![image](assets/discord.png)

### Trello
----

> URL : https://Server-IP-Address:5000/squadcast/connector/trello

Request Headers :- 
* To use the Trello webhook, just paste the URL mentioned above in Squadcast Webhook URl box. In the headers, just add "idList", "key" & "token" and their proper values. Eg. : 
![image](assets/trello.png)

* To see your idList, Open a card > Click on Share > Click on Export Json > You'll see a JSON which will contain idList.
* ![image](assets/idList-example.png)
* Tip : To get you own token & key, navigate to : https://trello.com/app-key

### Linear
----

> URL : https://Server-IP-Address:5000/squadcast/connector/linear

Request Headers :- 
* Inside the .env file, users need to define the `linearAPIKey` and change the `initializeLinearClient` variable’s value to “yes”.
![image](assets/linear-env.png)

* To use the Linear webhook, just paste the URL mentioned above in Squadcast Webhook URl box. Additionally, users can also define `priority` for the issues. 1 is Urgent, 2 is High, 3 is Medium & 4 is Low. Eg. : 
![image](assets/linear.png)

### MatterMost
----

> URL : https://Server-IP-Address:5000/squadcast/connector/mattermost

Steps :-
* `Important` : Before starting, create your own MatterMost Incoming webhook. For that, navigate to Integrations > Incoming Webhooks > Add Incoming Webhook. Eg. : 
![image](assets/mattermost.png)
* To notify a Channel, just paste the URL mentioned above in Squadcast Webhook URl box. In the headers, just add the Incoming Webhook as "webhook". Eg. : 
* ![image](assets/mattermost_ow.png)

### Zulip
----

> URL : https://Server-IP-Address:5000/squadcast/connector/zulip

Steps :-
* `Important` : Before starting, create your own Zulip Bot. Then add the bot in the respective organisation and Streams. Eg. : 
![image](assets/zulip_bot.png)
* To notify Stream and create a topic, just paste the URL mentioned above in Squadcast Webhook URl box. In the headers, just add the BOT EMAIL as "username", BOT API KEY as "password" & add the name of the STREAM as "stream". Eg. : 
* ![image](assets/zulip.png)

### Service Now
----

> URL : https://Server-IP-Address:5000/squadcast/connector/servicenow

Request Headers :- 
* To use the Service Now webhook, just paste the URL mentioned above in Squadcast Webhook URl box. In the headers, just add "subdomain", "urgency", "impact", "username" & "password" and their proper values. Eg. : 
![image](assets/servicenow.png)

### Telegram
----

> URL : https://Server-IP-Address:5000/squadcast/connector/telegram

Steps :-
1. `Important` : Before starting, create your own Telegram Bot : https://core.telegram.org/bots#6-botfather
2. Paste the Telegram Bot Token in the `telegram_bot_token` in .env file. Also change the `telegram_bot_start` variable's value to "yes". Eg. : 
![image](assets/telegram_env.png)
3. Now you can start the server, Refer Getting Started - Step 3.
4. To use the Telegram webhook, just paste the URL mentioned above in Squadcast Webhook URl box. In the headers, just add "chatId" and its proper value. Eg. : 
![image](assets/telegram.png)
* Tip : To get you own chatId, follow this article : https://www.alphr.com/find-chat-id-telegram/


### Click Up
----

> URL : https://Server-IP-Address:5000/squadcast/connector/clickup

Request Headers :- 
* To use the Click Up webhook, just paste the URL mentioned above in Squadcast Webhook URl box. In the headers, just add "listId", "token" & "priority" and their proper values. Eg. : 
![image](assets/clickup.png)
* `Important` : Priority is a number that corresponds to the Priorities available in the ClickUp UI. As in the ClickUp UI, priorities cannot be customized.1 is Urgent, 2 is High, 3 is Normal & 4 is Low.
* Tip : To get your own Access Token & listId, refer https://jsapi.apiary.io/apis/clickup20/introduction/authentication.html

### Email
----

> URL : https://Server-IP-Address:5000/squadcast/connector/email

Request Headers :- 
* To use the email webhook, just paste the URL mentioned above in Squadcast Webhook URl box. In the headers, just add "from_email", "from_password", "to_email" & "SMTP" and their proper values. Eg. : 
![image](assets/email.png)

List of SMTP Providers Supported : -
* Service names are case insensitive : 
"126"
"163"
"1und1"
"AOL"
"DebugMail"
"DynectEmail"
"FastMail"
"GandiMail"
"Gmail"
"Godaddy"
"GodaddyAsia"
"GodaddyEurope"
"hot.ee"
"Hotmail"
"iCloud"
"mail.ee"
"Mail.ru"
"Maildev"
"Mailgun"
"Mailjet"
"Mailosaur"
"Mandrill"
"Naver"
"OpenMailBox"
"Outlook365"
"Postmark"
"QQ"
"QQex"
"SendCloud"
"SendGrid"
"SendinBlue"
"SendPulse"
"SES"
"SES-US-EAST-1"
"SES-US-WEST-2"
"SES-EU-WEST-1"
"Sparkpost"
"Yahoo"
"Yandex"
"Zoho"
"qiye.aliyun"

---
---
---

## Other Use Cases

### Rapid7 InsightIDR - Reassign Incident
----

> URL : https://Server-IP-Address:5000/squadcast/connector/update-escalation/rapid7

Request Headers :- 
* Rapid7 InsightIDR URL supports Reassigning of an incident based on the Priority. In the headers, just add "region", "x-refresh-token", "x-api-key", "reassignId" & "reassignType" and their proper values. Eg. : 
![image](assets/rapid7-insightidr.png)

* Tip : To get you own "x-api-key", go to Settings > API Keys > User Key > New User Key 
