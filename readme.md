# holnap

## Setup Server

```
mkdir -p ~/projects/holnap
scp website/* holnap:projects/holnap/
scp web holnap:projects/api/
```

```
ssh holnap
sudo service nginx start
sudo service influxdb start
sudo service grafana-server start
./projects/api/web
```
