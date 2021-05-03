## Так выглядит начало Телеграм-бота

```javascript
const TelegramBot = require('node-telegram-bot-api')
const debug = require('./helpers')
const TOKEN = '12345:BOwUFeI3ogw98eg'

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
```


[Уроки Владилена по созданию ботов на Node.js](https://www.youtube.com/watch?v=-6aesuE9oP4&list=PLhgRAQ8BwWFaxlkNNtO0NDPmaVO9txRg8&index=1)
