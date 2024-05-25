# project-03

## Сервисы, для которых не писались роли в ansible

- openvpn-server
- openvpn-client
- pgadmin
  


## Настройка Mail сервера

Во время настроки mail-сервера в логах отправки было выявлено, что:

May 23 09:56:18 server-02 postfix/smtp[261379]: 779AD671A0: to=<hidden@hidden>, relay=none, delay=151, delays=0.1/0.02/150/0, dsn=4.4.1, status=deferred (connect to hidden.mail.protection.outlook.com[52.101.68.36]:25: Connection timed out)

Запрос в службу технической поддержки результатов не дал:

![image](https://github.com/dashaakinshina/project-03/assets/122722303/f82969e7-8255-40b9-b4bf-98d017ce67e0)
