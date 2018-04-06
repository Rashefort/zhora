## ZHORA
----------
----------


###### Установка
pip install zhora


----------
###### Примеры использования

```
# example 01
from zhora import Pump


class Download(Pump):
    def correct(self, url):
        return url.replace('thumb', 'xlarge')


if __name__ == '__main__':
    pages = [
        [f'http://www.photosight.ru/photos/category/3/?pager={i}' for i in range(1, 6)],
        [f'http://www.photosight.ru/photos/category/3/?pager={i}' for i in range(6, 11)],
    ]

    Download(pages, './/div[contains(@class, "photo-item")]/a/img/@src').run()
```


```
# example 02
from zhora import Pump


class Download(Pump):
    def correct(self, url):
        return f'http://glamur.biz{url}'


if __name__ == '__main__':
    pages = [
        [f'http://glamur.biz/asian/page/{i}/' for i in range(1, 3)],
        [f'http://glamur.biz/asian/page/{i}/' for i in range(3, 5)],
        [f'http://glamur.biz/asian/page/{i}/' for i in range(5, 7)],
        [f'http://glamur.biz/asian/page/{i}/' for i in range(7, 9)],
        [f'http://glamur.biz/asian/page/{i}/' for i in range(9, 11)],
        [f'http://glamur.biz/asian/page/{i}/' for i in range(11, 13)],
        [f'http://glamur.biz/asian/page/{i}/' for i in range(13, 15)],
    ]

    Download(pages, './/div[@align="center"]/img/@src').run()
```


----------
###### FAQ
1. Почему zhora?
- Потому что имя pump (насос) на pypi уже занято, а мне внезапно (такие вещи воообще внезапно происходят) вспомнилась песня - "Жора, где ты был?"
