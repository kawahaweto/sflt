# Домашнее задание к занятию 1 «Disaster recovery и Keepalived»
------


### Задание 1
- Дана [схема](1/hsrp_advanced.pkt) для Cisco Packet Tracer, рассматриваемая в лекции.
- На данной схеме уже настроено отслеживание интерфейсов маршрутизаторов Gi0/1 (для нулевой группы)
- Необходимо аналогично настроить отслеживание состояния интерфейсов Gi0/0 (для первой группы).
- Для проверки корректности настройки, разорвите один из кабелей между одним из маршрутизаторов и Switch0 и запустите ping между PC0 и Server0.
- На проверку отправьте получившуюся схему в формате pkt и скриншот, где виден процесс настройки маршрутизатора.

------
### Ответ

[File pkt](https://github.com/kawahaweto/sflt/blob/main/disaster-recovery/hsrp_advanced.pkt)

<details>

   
   <summary>Screenshots</summary>

![Alt text](https://github.com/kawahaweto/sflt/blob/main/disaster-recovery/t1_router1%262.png "routers")

![Alt text](https://github.com/kawahaweto/sflt/blob/main/disaster-recovery/t1_ping.png)

</details>

   ------

### Задание 2
- Запустите две виртуальные машины Linux, установите и настройте сервис Keepalived как в лекции, используя пример конфигурационного [файла](1/keepalived-simple.conf).
- Настройте любой веб-сервер (например, nginx или simple python server) на двух виртуальных машинах
- Напишите Bash-скрипт, который будет проверять доступность порта данного веб-сервера и существование файла index.html в root-директории данного веб-сервера.
- Настройте Keepalived так, чтобы он запускал данный скрипт каждые 3 секунды и переносил виртуальный IP на другой сервер, если bash-скрипт завершался с кодом, отличным от нуля (то есть порт веб-сервера был недоступен или отсутствовал index.html). Используйте для этого секцию vrrp_script
- На проверку отправьте получившейся bash-скрипт и конфигурационный файл keepalived, а также скриншот с демонстрацией переезда плавающего ip на другой сервер в случае недоступности порта или файла index.html

------
### Ответ
[bash-script](https://github.com/kawahaweto/sflt/blob/main/disaster-recovery/check_nginx.sh)

[keepalived.conf](https://github.com/kawahaweto/sflt/blob/main/disaster-recovery/keepalived.conf)   

   <details>

   <summary>Screenshots</summary>

![text](https://github.com/kawahaweto/sflt/blob/main/disaster-recovery/t2_backupstate2.png)
![text](https://github.com/kawahaweto/sflt/blob/main/disaster-recovery/t2_backupstate.png)
![text](https://github.com/kawahaweto/sflt/blob/main/disaster-recovery/t2_failed_to_master.png)
![text](./t2_master_state.png)
</details>
