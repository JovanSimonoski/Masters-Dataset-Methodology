
# Scenario

#### Prof note
 - VM
 - Container Images
 - CVE
#### Here we would have:
- Metasploitable 2
- Metasploitable 3
	- Ubuntu VM
		- Check if attacks on the Ubuntu VM are possible
	- Windows VM
		- All attacks are performed on the Windows VM
- SecGen Custom VMs - Still testing if possible
- VulHub Docker Containers inside VM
# Monitoring

#### Prof note
- Netflow
- Syslog
- Raw Packet Capture
- NTP (synchronize timestamps)

#### Here we would have:

##### NTP

- NTP Syncing will be done by configuring `ntp.finki.ukim.mk` as NTP server on all machines 
- For Linux based, in **systemd** 
	- `/etc/systemd/timesyncd.conf`
- *For older Linux distros, manual installation of NTP server*
- For Windows based, in **Windows Time Service (W32Time)**
##### Logs

- [VictoriaLogs](https://github.com/VictoriaMetrics/VictoriaLogs)
	- All the system logs are stored here
	- Pulling logs from the Kafka queue

- Log Agent on the machine
	- Collecting logs from the machine and send them to Kafka
	- Possible agents:
		- [Grafana Promtail](https://grafana.com/grafana/dashboards/20881-promtail-monitoring-metrics-and-logs/)
		- [fluentbit](https://fluentbit.io/)

- [kafka](https://kafka.apache.org/)
	- receiving and queuing logs from the log agent of each machine

![[Logs.drawio.png]]

##### NetFlow

- [nprobe](https://www.ntop.org/products/netflow-probes/nprobe/) - NetFlow probe (on the firewall)

- [ntopng](https://www.ntop.org/products/traffic-analysis/ntopng/) - NetFlow web interface

- [kafka](https://kafka.apache.org/)
	- optional: receiving and queuing NetFlow packets from the NetFlow probe (nProbe on the firewall)

![[NetFlow.drawio.png]]
# Attacks

# Timing

# Benign Traffic - To discuss

# Automatic Labeling