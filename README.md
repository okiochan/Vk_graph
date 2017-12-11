# Vk_graph


Граф дружеских связей в vk.com. Больше инфы можно прочитать [здесь](http://habrahabr.ru/post/221251/).

# Что нужно

* Python 3.4
* [requests](https://github.com/kennethreitz/requests)
* [RabbitMQ](http://www.rabbitmq.com)
* [Celery](http://www.celeryproject.org)
* [networkx](https://github.com/networkx/networkx)

# Первые шаги

Для начала необходимо создать [Standalone-приложение](https://vk.com/dev/standalone) в VK. Делается это [там](https://vk.com/editapp?act=create). В итоге попросят ввести код-подтверждения, высланный на мобильный, после чего мы попадаем на страницу управления приложением. На вкладке **Настройки** нам пригодится **ID приложения** для получения **access_token**. 

Чтобы его получить необходимо сформировать **url**:
```
https://oauth.vk.com/authorize?client_id=IDприложения&scope=friends,offline&redirect_uri=https://oauth.vk.com/blank.html&display=page&v=5.21&response_type=token
```

Если адрес сформирован правильно, переходим по нему и получаем нечто вроде:
```
https://oauth.vk.com/blank.html#access_token=ACCESS_TOKEN&expires_in=0&user_id=USER_ID
```

