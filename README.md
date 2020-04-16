# changelog
change log for finish line prototype of top-secret service

# update 13.04.20 - 16.04.20
- Начата работа над API и интерфейсом. Готова разметка, также часть страниц. Используется adminlte, bootstrap, jquery. 
- Начата и продолжается работа над API. Готов механизм авторизации, используя JWT (токен). Можно использовать как в API, так и в интерфейсе. Двойная защита, токен подписывается секретным ключом, пароли хешируются. Куки в итоговом проекте не будут использоваться с целью безопасности. 
- Также, взаимодействие с БД ведется через модели (ORM Bookshelf (knex, postgres)). Готовы миграционные данные для таблиц, создание и развертывание теперь будет гораздо быстрее..
# update 11.04.20
- Готов функциональный прототип
# update 07.04.20 - 08.04.20
- Из-за болезни интерфейсника, самостоятельно полностью переписана форма и механизм взаимодействия. Теперь у нас есть /create_flat, и на ближайшее будущее - заглушки для /create_cottage и /create_room/.
- Адрес, информация о доме, фотографии теперь подгружаются динамически. Форма готова, меньше чем за день. 
- Сервис окончательно онлайн. 
- Делаем последние правки перед "релизом" прототипа. За неделю разрешено 20 задач, вставших в процессе разработки.  
# update 05.04.20 - 06.04.20
- Перенесли БД на сервер. Было больно.
- Карточка объекта теперь отображается нормально.
- Разработчик, которому отправили формы на доработку, внезапно заболел ауральной мигренью. Не проблема, двигаемся дальше.

# update 04.04.20
- Была проведена генеральная уборка кода, в частности роутеров для разных модулей, для дальнейшего удобства добавления новых фич, исправления и документирования. В роутере index теперь 50 строк кода, а не 120, как и должно быть. /objects_all теперь /objects/all
- Найден и обезврежен баг в таблице объектов, проявлявшийся в лимите символов для категории. 
- Обезврежен баг, который выводил системную ошибку, вместо нужной 404 при попытке отобразить отсутствующий объект 
- Собраны все необходимые формы для финальной компиляции в единую при создании объекта. 

# update 03.4.20
- Нашли, оплатили провайдера для БД, переносим.
- Внесены правки в /objects/create. Представление также будет полностью изменено, с использованием ajax
- На всякий случай прикручена валидация к /objects/:id. Попытка ввести туда произвольные символы приводила к вылету и перезагрузке приложения. 

# update 02.4.20
- Налажена первоначальная система открытых и закрытых безопасных репозиториев.
- Потихоньку переносим в онлайн. Доступно на Heroku. Перенесли серверную часть. БД пока что нет, ищем провайдера.
- Поправлен роутинг объектов. Для полного списка объектов - /objects_all, (если установлено isAdmin), для списка юзера - /objects, для отображения карточки конкретного объекта - /objects/:id

# update 01.04.20 
- Создана страница сhangelog
- Сделан логотип
- Перерисована часть формы создания объекта
- Тип формы изменен на multipart
- Исправлена кодировка в /account. Больше нет кракозябр
- Изменен один из запросов к схеме базы. Случайность теперь обеспечена: 
```sql
OFFSET floor(random() * 666) 
``` 
Нужно изменить множитель, ххххх могут быть проблемой при таком запросе.

