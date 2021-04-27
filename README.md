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
- Open cmd on your computer (cd to the folder you put the programme)
- Login to your Heroku account
```cmd
heroku login
```
- Initialize git
```cmd
git config --global user.name {"NAME"}
git config --global user.email {E-MAIL}
git init
```
- Connect your folder to Heroku
```cmd
heroku git:remote -a {HEROKU_APP_NAME}
```
- PUSH your programme (every PUSH need to do this)
```cmd
git add .
git commit -m "Add code"
git push -f heroku master
```
## Combine Heroku to LINE Bot
- Go to LINE Developers -> Choose the Bot you'd created
- Go to "Webhook URL" -> Input the URL below
```cmd
{HEROKU_APP_NAME}.herokuapp.com/callback
```
## Basic Code
- Check basic_LineBot.py above
