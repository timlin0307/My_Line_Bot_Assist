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
## Set Up Your Bot
- Go to LINE Developers -> Choose the Bot you'd created
- Check "Use webhook" -> "Edit" -> "Enable" -> "Update"
- "Disable" auto-reply and greeting messages (it depends on you)
- "Issue" a Channel Access Token and a Channel Secret, keep them
## Install And Set Up Heroku
- Download and install [The Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli) (it has instructions)
- Login to [Heroku](https://www.heroku.com)
- Go to "New" -> "Create New App"
- Name the app -> "Create App" 
## PUSH Bot Programme to Heroku
- Open cmd on your computer
- Login to your Heroku account
'''cmd
heroku login
'''
- 
