## Бот отправит сообщение 

```javascript
bot.on('message', msg => {

    const markdown = `
[Hello](https://www.youtube.com/watch?v=w_7olgiS110), ${msg.from.first_name}`

    bot.sendMessage(msg.chat.id, markdown, {
        parse_mode: 'Markdown'
    })
})
```

Поддерживаемые конструкции: [Telegram Bot API](https://core.telegram.org/bots/api#markdownv2-style)


#### Пример ответа

![Привет, ИнфоЗебра!](https://i.imgur.com/7SgkNh6_d.webp?maxwidth=320&shape=thumb&fidelity=medium)
