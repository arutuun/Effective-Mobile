1\. Пример REST API запроса

Когда пользователь переходит на экран с магазинами партнёрами, приложение должно отправить запрос к API для получения списка ресурсов. Стандартно используется метод GET.  
Пример такого запроса:

GET /api/v1/partner-stores HTTP/1.1  
Host: api.petrushka-zelenaya.ru  
Authorization: Bearer \<токен\_пользователя\>  
Accept: application/json

Где:  
“/api/v1/partner-stores” \- эндпоинт для получения списка партнёрских магазинов  
“Host” \- домен API интернет-магазина  
“Authorization” \- если требуется авторизациязаголовок с токеном пользователя  
“Accept: application/json” \- формат ответа

2\. Пример ответа REST API (JSON)

Ответ API должен содержать данные, соответствующие макету экрана (названия магазинов, условия доставки, логотипы и ссылки для перехода). Пример JSON-ответа:

{  
  "stores": \[  
    {  
      "id": "1",  
      "name": "METRO",  
      "delivery\_info": "Ближайшая доставка сегодня 21:00–23:00",  
      "logo\_url": "https://example.com/images/metro\_logo.png",  
      "redirect\_url": "https://metro.ru"  
    },  
    {  
      "id": "2",  
      "name": "Ашан",  
      "delivery\_info": "Ближайшая доставка сегодня 18:00–20:00",  
      "logo\_url": "https://example.com/images/ashan\_logo.png",  
      "redirect\_url": "https://ashan.ru"  
    },  
    {  
      "id": "3",  
      "name": "ВкусВилл",  
      "delivery\_info": "Быстрая доставка от 20 до 60 минут",  
      "logo\_url": "https://example.com/images/vkusvill\_logo.png",  
      "redirect\_url": "https://vkusvill.ru"  
    },  
    {  
      "id": "4",  
      "name": "ВИКТОРИЯ",  
      "delivery\_info": "Ближайшая доставка сегодня 17:00–19:00",  
      "logo\_url": "https://example.com/images/viktoria\_logo.png",  
      "redirect\_url": "https://viktoria.ru"  
    }  
  \]  
}

Где:  
“id” \- уникальный идентификатор магазина  
“name” \- название магазина  
“delivery\_info” \- информация о времени доставки  
“logo\_url” \- адрес изображения логотипа магазина (используется для отображения логотипа рядом с названием);  
“redirect\_url” \- ссылка на внешний ресурс магазина. При клике на карточку магазина приложение должно перенаправить пользователя по этой ссылке.

