# grafana-and-prometheus
grafana prometheus
dnf install grafana golang-github-prometheus prometheus-node_exporter -y
nano /etc/prometheus/prometheus.yml
----
'hq-srv:9100','br-srv:9100'
----
nano /etc/systemd/system/node_exporter.service
--
[Unit]
Description=Node Exporter
After=network.target
[Service]
#User=nodeusr
#Group=nodeusr
Type=simple
ExecStart=/usr/bin/node_exporter
[Install]
WantedBy=multi-user.target
-
systemctl daemon-reload
systemctl enable --now node_exporter.ser
----systemctl restart prometheus
---systemctl enable grafana-server --now
---systemctl status grafana-server
---
google grafana dashboards
node exporter resources
copy id
----
http://192.168.100.1:3000
admin admin
---
connections
--
Prometheus
add
--- conection
http://localhost:9090
add
--
dashboards new import
11074 url load


bind mon IN A 100.1
restart 
