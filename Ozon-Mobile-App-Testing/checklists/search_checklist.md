## Чек-лист для проверки поиска в приложении Ozon

**Устройство**: Realme RMX3085 (8/128GB, Android 13)  
**Версия приложения**: Ozon 18.30.0  
**Дата тестирования**: 16.06.2025  

| №  | ID           | Проверка                     | Ввод данных                              | Ожидаемый результат                     | Статус | Скриншот                          |
|----|--------------|------------------------------|------------------------------------------|-----------------------------------------|--------|-----------------------------------|
| 1  | TC-SEARCH-001 | Корректный запрос           | «Футболка тестировщика»                  | Релевантные товары с ценами и рейтингами | ✅     | ![correct](/Ozon-Mobile-App-Testing/screenshots/correct_query.png) |
| 2  | TC-SEARCH-002 | Пустой запрос               | `(пусто)`                                | Подсказка «Введите запрос»              | ⚠️     | ![empty](/Ozon-Mobile-App-Testing/screenshots/empty_query.png)                                  |
| 3  | TC-SEARCH-003 | Спецсимволы                 | `&@_#_#&@-#+₽(!₽!₽!₽(#!?#`              | «Ничего не найдено»                     | ⚠️     | ![bug](/Ozon-Mobile-App-Testing/screenshots/ozon_bad_results_rmx3085.png) |
| 4  | TC-SEARCH-004 | Длинный запрос (150+ символов) | «Мама мыла раму...» (полный текст ниже) | Обрезка запроса   | ✅     | ![long](/Ozon-Mobile-App-Testing/screenshots/long_correct_query.png) |
| 5  | TC-SEARCH-005 | Эмодзи                      | «🎉🎉🎉»                                 | Игнорирование эмодзи                    | ✅     | ![emoji](/Ozon-Mobile-App-Testing/screenshots/emoji_query.png) |
| 6  | TC-SEARCH-006 | История поиска              | «Книги по тестированию» → перезапуск     | Сохранение в истории                    | ✅     | ![history](/Ozon-Mobile-App-Testing/screenshots/test_memory_query.png) |

**Примечания**:
1. Полный текст длинного запроса (152 символа):  
   `Мама мыла раму... [и еще 130 символов]...`
2. Баг-репорт по спецсимволам: [BUG-003](/Ozon-Mobile-App-Testing/bug_reports/ozon_search_special_chars.md)
