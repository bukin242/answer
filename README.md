# Level I
__*Q:*__ Чем отличается Proc от lambda?  

 1. Proc не чувствителен к количеству аргументов, нежели Lambda.  
 2. Если обернуть Proc и лямбду в функцию, то return прока прекратит выполнение функции, в случае с лямбдой функция продолжит выполняться.
---
__*Q:*__ Чем отличается && от and?  

Приорететом у && выше приоретет чем у and. проверяется raise 123 && 'abc', raise 123 and 'abc'
___
__*Q:*__ Какие плюсы и минусы Ruby по сравнению с другими современными языками программирования вы выделяете для себя?  

* **Плюсы**  
    1. Эстетически очень приятный понятный язык, .
    2. Есть блоки, проки
    3. Хорошая ООП арадигма. Все является обьектом.
    4. Сообщество готовое всегда придти на помощь.
    5. Метапрограммирование.
    6. Уже написано множетсво готовый гемов.

 * **Минусы**  
    1. Медлительность, производительность
    2. Нет настоящей многопоточности.
---
__*Q:*__ В каком случае вы бы стали использовать Ruby on Rails для разработки web-приложения, а в каком — другой фреймворк?  

Rails хорош в вебе (форумы, каталоги, интенет магазины) так же хорошо строить на нем большие массивные приложения.
Для API можно использовать другой более легковесный фреймворк. Для BigData можно использовать Django, python
___
__*Q:*__ Вы запустили большой и сложный ruby скрипт на вашем любимом дистрибутиве Linux, и в процессе работы он намертво «зависает». Как найти причину сбоя?  

Использовал бы отладчик Pry через binding.pry, смотрел бы процесс через ps aux

__*Q:*__ Вы запустили большой и сложный ruby скрипт на вашем любимом дистрибутиве Linux, и в процессе работы он умирает, исчерпав память, хотя, казалось бы, не должен. Как найти причину сбоя?  

Использовал бы бенчмарки для отслеживания утечки памяти. Можно так же использовать модуль ObjectSpace чтобы проверить потребляемое кол-во.

___
__*Q:*__ Некоторые проекты (Rails и не только) мы запускаем под JRuby. Как вы думаете, почему?  

1. Вы хотите поддержку JAVA решений в проекте.
2. Вам нужна настоящая многопоточность.

___
__*Q:*__ Какие плюсы и минусы библиотеки ActiveRecord в Rails вы знаете? Какие альтернативы существуют? В чем их плюсы и минусы? Какие из них вы использовали?  

Библиотека ActiveRecord это паттерн проектирования. Достаточно гибкий. Из минусов сложные запросы прихожится писать руками на SQL. Иногда не достаточно функционала в миграциях. Приходится писать чистый SQL.

# Level II
__*Q:*__ Есть Rails приложение, развернутое на N серверах. В приложение нужно добавить загрузку и хранение аватаров.  

1. Какую библиотеку использовать?
можно использовать carrierwave + fog gem для загрузки на CDN
2. Куда складывать аватарки и почему?
Лучше использовать облачные сервисы Amazon.
3. Как и зачем нужно обрабатывать загружаемые аватарки?
Если требуется разный размер (resize) аватарки.
4. Какие проверки загружаемого файла и когда (например, на клиенте, в Nginx или Rails) лучше всего производить?
Из браузера, приверять максимальную ширину высоту, максимальный размер файла.
Из rails приложение проверять то что является корректным изображением.

___
__*Q:*__ Есть большое приложение с десятками тысяч тестов. Как лучше всего организовать код и тесты, чтобы добиться максимальной скорости прогона тестов?  

Нужно расспаралеллить тесты. Можно раскидать функциональные куски кода по гемам. И у каждого гема будет свой набор тестов.

# Level III
__*Q:*__ nmax
[https://github.com/bukin242/nmax](https://github.com/bukin242/nmax)
__*Q:*__ currency
[https://github.com/bukin242/currency](https://github.com/bukin242/currency)
