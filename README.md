# GRIVA WordPress Frontend Cache for guests
Данный плагин позволяет почти в одно действие настроить весьма простой кэш страниц сайта на WordPress.
## Установка
В папке ```/wp-content/mu-plugins``` (если таковой нет, то создайте) поместите файл ```griva-chache.php```
Все будет подключено само и дефолтные настройки удволетворяют большинству требований
## Настройка
В угоду упрощения, все настройки находятся в самом файле. Их, всего лишь две:
```
/**
 * Относительный путь к папке хранения кэша (относительно корневого каталога сайта)
 * !! В конце строки не должно быть символов разделителя директорий
 * @var string
*/
private $cacheDir = "wp-content/cache";

/**
 * Время хранения файла кэша в секундах
 * @var int
 */
private $cacheTime = 3600;
```

## Очистка всего кеша
Просто удалите все элементы из папки ```$cacheDir```

## Системные требования
PHP 5.6+

## Где использовать?
Данный плагин не универсален. Мой паттерн использования, это сайты, где нет системы авторизации. Потому что данный плагин регенерирует кэш страницы, если вы посещаете ее как залогиненый пользователь, (что удобно, например, на сайтах - блогах, или визитках, или корпоративных сайтах).

## Ключевые особенности
- Кеширует по URL (включая GET параметры)
- Обновить кэш одной страницы можно простым ее посещением, как залогиненый пользователь
- Не применим к высоконагруженным сайтам
