## Создаем клавиатуру внизу экрана для удобного взаимодействия пользователя с ботом

``` javascript
bot.on('message', msg => {

    const chatId = msg.chat.id

    if (msg.text === 'Закрыть'){

        bot.sendMessage(chatId, 'Закрываю клавиатуру', {
            reply_markup: {
                remove_keyboard: true
            }
        })

    } else if (msg.text === 'Ответить'){

        bot.sendMessage(chatId, 'Отвечай', {
            reply_markup: {
                force_reply: true
            }
        })

    } else {
        bot.sendMessage(chatId, 'Клавиатура', {
            reply_markup: {
                keyboard: [
                    ['Отправить геопозицию'],
                    ['Ответить', 'Закрыть'],
                    ['Отправить контакт']
                ]
            }
        })
    }
})

```

###### Вот результат:
![axion-bot-keyboard-for github(1)](https://user-images.githubusercontent.com/82906305/116095761-60e56280-a6b1-11eb-86ad-1d64dcfdfd10.gif)
