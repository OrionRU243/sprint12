# sprint12
Задание 1 Представь: тебе нужно проверить, отображается ли созданный заказ в базе данных. Для этого: выведи список логинов курьеров с количеством их заказов в статусе «В доставке» (поле inDelivery = true).

запрос:

      SELECT c.login, COUNT(o.id) AS "deliveryCount" 
      FROM "Couriers" AS c 
      LEFT JOIN "Orders" AS o ON c.id = o."courierId" 
      WHERE o."inDelivery" = true 
      GROUP BY c.login;
      
Задание 2

Ты тестируешь статусы заказов. Нужно убедиться, что в базе данных они записываются корректно. Для этого: выведи все трекеры заказов и их статусы. Статусы определяются по следующему правилу: Если поле finished == true, то вывести статус 2. Если поле canсelled == true, то вывести статус -1. Если поле inDelivery == true, то вывести статус 1. Для остальных случаев вывести 0.

запрос:

       SELECT track, 
          CASE 
        WHEN finished = true THEN 2 
        WHEN cancelled = true THEN -1 
        WHEN "inDelivery" = true THEN 1 
  ELSE 0 END AS status 
      FROM "Orders";

      5. Автоматизация теста.
      скриншоты 37 и 36
Для запуска теста необходимо в файл configuration скопировить URLстенда вида [https://7b6b5ade-dbda-4523-aad6-50978727d2a9.serverhub.praktikum-services.ru](https://1f0bc3e5-1660-46e8-b514-df0376aebdb0.serverhub.praktikum-services.ru/)

В файле sendor_stand_request нажать кнопку Run
