# Общее описание архитектуры
1. Архитектура
Выбранное решение для поставленной задачи - микросервисная архитектура, так как оан отвечает требованиям, позволяет проводить масштабирование, добавлять новые домены и функции, не привязываться к архитектуре ранее реализованной части приложения, такэе можно распараллелить разработку. Монолит не выбран, так как выбрано относительно большое кол-во доменов (более 5), что усложнит и увелисит время разработки.
2. БД
СУБД PostgreSQL, так как предоставляется большинством облачных сервисов, обладает возможностями полнотекстового поиска, производительна.
3. Асинхронные интеграции
Асинхронные взаимодействия выбраны для отправки уведомлений и сохранения показателей тренировки, так как пользователь может находиться в зоне отсутствия интернета какое-то время.
Выбрана схема логов и инструмент Kafka , чтобы иметь возможность перечитывать сообщений.
4. Синхронные интеграции
Синхронные интеграции релаизуются на основе архитектурного стиля REST.
6. API Gateway
Внутренние и внешние интеграции реализуются через API Gateway
7. Все ресурсы для нового приложения арендуются в облачных сервисах.
8. Все обращения к БД и API Gateway должны быть рализованы с аутентификацией и авторизацией.
