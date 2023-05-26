# 10.4-HW
### Домашнее задание к занятию 10.4 - "Резервное копирование. Bacula" - Семкин Вячеслав
***
### Задание 1

В чём разница между:

- полным резервным копированием,
- дифференциальным резервным копированием,
- инкрементным резервным копированием.

*Приведите ответ в свободной форме.*

**Ответ:**

Peacemaker — это менеджер ресурсов кластера.

***
### Задание 2

Установите программное обеспечении Bacula, настройте bacula-dir, bacula-sd,  bacula-fd. Протестируйте работу сервисов.

*Пришлите:*   
*- конфигурационные файлы для bacula-dir, bacula-sd,  bacula-fd,*   
*- скриншот, подтверждающий успешное прохождение резервного копирования.*

**Ответ:**
Конфигурационные файлы прикреплены.

Копирование произведено.

![2-1](https://github.com/SemkinVA/10.4-HW/blob/main/2-1.png)

***
### Задание 3

Установите программное обеспечении Rsync. Настройте синхронизацию на двух нодах. Протестируйте работу сервиса.

*Пришлите рабочую конфигурацию сервера и клиента Rsync блоком кода в вашем md-файле.*

**Ответ:**


![3-1](https://github.com/SemkinVA/10.4-HW/blob/main/3-1.png)

Конфигурация Nod1
```
pid file = /var/run/rsyncd.pid
log file = /var/log/rsyncd.log
transfer logging = true
munge symlinks = yes
[data]
path = /data
uid = root
read only = yes
list = yes
comment = Data backup Dir!!!
auth users = backup
secrets file = /etc/rsyncd.scrt
```
Конфигурация Nod2
```
pid file = /var/run/rsyncd.pid
log file = /var/log/rsyncd.log
transfer logging = true
munge symlinks = yes
[data]
path = /root
uid = root
read only = yes
list = yes
comment = Data backup Dir
auth users = backup
secrets file = /etc/rsyncd.scrt
```
***


