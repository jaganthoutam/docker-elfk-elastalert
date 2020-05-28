# Elastic stack (ELK) on Docker

  * Use if you use CIS OS Hardening.
```bash
systemctl restart firewalld
systemctl enable firewalld
#ForKibana
firewall-cmd --permanent --zone=public --add-port=80/tcp
firewall-cmd --permanent --zone=public --add-port=443/tcp
firewall-cmd --zone=public --add-port=6443/tcp --permanent
firewall-cmd --zone=public --add-port=2376/tcp --permanent
firewall-cmd --zone=public --add-port=2377/tcp --permanent
firewall-cmd --zone=public --add-port=2379/tcp --permanent
firewall-cmd --zone=public --add-port=2380/tcp --permanent
firewall-cmd --zone=public --add-port=4789/udp --permanent
firewall-cmd --zone=public --add-port=7946/tcp --permanent
firewall-cmd --zone=public --add-port=7946/udp --permanent
firewall-cmd --zone=public --add-port=10250/tcp --permanent
firewall-cmd --zone=public --add-port=5044/tcp --permanent
firewall-cmd --zone=public --add-port=5044/udp --permanent
firewall-cmd --reload
#For Elastic Search
firewall-cmd --zone=public --add-port=8080/tcp --permanent  
firewall-cmd --zone=public --add-port=1337/tcp --permanent
firewall-cmd --zone=public --add-port=27017/tcp --permanent
firewall-cmd --zone=public --add-masquerade --permanent
firewall-cmd --permanent --zone=public --change-interface=docker0
firewall-cmd --permanent --direct --add-rule ipv4 filter INPUT 4 -i docker0 -j ACCEPT
firewall-cmd --reload
systemctl restart firewalld
systemctl restart docker
```
## Elasticsearch docker-compose 
```bash
https://github.com/jaganthoutam/docker-elk-new.git
cd docker-elk-new
docker-compose up -d

```
