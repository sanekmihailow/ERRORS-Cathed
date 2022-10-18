<d>
  <details>
    <summary> Links </summary>

# Links

[stackoverflow](https://stackoverflow.com/questions/60151640/kdevtmpfsi-using-the-entire-cpu#60185198)

[askubuntu](https://askubuntu.com/questions/1225410/my-ubuntu-server-has-been-infected-by-a-virus-kdevtmpfsi)

[habr](https://habr.com/ru/post/582830/)

</details>
</d>

## kdevtmpfsi miner

> Если попытаться сделать на чтение файл майнера он будет его пытаться писать в другие места (/dev/shm/ и т.д.). Он слушает рандомный порт в **netstat** видно.

- 1 Выявить зловреда в cron и убрать
```bash
for user in $(cut -f1 -d: /etc/passwd); do echo $user; crontab -u $user -l; done
```
- 2 Убить зловреда и не давать ему возможности на запись

```bash
#!/bin/bash

chmod o-w /var/tmp/
chmod o-w /tmp/
find / -iname kinsing -exec rm -fv {} \;
find / -iname kdemtmpfsi* -exec rm -fv {} \;
pkill kdevtmpfsi
pkill kinsing
find / -iname kinsing -exec rm -fv {} \;
find / -iname kdemtmpfsi* -exec rm -fv {} \;
pkill kdevtmpfsi
pkill kinsing
sleep 1
reboot
```

