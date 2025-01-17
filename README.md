# Домашнее задание к занятию «Система мониторинга Zabbix»

## Задание 1
![Описание изображения](/screen_1.png)

sudo apt install -y postgresql-common
sudo /usr/share/postgresql-common/pgdg/apt.postgresql.org.sh

sudo apt update
sudo apt install postgresql-16

wget https://repo.zabbix.com/zabbix/6.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_latest_6.0+ubuntu22.04_all.deb
dpkg -i zabbix-release_latest_6.0+ubuntu22.04_all.deb
apt update

apt install zabbix-server-mysql zabbix-frontend-php zabbix-apache-conf zabbix-sql-scripts zabbix-agent

sudo -u postgres createuser --pwprompt zabbix
sudo -u postgres createdb -O zabbix zabbix

zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix

systemctl restart zabbix-server zabbix-agent apache2

## Задание 2

![Описание изображения](/screen_2.png)
![Описание изображения](/screen_3.png)
![Описание изображения](/screen_4.png)

10  sudo wget https://repo.zabbix.com/zabbix/6.0/ubuntu-arm64/pool/main/z/zabbix-release/zabbix-release_latest_6.0+ubuntu22.04_all.deb
11  dpkg -i zabbix-release_latest_6.0+ubuntu22.04_all.deb
12  sudo dpkg -i zabbix-release_latest_6.0+ubuntu22.04_all.deb
13  apt update
15  sudo apt install zabbix-agent
16  systemctl restart zabbix-agent
