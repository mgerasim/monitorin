# monitorin
Zabbix server - сервер мониторинга инфраструктуры
Требования:
Name| 	Platform| 	CPU/Memory| 	Database| 	Monitored hosts
Small| 	CentOS| 	Virtual| Appliance| 	MySQL| InnoDB| 	100

Имя: zbx01

Инициализация:

mv .bash_profile .bash_profile.bak

wget https://raw.githubusercontent.com/mgerasim/bash_profile/master/.bash_profile

Установка агента:

rpm -Uvh http://repo.zabbix.com/zabbix/3.4/rhel/7/x86_64/zabbix-release-3.4-1.el7.centos.noarch.rpm

yum -y install zabbix-agent

vi /etc/zabbix/zabbix_agentd.conf

Server=192.168.1.25

ServerActive=192.168.1.25

Hostname=srv10

systemctl restart zabbix-agent

systemctl enable zabbix-agent

cat /var/log/zabbix/zabbix_agentd.log

## Авторизация по ключу

cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys

ssh root@ast01

scp -r ~/.ssh* ast01:~/

scp -r ~/.ssh* root@ast01:~/
