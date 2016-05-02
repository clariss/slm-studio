## Fix SNMP in Debian 6 h0wt0 ##

---

Because of a non-free licensing issue, Debian 6 needs to be configured to get some non-free packages to fix a SNMP problem.
First, configure Debian to get non-free packages:
```
echo "deb http://ftp.uk.debian.org/debian/ squeeze main non-free" >> /etc/apt/sources.list
echo "deb-src http://ftp.uk.debian.org/debian/ squeeze main non-free" >> /etc/apt/sources.list
echo "deb http://security.debian.org/ squeeze/updates main non-free" >> /etc/apt/sources.list
echo "deb-src http://security.debian.org/ squeeze/updates main non-free" >> /etc/apt/sources.list
```

Then update the packages list (that's right, you'll run the command twice):
```
apt-get update
apt-get update
```

Finally, get the non-free package:
```
apt-get install snmp-mibs-downloader
```

Edit snmp config:
```
vi /etc/snmp/snmp.conf
```
and remove line:
```
mibs
```