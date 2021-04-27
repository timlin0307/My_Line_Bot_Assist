# My_Line_Bot_Assist
## Introduction
Develop my own assistant via Line Bot. Update irregularly.
## Requirements
- [An LINE account](https://line.me/en/)
- [An Heroku account](https://www.heroku.com)
- [Python 3](https://www.python.org/)
## Create LINE Bot Channel
- Login to [LINE Developers Messaging API](https://developers.line.biz/en/services/messaging-api/)
- "Create New Provider" -> Give provider name -> "Comfirm" -> "Create"
- "Create Channel" -> Fill in the information of your bot -> "Comfirm" -> Agree Terms -> "Create"
- Refer to [1]
## Set Up A Bot
- Go to LINE Developers -> Choose the Bot you've created
- Check "webhook" -> "Edit", "Enable", "Update"
- "Disable" auto-reply and greeting messages (it depends on you)
- "Issue" a Channel Access Token and a Channel Secret, then keep it
- Refer to [1]
## References
- [1] [LineBot+Python，輕鬆建立聊天機器人](https://blackmaple.me/line-bot-tutorial/)
