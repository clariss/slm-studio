new /etc/apt/sources.list
```
deb http://ftp.uk.debian.org/debian/ squeeze main
deb-src http://ftp.uk.debian.org/debian/ squeeze main

deb http://ftp.uk.debian.org/debian/ squeeze-updates main
deb-src http://ftp.uk.debian.org/debian/ squeeze-updates main

deb http://ftp.uk.debian.org/debian/ squeeze contrib non-free
deb-src http://ftp.uk.debian.org/debian/ squeeze contrib non-free


deb http://security.debian.org/ squeeze/updates main
deb-src http://security.debian.org/ squeeze/updates main

deb http://security.debian.org/ squeeze/updates contrib non-free
deb-src http://security.debian.org/ squeeze/updates contrib non-free
```

install fonts package
```
apt-get update
apt-get install msttcorefonts
```


wget https://lamp-ng.googlecode.com/files/logzilla_v2.9.9o.tgz

tar xzvf logzilla\_v2.9.9o.tgz

mv php-syslog-ng logzilla

mv logzilla /var/www

mkdir -p /var/log/logzilla

sudo cpan Text::LevenshteinXS

vi /etc/apache2/apache2.conf
ServerRoot "/etc/apache2" <<- Existing line
ServerName lamp-ng

```
vi /etc/apache2/sites-available/logzilla
# LogZilla
   Alias /logs "/var/www/logzilla/html/"
   <Directory "/var/www/logzilla/html/">
       Options Indexes MultiViews FollowSymLinks
       AllowOverride All
   Order allow,deny
   Allow from all
   </Directory>
```

a2ensite logzilla
/etc/init.d/apache2 reload
/etc/init.d/apache2 restart

```
sudo vi /etc/php5/apache2/php.ini
Change:
memory_limit = 16M 
to:
memory_limit = 128M 
Change:
max_execution_time = 30
to:
max_execution_time = 300
```
You should also do the same for /etc/php5/cli/php.ini

/etc/init.d/apache2 restart

chown -R www-data:www-data /var/www/logzilla/html
```
vi /etc/logrotate.d/logzilla
# http://nms.gdd.net/index.php/LogZilla_Installation_Guide#Logrotate
# LogZilla logrotate snippet for Ubuntu Linux
# contributed by Clayton Dukes
#
/var/log/logzilla/*.log {
  missingok
  compress
  rotate 5
  daily
  postrotate
  /etc/init.d/syslog-ng reload > /dev/null 2>&1 || true
  endscript
}
```

crontab -e
```
...
```

Test logzilla connect to MySQL:
```
printf "test\t190\tCRON\tTest\n" | /var/www/logzilla/scripts/db_insert.pl -d5 -v
```