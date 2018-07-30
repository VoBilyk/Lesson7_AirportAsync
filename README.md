# Airport Dispatcher RESTful

## Що зроблено:
* Створенно RESTful Web Api проект, який виконує функції диспетчера аеропорту
* Предметна область спроектована за [файл](https://docs.google.com/document/d/1ND_K4P_XMS5WfbUnIVUBkqEn6aGjCtZ-qGPMTl5n7KM/edit?usp=sharing)
* Проект створено за багаторівневою архітектурою (Presentation layer, Business layer, Data Access layer)
* Data Access layer сформовано за UnitOfWork принципом

*Використано IoC контейнер, Fluent Validator, AutoMapper, Bogus, Newtonsoft.Json*

## Upd1: підключено базу даних
* Підключено MS Server Database за допомогою ORM EntityFramework Core
* Реалізовано звязки між таблицями за допомогою FluentApi
* Налаштовано деякі атрибути властивостей моделей за допомогою DataAnnotation

## Upd2: добавлено тести
  * Все запросы на создание и обновление сущностей покрыты юнит-тестами, которые проверяют валидацию и маппинг.
  * Написано интеграционные тестов при работе с базой данных.
  * Написано тесты, которые проверяют работу контроллеров.
  * Написано функциональные тестов, которые вызывают API и проверять результат.
*Для Тестів використано бібліотеки NUnit, FakeItEasy*

## Upd3: добавлено асинхронність
* Тепер всі запити до контролерів виконуються асинхронно.
* Добавлено завантаження даних з [mockApi](http://5b128555d50a5c0014ef1204.mockapi.io/crew) за допомогою _GET api/crews/mockapi_
* При завантаженні даних з mockApi вони зберігаються асинхронно в базі даних і лог файлах з датою створення запиту в папці logs WebApi проекту.
* Реалізовано імітацію фіктивної загрузки всіх елементів flights за допомогою _GET: api/flights/await?delay:value_, де value - час в мілісикундах 

