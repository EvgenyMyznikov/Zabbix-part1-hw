# Домашнее задание к занятию "`9.2.Zabbix.Часть 1`" - `Myznikov Evgeny`

### Задание 1
![Zabbix_Server](https://github.com/EvgenyMyznikov/Zabbix-part1-hw/blob/main/img/Zabbix-part1-2022-11-20%20164856.png?raw=true)
Command list:
sudo apt install postgresql
sudo wget https://repo.zabbix.com/zabbix/6.0/debian/pool/main/z/zabbix-release/zabbix-release_6.0-4%2Bdebian11_all.deb
sudo dpkg -i zabbix-release_6.0-4+debian11_all.deb
sudo apt update && sudo apt upgrade -y
sudo apt install zabbix-server-pgsql zabbix-frontend-php php7.4-pgsql zabbix-apache-conf zabbix-sql-scripts nano -y
sudo apt install zabbix-agent2 zabbix-agent2-plugin-*
sudo -u postgres createuser --pwprompt zabbix
sudo -u postgres createdb -O zabbix zabbix
zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix
sudo systemctl restart zabbix-server apache2
sudo systemctl enable zabbix-server apache2
sudo nano /etc/zabbix/zabbix_server.conf
sudo systemctl restart zabbix-agent2
sudo systemctl enable zabbix-agent2

### Задание 2
![Hosts](https://github.com/EvgenyMyznikov/Zabbix-part1-hw/blob/main/img/Configuration-2022-11-24%20125938.png?raw=true)

![Latest_data](https://github.com/EvgenyMyznikov/Zabbix-part1-hw/blob/main/img/LastDataHosts-2022-11-24%20134436.png?raw=true)

![zabbix_agent_log_host1](https://github.com/EvgenyMyznikov/Zabbix-part1-hw/blob/main/img/Host1_log-%202022-11-24%20180302.png?raw=true)

![zabbix_agent_log_host2](https://github.com/EvgenyMyznikov/Zabbix-part1-hw/blob/main/img/Host2_log-2022-11-24%20180657.png?raw=true)

Command list:
sudo wget https://repo.zabbix.com/zabbix/6.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_6.0-4%2Bubuntu22.04_all.deb
sudo dpkg -i zabbix-release_6.0-4+ubuntu22.04_all.deb
sudo apt update && sudo apt upgrade -y
sudo apt install zabbix-agent2 zabbix-agent2-plugin-*
sudo systemctl restart zabbix-agent2
sudo systemctl enable zabbix-agent2
sudo systemctl status zabbix-agent2.service
sudo nano /etc/zabbix/zabbix_agent2.conf    # change server ip
sudo systemctl restart zabbix-agent2.service

