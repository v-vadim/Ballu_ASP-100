# Ballu_ASP-100
MQTT для бризера Ballu ONEAIR ASP-100
Данный конфиг использует Packages https://www.home-assistant.io/docs/configuration/packages/
Для работы с бризером необходимо установить и настроить MQTT брокер EMQX (На данный момент с mosqito не работает)
В MQTT брокере необходимо включить на настроить поддержку SSL на порту 8883.
Включить авторизацию по логину паролю и добавить пользователя rusclimate
На вашем роутере необходимо настроить DNS запись mqtt.cloud.rusklimat.ru c IP вашего MQTT
Перезагрузить бризер, для обновления сетевых настроек
Подключиться к вашему MQTT любым mqtt explorer и найти топик rusclimate/<device_type>/<device_id>/
Вписать в конфиг ballu_asp-100.yaml эти данные, и MAC вашего устройства
Поместить полученный файл в папку Packages вашего HA
