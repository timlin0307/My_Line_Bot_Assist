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
## Basic Programme
```cmd
from flask import Flask, request, abort

from linebot import (
    LineBotApi, WebhookHandler
)
from linebot.exceptions import (
    InvalidSignatureError
)
from linebot.models import *

app = Flask(__name__)

# Channel Access Token
line_bot_api = LineBotApi('JQ+Txo/FPbZYT8/5926rqrVNkpBpAuL70V5/Q1PC/VyyF789IS8YNfEFh5dOVtWHzYCupb6zeyw3FSKXVVGvfj9P84AR2R1XXebK2qzdrcr0x1RlKdPGYzA+sts8Fu6Ckso8MCKkTFGyuSHU42ufuwdB04t89/1O/w1cDnyilFU=')
# Channel Secret
handler = WebhookHandler('af5b2535296d40edf9953e3d7175340a')

# 監聽所有來自 /callback 的 Post Request
@app.route("/callback", methods=['POST'])
def callback():
    # get X-Line-Signature header value
    signature = request.headers['X-Line-Signature']
    # get request body as text
    body = request.get_data(as_text=True)
    app.logger.info("Request body: " + body)
    # handle webhook body
    try:
        handler.handle(body, signature)
    except InvalidSignatureError:
        abort(400)
    return 'OK'

# 處理訊息
@handler.add(MessageEvent, message=TextMessage)
def handle_message(event):
    message = TextSendMessage(text=event.message.text)
    line_bot_api.reply_message(event.reply_token, message)

import os
if __name__ == "__main__":
    port = int(os.environ.get('PORT', 5000))
    app.run(host='0.0.0.0', port=port)
```
## My Programme Status
- 
