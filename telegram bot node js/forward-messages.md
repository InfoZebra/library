# Пересылка сообщений по нажатию кнопки

```javascript
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

### Результат

![image](https://user-images.githubusercontent.com/79378855/117831457-426c9300-b27d-11eb-8d3e-b9c60f5263bd.png)

