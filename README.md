# Search Server - поисковая система
SearchServer - класс, реализующий поиск по набору документов.
### :information_source: Основные возможности:
  * Документы добавляются в текстовом виде. Каждый документ может иметь рейтинг и статус (ACTUAL, IRRELEVANT, BANNED,	REMOVED).
  * Поиск происходит по ключевым словам документа, исключая минус-слова и пропуская стоп-слова.
  * Стоп-слова добавляются либо при создания экземпляра класса, либо соотвествующим методом.
  * При запросе наиболее релевантных документов, выдача сортируется сначала по релевантности, потом по рейтингу.
  * Релевантность рассчитывается в соответствии с мерой TF-IDF.
  * Запрашивать можно документы с определенным статусом, либо фильтруя в соответствии с переданной функцией-предикатом.
  * Методы поиска допускают распараллеливание в соответствии с переданной политикой.
В распараллеливании участвует ассоциативный контейнер ConcurrentMap (обертка над std::map), допускающий чтение/запись в несколько потоков.
