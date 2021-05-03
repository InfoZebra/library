## Отправить сообщение через 3 секунды без уведомления

```javascript
bot.on('message', msg => {

    setTimeout(() => {
        bot.sendMessage(msg.chat.id, `https://www.youtube.com/watch?v=sCE9CpJLpo8`, {
            disable_web_page_preview: true,
            disable_notification: true
        })
    }, 3000)
})
```
Сообщение отправится без звука, но пользователь все равно увидит всплывающее окно
