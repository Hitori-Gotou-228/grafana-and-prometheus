#grafana_and_prometheus
на двух серверах <br/>
dnf install grafana golang-github-prometheus prometheus-node_exporter -y <br/>
в конце файла nano /etc/prometheus/prometheus.yml  <br/>
меняем 'lochalhost:9090',hq-srv:9100','br-srv:9100'  <br/>

![image](https://github.com/user-attachments/assets/a829cb53-c0cb-4e0c-9d86-04fc34a2285e)

nano /etc/systemd/system/node_exporter.service <br/>
[Unit]
Description=Node Exporter
After=network.target
[Service]
Type=simple
ExecStart=/usr/bin/node_exporter
[Install]
WantedBy=multi-user.target

![image](https://github.com/user-attachments/assets/4d886978-0a5e-423e-a686-f44c55f89818)


systemctl daemon-reload <br/>
systemctl enable --now node_exporter.service <br/>
systemctl enable --now prometheus <br/>
systemctl restart prometheus <br/>
systemctl enable --now grafana-server <br/>
systemctl restart grafana-server <br/>
google grafana dashboards <br/>
node exporter resources <br/>
copy id <br/>

http://192.168.100.1:3000 <br/>
admin admin <br/>

connections <br/>

Prometheus <br/>
add <br/>
conection <br/>
http://localhost:9090 <br/>
add <br/>

dashboards new import <br/>
11074 url load <br/>


bind mon IN A 100.1 <br/>
restart <br/>
