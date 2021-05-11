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

### Создание поисковой ссылки

```javascript
bot.on('inline_query', query => {

    const results = []
    const searches = {
        'YouTube': 'https://www.youtube.com/results?search_query=',
        'ВКонтакте': 'https://vk.com/search?c[q]=',
        'Facebook': 'https://www.facebook.com/search/top/?q=',
	'IP-info': 'https://ip-info.org/en/?ip=',
        'DuckDuckGo': 'https://duckduckgo.com/?q=',
        'Let Me DuckDuckGo That For You': 'https://lmddgtfy.net/?q=',
        'Qwant': 'https://lite.qwant.com/?q=',
        'Google': 'https://www.google.com/search?q=',
        'Microsoft Bing': 'https://www.bing.com/search?q=',
        'Ударение': 'https://где-ударение.рф/в-слове-',
        'Ask.com': 'https://www.ask.com/web?q=',
        'Ahmia': 'https://ahmia.fi/search/?q=',
        'Startpage': 'https://www.startpage.com/?q=',
        'MetaGer': 'https://metager.org/meta/meta.ger3?eingabe=',
        'Twitter': 'https://twitter.com/search?q=',
        'Excite': 'https://results.excite.com/serp?q=',
        'Searx': 'https://searx.gnu.style/search?q=',
        'Gigablast': 'https://www.gigablast.com/search?c=main&q=',
        'Lycos': 'https://search.lycos.com/web/?q=',
        'MetaCrawler': 'https://www.metacrawler.com/serp?q=',
        'Mojeek': 'https://www.mojeek.com/search?q=',
        'WebCrawler': 'https://www.webcrawler.com/serp?q=',
        'Yahoo! Search': 'https://search.yahoo.com/search?p=',
        'Swisscows': 'https://swisscows.com/web?query=',
        'Yandex Search': 'https://yandex.ru/search/?text='
        }
    
    for (let i = 0; i < Object.keys(searches).length; i++) {
        const запрос = query.query
        const end_query = запрос.replace(/[" "]/g, "+");
        results.push({
            
            type: 'article',
            id: i.toString(),
            title: Object.keys(searches)[i],
            input_message_content: {
                message_text: searches[Object.keys(searches)[i]] + end_query
            }
        })
    }

    bot.answerInlineQuery(query.id, results, {
        cache_time: 0
    })
})
```

![image](https://user-images.githubusercontent.com/79378855/117827780-f53af200-b279-11eb-8e67-46ca32b49be3.png)
![image](https://user-images.githubusercontent.com/79378855/117827862-02f07780-b27a-11eb-9792-e6497aab50d0.png)

