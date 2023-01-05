# Домашнее задание к занятию "`9.2. Zabbix. Часть 1`" - `Качан Олег`

---

### Задание 1.

Установите Zabbix Server с веб-интерфейсом.

`Скриншот запущенного сервера:`

![alt text](https://github.com/otuzi/09-02-hw/blob/main/img/image1.png)

`Скриншот запущенного сервера в yandex.cloud:`

![alt text](https://github.com/otuzi/09-02-hw/blob/main/img/image2.png)

---

### Задание 2.

Установите Zabbix Agent на два хоста.

Приложите скриншот раздела Configuration > Hosts, где видно, что агенты подключены к серверу. Приложите скриншот лога zabbix agent, где видно, что он работает с сервером. Приложите скриншот раздела Monitoring > Latest data для обоих хостов, где видны поступающие от агентов данные. Приложите текст использованных команд в GitHub.

`Скриншот раздела Configuration > Hosts:`

![alt text](https://github.com/otuzi/09-02-hw/blob/main/img/image3.png)

`Скриншот запущенных серверов в yandex.cloud:`

![alt text](https://github.com/otuzi/09-02-hw/blob/main/img/image4.png)

`Скриншот лога zabbix agent:`

![alt text](https://github.com/otuzi/09-02-hw/blob/main/img/image5.png)

`Если подключение zabbix сервера к zabbix агенту прошло успешно то в логах он не показывает данное подключение`

`С какого zabbix сервера zabbix агент позволяет подключения можно увидеть в файле конфигурации vim /etc/zabbix/zabbix_agentd.conf , скриншот`

![alt text](https://github.com/otuzi/09-02-hw/blob/main/img/image6.png)

`Скриншот раздела Monitoring > Latest data для обоих хостов:`

![alt text](https://github.com/otuzi/09-02-hw/blob/main/img/image7.png)

Текст используемых команд:

1. `wget https://repo.zabbix.com/zabbix/6.0/debian/pool/main/z/zabbix-release/zabbix-release_6.0-4%2Bdebian11_all.deb`
2. `sudo dpkg -i zabbix-release_6.0-4+debian11_all.deb`
3. `sudo apt update`
4. `sudo apt install zabbix-agent`
5. `sudo systemctl restart zabbix-agent`
6. `sudo systemctl enable zabbix-agent`
7. `sudo sed -i 's/Server=127.0.0.1/Server=10.128.0.8/g' /etc/zabbix/zabbix_agentd.conf`
8. `vim /etc/zabbix/zabbix_agentd.conf`
9. `sudo systemctl restart zabbix-agent`
10. `systemctl status zabbix-agent`
11. `tail -f /var/log/zabbix/zabbix_agentd.log`

---