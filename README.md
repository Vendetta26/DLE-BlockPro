# Краткая информация о модуле
- **ВНИМАНИЕ!** Работа модуля в кодировке windows-1251 не гарантируется, не проверялась и проверяться когда-либо автором модуля не будет. Техническая поддержка кодировки windows-1251 оказывается с наименьшим приоритетом и только при наличии желания и времени. Это принципиальная позиция и меняться не будет. В общем рекомендую переходить на нормальную кодировку сайта :smile:
- На данный момент модуль находится в стадии бета тестирования.
- Краткая информация о шаблонных тега прописана в шаблоне **{THEME}/blockpro/blockpro.tpl**
- Более детальная информация по используемому шаблонизатору модуля находится в [документации по шаблонизатору](https://github.com/bzick/fenom/blob/master/docs/ru/readme.md)
- Все вопросы, баги и проблемы прошу писать в [посте о бетатестировании](http://pafnuty.name/main/154-blockpro4-beta.html), а если требуется предоставить доступ к закрытым данным (сайт, если он закрыт или нт желания светить, ftp и пр.), то пишем на [email](pafnuty10@gmail.com) или [в личку на сайте](http://pafnuty.name/index.php?do=pm&doaction=newpm&username=%CF%E0%F4%CD%F3%F2%E8%C9).
- Сообщаем о багах в следующем формате: 
    + Строка подключения.
    + Содержимое шаблона блока.
    + Наблюдаемый текст ошибки.
    + Данные о статистике блока (прописываем в строке подключения ``&showstat=y``)

# Зарезервированные шаблонные теги:

- ``{$block_id}`` - уникальный идентификатор блока, формируется из текущего конфига блока (не включая номер текущей страницы).
- ``{$theme}`` - аналог {THEME}
- ``{$list}`` - массив, с отобранными по параетрам строки подключения, новостями.
- ``{$member_group_id}`` - выводит id групы текущего пользователя.
- ``{$pages}`` - выводит постраничную навигацию.
- Теги, зарезервированные внутри цикла, где ``$el`` - элемент внутри цикла (можно менять на свой, по усмотреню):
    + ``{$el.favorites}`` - выводит favorites новости.
    + ``{$el.url}`` - сформированный url в соответствии с настройками ЧПУ.
    + ``{$el.showRating}`` - показывает рейтинг новости.
    + ``{$el.showRatingCount}`` - показывает счётчик рейтинга (обновляется при выставлении рейтинга), если нужно просто вывести счётчик - можно использовать ``{$el.rating_count}``.
    + ``{$el.editOnclick}`` - выводит атрибут onclick для фомирования "кнопки" редактирования. 
    + ``{$el.avatar}`` - выводит аватар пользователя, если в строке подключения указана переменная ``&avatar=y``
- Теги, которые формируются автоматически (выводят содержимое соответствующих даных из БД). 
    + ``{$el.id}``
    + ``{$el.autor}``
    + ``{$el.date}``
    + ``{$el.short_story}``
    + ``{$el.full_story}``
    + ``{$el.xfields}``
    + ``{$el.title}``
    + ``{$el.category}``
    + ``{$el.alt_name}``
    + ``{$el.allow_comm}``
    + ``{$el.comm_num}``
    + ``{$el.fixed}``
    + ``{$el.tags}``
    + ``{$el.news_read}``
    + ``{$el.allow_rate}``
    + ``{$el.rating}``
    + ``{$el.vote_num}``
    + ``{$el.votes}``
    + ``{$el.view_edit}``
    + ``{$el.editdate}``
    + ``{$el.editor}``
    + ``{$el.reason}``

- Модификаторы, используемые в шаблонах (можно применять к любым данным, но модификаторы не проверяют входящие данные, имейте ввиду):
    + [Список модификаторов по умолчанию](https://github.com/bzick/fenom/blob/master/docs/ru/syntax.md#%D0%9C%D0%BE%D0%B4%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80%D1%8B), используемых шаблонизатором.
    + ``{$foo|image}`` - выводит картинку новости, пример использования в шаблоне.
    + ``{$foo|limit:500}`` - ограничивает символы в тексте с учётом слов.
    + ``{$foo|catinfo}`` - выводит информацию о категориии новости.
    + ``{$foo|dateformat}`` - выводит отформатированную дату новости.
    + ``{$foo|declination}`` - выводит слово (без числа) с правильным склонением в зависимости от числа, к которому применяется.


# Установка BlockPro
- Перекодировать файлы в windows-1251 при необходимости. 
- Залить содержимое папки upload в корень сайта. **ВНИМАНИЕ!** Папка с шаблонами модуля содержит шаблон blockpro.tpl, имя его совпадает с уже существующим, будьте осторожны.
- Запустить файл **/blockpro_install.php** и следовать инструкциям.