<d>
<details>
    <summary> Links </summary>

[staoverflow](https://stackoverflow.com/questions/7942154/mysql-error-2006-mysql-server-has-gone-away)

[haydenjames.io](https://haydenjames.io/mysql-server-has-gone-away-error-solutions/)

[bitrix](https://dev.1c-bitrix.ru/community/webdev/user/94272/blog/11593/)

</details>
</d>

> Возникла во время восстановления базы данных

- 1 первым делом проверить память через free htop (у меня ошибка возникала когда oom killer убивал mysql из-за недостатка памяти)
```
чтобы освободить память сделал reboot, затем в процессе восстановления она снова возникала, тут главное обновить страницу и продолжать восстановление
```
- 2 Увеличть max_allowed_packet в mysql
```
[mysqld]
max_allowed_packet=1024M
```
- 3 Увеличиь тайм аут бд в bitrix в **bitrix/php_interface/after_connect.php**
```
$DB->Query("SET wait_timeout=28800");
```
