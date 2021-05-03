## Отключить предварительный просмотр ссылки можно следующим образом:

```javascript
bot.on('message', msg => {
    bot.sendMessage(msg.chat.id, `https://www.youtube.com/watch?v=sCE9CpJLpo8`, {
        disable_web_page_preview: true
    })
})
```
