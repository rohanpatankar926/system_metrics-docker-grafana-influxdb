# system_metrics-docker-grafana-influxdb
The main goal is to show how to start getting system metrics from your servers quick and easy, without spending lot of time for configuring big and complicated monitoring systems. Especially if you only need to take care for few Web servers instead of monitoring big company infrastructure with hundreds of devices.<br>
 
Make the directories and cd it<br>
`mkdir /opt/monitoring && cd /opt/monitoring`

```
server1$ docker network create monitoring
server1$ docker volume create grafana-volume
server1$ docker volume create influxdb-volume
```
Check docker networks
```
sudo docker network ls
NETWORK ID     NAME                    DRIVER    SCOPE
b7a0bea7c3ad   bridge                  bridge    local
08c8369c7c71   grafana-volume          bridge    local
c48fa2a0f282   host                    host      local
75acbb375b70   influxdb-volume         bridge    local
9712caa9f232   monitoring              bridge    local
a01591466641   monitoring_monitoring   bridge    local
d593e9702272   none                    null      local
```

check docker volumes
```
sudo docker volume ls
DRIVER    VOLUME NAME
local     grafana-volume
local     influxdb-volume
local     monitoring
```

docker compose
`sudo docker-compose up -d`
