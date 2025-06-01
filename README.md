#grafana_and_prometheus
#grafana_and_prometheus
на двух серверах
dnf install grafana golang-github-prometheus prometheus-node_exporter -y
в конце файла 
nano /etc/prometheus/prometheus.yml
меняем
'hq-srv:9100','br-srv:9100'

![image](https://github.com/user-attachments/assets/a829cb53-c0cb-4e0c-9d86-04fc34a2285e)

nano /etc/systemd/system/node_exporter.service
[Unit]
Description=Node Exporter
After=network.target
[Service]
Type=simple
ExecStart=/usr/bin/node_exporter
[Install]
WantedBy=multi-user.target

![image](https://github.com/user-attachments/assets/4d886978-0a5e-423e-a686-f44c55f89818)


systemctl daemon-reload
systemctl enable --now node_exporter.service
systemctl enable --now prometheus
systemctl restart prometheus
systemctl enable --now grafana-server
systemctl restart grafana-server
google grafana dashboards
node exporter resources
copy id

http://192.168.100.1:3000
admin admin

connections

Prometheus
add
conection
http://localhost:9090
add

dashboards new import
11074 url load


bind mon IN A 100.1
restart  
