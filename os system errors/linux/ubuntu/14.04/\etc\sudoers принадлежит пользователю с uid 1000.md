<d>
  <details>
    <summary> Links </summary>

# Links

[askubuntu](https://askubuntu.com/questions/513523/sudo-doesnt-work-etc-sudoers-is-owned-by-uid-1000-should-be-0)

[cyberforum](https://www.cyberforum.ru/ubuntu-linux/thread1375811.html)

[ubuntu](https://forum.ubuntu.ru/index.php?topic=224191.0)

[sergeymukhin](https://sergeymukhin.com/blog/povrezhdennyy-etc-sudoers-oshibka-v-sintaksise)

[qna.habr](https://qna.habr.com/q/572143)

</details>
</d>

> sudo: /etc/sudoers принадлежит пользователю с uid 1000, а должен принадлежать пользователю с uid 0

> sudo: /etc/sudoers.d принадлежит пользователю с uid 1000, а должен принадлежать пользователю с uid 0

> sudo: no valid sudoers sources found, quitting

> sudo: не удаётся инициализировать модуль политики

- способ 1. (легкий и удаленный)

открываем два терминала ssh на первом пишем `echo $$` получаем пид, например: 3440

На втором `pkttyagent --process 3440`

Переходим на первый вводим команду `pkexec chown root:root /etc/sudoers /etc/sudoers.d -R`

Переходим на второй вводим пароль пользователя, получаем сообщение "==== AUTHENTICATION COMPLETE ==="

Переходим снова на верый и на всякий вводим `pkexec visudo`

На втором авторизуемся, переходим на первый -> **F10** -> **save**

Радуемся восстановленному sudo

- способ 2. (средний, не удаленный - требуется livecd)

Проделываем операцию монтирования с Livecd. 

```bash
fdisk -l; |grep /dev/
sudo su -
mount /dev/sda2 /mnt
mount --bind /dev /mnt/dev
mount --bind /sys /mnt/sys
mount --bind /proc /mnt/proc
```

Берем аттрибуты из livecd. Из минусов заменятся аттрибуты в /etc на аттрибуты из livecd.
```bash
cd /etc
getfacl --recursive . >/tmp/acl
getfattr --recursive --dump . >/tmp/attr
cd /mnt/etc
setfacl --restore=/tmp/acl
setfattr --restore=/tmp/attr
```

- способ 3. (средний, не удаленный - требуется Livecd)

Проделываем процедуру монтирования из способа 2, затем заходим в смонтированную среду и обнуляем права

```bash
chroot /mnt
#chroot /mnt /bin/sh
mount -a
chown -R 0:0 /etc/sudoers.d/
chown -R 0:0 /etc/sudoers
chown -R 0:0 /var/lib/sudo
chmod 440 /etc/sudoers
chmod 440 /etc/sudoers.d
#chown -R root:root /mnt/lib{,32,64}
#chown -R root:root /mnt/bin
#chown -R root:root /mnt/boot
#chown -R root:root /mnt/sbin
#chown -R root:root /mnt/usr
#chown -R root:root /mnt/srv
```


