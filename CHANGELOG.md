# 4.7
- Минимально необходимая версия php теперь 5.4.
- Исправлена ошибка логики построения запроса для отбора новостей в режиме вывода афишей.
- Теперь модуль не зависит от настройки `short_open_tag`.
- Исправлена mysql ошибка, при некоторых случаях выборки по автору новости.
- Исправлено некорректное формирование ссылки на аватар пользователя в dle 10.6.
- Обновлён шаблонизатор до актуальной версии.
- [beta] **Добавлена интеграция с сервисом tinyPNG.** Теперь можно удобно изменять размер и сразу же оптимизировать картинки. Отличительной особенностью сервиса является "умное" создание миниатюр в режиме crop. Для использования сервиса необходимо [получить API key](https://tinypng.com/developers). Для обработки картинок через tinyPNG необходимо заменть модификатор `image` на `tinypng`. Например: `{$el.short_story|tinypng:$noimage:'small':'all':'250':'':'crop'}`. Модификатор имеет такой же синтаксис передачи параметров, но не воспринимает значение качества картинки и принимает только следующие параметры ресайза: **portrait, landscape, auto, crop**.