Changing keyboard

sudo localectl set-keymap be



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