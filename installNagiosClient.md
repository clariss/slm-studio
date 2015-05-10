## Install Nagios NRPE in clients ##

---


Each one of the clients will need to have this installed and configured. On each machine that the Nagios host will contact to execute plugins remotely, issue
```
apt-get install nagios-nrpe-server
apt-get install nagios-plugins
```

Make sure the nrpe daemon is running:
```
netstat -at | grep nrpe
```
The output out this command should show something like this:
```
tcp 0 0 *:nrpe *:* LISTEN
```


Edit NRPE configuration file to allow monitoring host access to remote host:
```
vi /etc/nagios/nrpe_local.cfg
```

add the following line (replace IP address with IP of monitoring host):
```
allowed_hosts=192.168.0.4
command[check_users]=/usr/lib/nagios/plugins/check_users -w 1 -c 2
command[check_load]=/usr/lib/nagios/plugins/check_load -w 2 -c 3
```

Restart the NRPE daemon with
```
/etc/init.d/nagios-nrpe-server restart 
```

Test that remote and monitoring hosts can communicate. On the monitoring host, issue (replace IP by the one of the remote host):
```
/usr/lib/nagios/plugins/check_nrpe -H 192.168.0.11
```

You should get back the NRPE version:
```
NRPE v2.12
```

Try a simple check from the monioring host (replace the ip by the one of the remote host):
```
/usr/lib/nagios/plugins/check_nrpe -H 192.168.0.11 -c check_users
```

references:

http://debianclusters.org/index.php/Nagios_NRPE_Addon_Installation_and_Configuration

http://forum.centreon.com/showthread.php/11775-NRPE-Install-Tutorial