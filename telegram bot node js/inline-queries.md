# Инлайн-запросы

```javascript
bot.on('inline_query', query => {

    const results = []

    for (let i = 0; i < 5; i++) {
        results.push({
            type: 'article',
            id: i.toString(),
            title: 'Title ' + i,
            input_message_content: {
                message_text: `Article #${i+1}`
            }
        })
    }

    bot.answerInlineQuery(query.id, results, {
        cache_time: 0
    })

})
```
###### Результат
![image](https://user-images.githubusercontent.com/79378855/117424886-f04d0a00-af2a-11eb-83b9-91a0d98befec.png)
