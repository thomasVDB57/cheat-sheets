#Troubleshooten netwerkservice#



1. Link layer
    - Check the cable/port LEDs
2. Network layer
    - `ip a`
    - `ip r` (+ ping default gw)
    - `cat /etc/resolv.conf` (+ `dig www.google.com @a.b.c.d +short`)
3. Transport layer
    - `sudo systemctl status SERVICE.service`
        - `sudo systemctl start SERVICE.service`
        - `sudo systemctl enable SERVICE.service`
    - `sudo ss -tlnp`
    - `sudo firewall-cmd --list-all`
        - `sudo firewall-cmd --add-service=SERVICE --permanent`
        - `sudo firewall-cmd --add-port=PORT/tcp --permanent`
        - `sudo systemctl restart firewalld`
4. Application layer
     ```sudo journalctl -f -u SERVICE.service
     	sudo systemctl restart SERVICE.service```


###Basic systeem###
Aanpassen keyboard indien foutief
```
sudo localectl set-keymap be
```



Controleren van de adapterinstellingen

ip a

	- Is the adapter up? if not 	sudo ifup enp0s8
	
	- Heeft de adapter het juiste IP address? 
				if not			aanpassen /etc/sysconfig/network-scripts/ifcfg-enp0s8


	- Aanpassen andere instelling in ifcfg.... bijv  onboot=yes
	
	
	
	
Controleren van de services

	draaien alle nodige services?
	
		- mariadb
		- httpd
	
				if not sudo service mariadb status
					   sudo service mariadb start