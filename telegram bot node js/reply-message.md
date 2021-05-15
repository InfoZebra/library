# Ответить на сообщение по нажатию кнопки
###### В коде присутствует код для пересылки сообщения

```javascript
const { query } = require('express')
const TelegramBot = require('node-telegram-bot-api')
const debug = require('./helpers')
const TOKEN = '1690134518:AAEck31ycLc1hrRoFWjCzYfTYGToH1sFrsk'

console.log("Bot has been started...")

const bot = new TelegramBot(TOKEN, {
    polling: {
        interval: 300,
        autoStart: true,
        params: {
            timeout: 10
        }
    }
})

const inline_keyboard = [
    [
        {
            text: 'Forward',
            callback_data: 'forward'
        },
        {
            text: 'Reply',
            callback_data: 'reply'
        }
    ],
    [
        {
            text: 'Edit',
            callback_data: 'edit'
        },
        {
            text: 'Delete',
            callback_data: 'delete'
        }
    ]
]

bot.on('callback_query', query => {

    const { chat, message_id, text } = query.message

    switch (query.data) {
        case 'forward':
            // куда, откуда, что (id)
            bot.forwardMessage(chat.id, chat.id, message_id)
            break
        case 'reply':
            bot.sendMessage(chat.id, 'Answering the question...', {
                reply_to_message_id: message_id
            })
    }

    bot.answerCallbackQuery({
        callback_query_id: query.id
    })
})

bot.onText(/\/start/, (msg, [source, match]) => {

    const chatId = msg.chat.id

    bot.sendMessage(chatId, 'Keyboard', {
        reply_markup: {
            inline_keyboard
        }
    })
})
```
### За ответ на сообщение отвечает лишь код, находящийся в конструкции switch -> case 'reply'

#### Снизу результат

![Screenshot from 2021-05-15 13-22-07](https://user-images.githubusercontent.com/79378855/118358988-ed38c600-b589-11eb-95f2-c8bb29f44f9a.png)
