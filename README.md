# Ballu_ASP-100
MQTT для бризера Ballu ONEAIR ASP-100

Данный конфиг использует Packages https://www.home-assistant.io/docs/configuration/packages/

Для работы с бризером необходимо установить и настроить MQTT брокер EMQX или Mosquitto 1.5.11 (Не работает с mosquitto выше 1.5.11)
В MQTT брокере необходимо включить и настроить поддержку SSL на порту 8883 (Сертификат можно любой, бризер не проверяет сертификат сервера mqtt) Включить авторизацию по логину-паролю и добавить пользователя rusclimate с паролем указанным в конфиге (Логин и пароль зашиты в прошивку бризера и являются одинаковыми для всех устройств)

На вашем роутере необходимо настроить DNS запись mqtt.cloud.rusklimat.ru c IP вашего MQTT, после этого на несколько секунд отключить питание бризера для сброса кеша DNS.

Подключиться к вашему MQTT серверу mqtt explorer'ом и найти топик rusclimate/<device_type>/<device_id>/

Заменить в конфиге ballu_asp-100.yaml <device_type>/<device_id> и < MAC> на данные вашего устройства которые отображаются в MQTT Explorer.

Пример: 

command_topic: rusclimate/69/c9b7536b6fe724cababcf9ca3add8/control/ 

MAC пишется слитно, без разделителей

identifiers: 64b1045c5316

Поместить полученный конфиг в папку Packages вашего HA
