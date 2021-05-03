# Клавиатура, которая появляется под сообщением
```javascript
bot.on('message', msg => {

    const chatId = msg.chat.id

    bot.sendMessage(chatId, 'Inline keyboard', {
        reply_markup: {
            inline_keyboard: [
                [
                    {
                        text: 'Google',
                        url: 'https://duckduckgo.com/?t=lm&q='+msg.text
                    }
                ],
                [
                    {
                        text: 'Reply',
                        callback_data: 'reply'
                    },
                    {
                        text: 'Forward',
                        callback_data: 'forward'
                    }
                ]
            ]
        }
    })
})

bot.on('callback_query', query => {
   // bot.sendMessage(query.message.chat.id, debug(query))

   bot.answerCallbackQuery(query.id, `${query.data}`)
})
```

###### Пример инлайн-клавиатуры:
![Инлайн-клавиатура](https://user-images.githubusercontent.com/79378855/116927670-a3381200-ac64-11eb-83f1-ec4a0eb7fab6.gif)
