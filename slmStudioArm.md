get Debian image (Debian 6, 16Gb disk)
```
wget http://www.downloadsnewit.co.uk/SD-images/Dreamplug/NewIT-Dreamplug-Debian-Squeeze/NewIT-Dreamplug-Debian-Squeeze-16Gb-30Aug11.img.gz
```

unzip and install Debian image
```
gunzip NewIT-Dreamplug-Debian-Squeeze-16Gb-30Aug11.img.gz
dd if=NewIT-Dreamplug-Debian-Squeeze-16Gb-30Aug11.img of=/dev/sdb bs=10M
```

install lamp-ng for Debian 6, download install script
```
wget http://lamp-ng.googlecode.com/svn/trunk/exe/install_v1_0.sh
```

execute install script
```
chmod +x install_v1_0.sh
. install_v1_0.shlamp-ng
```

fix MySQL ibdata1 default config, changing from 1 database file to 1 file per table.
```
vi /etc/mysql/my.cnf
```
add MySQL configuration so a tablespace file is created for each table. Find [mysqld](mysqld.md) in the file and add innodb\_file\_per\_table as below.
```
[mysqld]
innodb_file_per_table = 1
```
Restart MySQL server
```
/etc/init.d/mysql restart
```

Fix SNMP, get the non-free package:
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