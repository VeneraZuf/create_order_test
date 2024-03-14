# Практический блок. Вторая часть диплома.
### Работа с базой данных. Задание 1.
Скриншот результата запроса check_created_order_in_database

Запрос: 

```
SELECT c.login, COUNT(o.id) AS "deliveryCount" FROM "Couriers" AS c INNER JOIN "Orders" AS o ON c.id = o."courierId" WHERE o."inDelivery" = true GROUP BY c.login;
```

### Работа с базой данных. Задание 2.
Скриншот результата запроса check_orders_are_written_correctly

Запрос: 

``` 
SELECT track, CASE WHEN finished = true THEN 2 WHEN cancelled = true THEN -1 WHEN "inDelivery" = true THEN 1 ELSE 0 END AS status FROM "Orders";
```

### Автоматизация теста к API.
Скриншот результата запроса check_get_order_data_by_track_number
- Для запуска тестов должны быть установлены пакеты pytest и requests
- Запуск всех тестов выполняется командой pytest