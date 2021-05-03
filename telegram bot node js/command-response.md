## Так выглядит простой ответ на команду с косой чертой, /help
###### Програма отправит мне то, что я написал после /help через пробел.

```javascript
bot.onText(/\/help (.+)/, (msg, [source, match]) => {
    
    const { id } = msg.chat

    bot.sendMessage(id, debug(match))
})
```
###### Пример ответа:
![](https://user-images.githubusercontent.com/82906305/115597819-5e19f480-a2e2-11eb-91e1-3153e3bf274b.png)
