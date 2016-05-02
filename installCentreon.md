
```
wget http://download.centreon.com/centreon/centreon-2.3.1.tar.gz

tar xzf centreon-2.3.1.tar.gz

cd centreon-2.3.1

./install.sh -i

------------------------------------------------------------------------
        Please choose what you want to install
------------------------------------------------------------------------

Do you want to install : Centreon Web Front
[y/n], default to [n]:
> y

Do you want to install : Centreon CentCore
[y/n], default to [n]:
> y

Do you want to install : Centreon Nagios Plugins
[y/n], default to [n]:
> y

Do you want to install : Centreon Snmp Traps process
[y/n], default to [n]:
> y

------------------------------------------------------------------------
        Start CentWeb Installation
------------------------------------------------------------------------
Where is your Centreon directory?
default to [/usr/local/centreon]
>

Do you want me to create this directory ? [/usr/local/centreon]
[y/n], default to [n]:
> y
Path /usr/local/centreon                                   OK

Where is your Centreon log directory
default to [/usr/local/centreon/log]
> /var/log/centreon

Do you want me to create this directory ? [/var/log/centreon]
[y/n], default to [n]:
> y
Path /var/log/centreon                                     OK

Where is your Centreon etc directory
default to [/etc/centreon]
>

Do you want me to create this directory ? [/etc/centreon]
[y/n], default to [n]:
> y
Path /etc/centreon                                         OK

Where is your Centreon generation_files directory?
default to [/usr/local/centreon]
>
Path /usr/local/centreon                                   OK

Where is your Centreon variable library directory?
default to [/var/lib/centreon]
>

Do you want me to create this directory ? [/var/lib/centreon]
[y/n], default to [n]:
> y
Path /var/lib/centreon                                     OK

Where is your CentPlugins Traps binary
default to [/usr/local/centreon/bin]
>

Do you want me to create this directory ? [/usr/local/centreon/bin]
[y/n], default to [n]:
> y
Path /usr/local/centreon/bin                               OK

Where is the RRD perl module installed [RRDs.pm]
default to [/usr/lib/perl5/RRDs.pm]
>
Path /usr/lib/perl5                                        OK
/usr/bin/rrdtool                                           OK
/usr/bin/mail                                              OK

Where is PEAR [PEAR.php]
default to [/usr/share/php/PEAR.php]
>
Path /usr/share/php                                        OK

Where is installed Nagios ?
default to [/usr/local/nagios]
> /usr/lib/cgi-bin/nagios3
Path /usr/lib/cgi-bin/nagios3                              OK

Where is your nagios config directory
default to [/usr/local/nagios/etc]
> /etc/nagios3
Path /etc/nagios3                                          OK

Where is your Nagios var directory ?
default to [/usr/local/nagios/var]
> /var/lib/nagios3
Path /var/lib/nagios3                                      OK

Where is your Nagios plugins (libexec) directory ?
default to [/usr/local/nagios/libexec]
> /usr/lib/nagios/plugins
Path /usr/lib/nagios/plugins                               OK
/usr/sbin/nagios3                                          OK

Where is your Nagios image directory ?
default to [/usr/local/nagios/share/images/logos]
> /usr/share/nagios/htdocs/images/logos
Path /usr/share/nagios/htdocs/images/logos                 OK

Where is your NDO ndomod binary ?
default to [/usr/sbin/ndomod.o]
> /usr/lib/ndoutils/ndomod-mysql-3x.o
/usr/lib/ndoutils/ndomod-mysql-3x.o

/usr/sbin/nagios3stats                                     OK
p1_file : /usr/lib/nagios3/p1.pl                           OK
/usr/bin/php                                               OK
/usr/bin/perl                                              OK
Finding Apache group :                                     www-data
Finding Apache user :                                      www-data
Finding Nagios user :                                      nagios
Finding Nagios group :                                     nagios

Where is your NDO ndomod binary ?
default to [/usr/sbin/ndomod.o]
> /usr/lib/ndoutils/ndomod-mysql-3x.o
/usr/lib/ndoutils/ndomod-mysql-3x.o                        OK

------------------------------------------------------------------------
        Configure Sudo
------------------------------------------------------------------------

Where is sudo configuration file
default to [/etc/sudoers]
>
/etc/sudoers                                               OK
Nagios init script                                         OK
Your sudo is not configured

Do you want me to configure your sudo ? (WARNING)
[y/n], default to [n]:
> y
Configuring Sudo                                           OK

------------------------------------------------------------------------
        Configure Apache server
------------------------------------------------------------------------

Do you want to add Centreon Apache sub configuration file ?
[y/n], default to [n]:
> y
Create '/etc/apache2/conf.d/centreon.conf'                 OK
Configuring Apache                                         OK

Do you want to reload your Apache ?
[y/n], default to [n]:
> y
Reloading Apache service                                   OK
Preparing Centreon temporary files
Change right on /var/log/centreon                          OK
Change right on /etc/centreon                              OK
Change right on /usr/share/nagios/htdocs/images/logos      OK
Install nagios documentation                               OK
Change macros for insertBaseConf.sql                       OK
Change macros for php files                                OK
Change right on /etc/nagios3                               OK
Copy CentWeb in system directory
Install CentWeb (web front of centreon)                    OK
Install libraries                                          OK
Copying libinstall                                         OK
Change macros for centreon.cron                            OK
Install Centreon cron.d file                               OK
Change macros for centAcl.php                              OK
Change macros for downtimeManager.php                      OK
Change macros for eventReportBuilder.pl                    OK
Change macros for dashboardBuilder.pl                      OK
Install cron directory                                     OK
Change right for eventReportBuilder.pl                     OK
Change right for dashboardBuilder.pl                       OK

------------------------------------------------------------------------
Pear Modules
------------------------------------------------------------------------
Check PEAR modules
PEAR                            1.4.9       1.9.1          OK
DB                              1.7.6                      NOK
DB_DataObject                   1.8.4                      NOK
DB_DataObject_FormBuilder       1.0.0RC4                   NOK
MDB2                            2.0.0                      NOK
Date                            1.4.6                      NOK
HTML_Common                     1.2.2                      NOK
HTML_QuickForm                  3.2.5                      NOK
HTML_QuickForm_advmultiselect   1.1.0                      NOK
HTML_Table                      1.6.1                      NOK
Archive_Tar                     1.1         1.3.7          OK
Auth_SASL                       1.0.1                      NOK
Console_Getopt                  1.2         1.2.3          OK
Net_SMTP                        1.2.8                      NOK
Net_Socket                      1.0.1                      NOK
Net_Traceroute                  0.21                       NOK
Net_Ping                        2.4.1                      NOK
Validate                        0.6.2                      NOK
XML_RPC                         1.4.5                      NOK
SOAP                            0.10.1                     NOK
Log                             1.9.11                     NOK

Do you want me to install/upgrade your PEAR modules
[y/n], default to [y]:
> y
Upgrading PEAR modules
Installing PEAR modules
DB                              1.7.6       1.7.14         OK
DB_DataObject                   1.8.4       1.9.6          OK
DB_DataObject_FormBuilder       1.0.0RC4    1.0.1          OK
MDB2                            2.0.0       2.4.1          OK
HTML_QuickForm_advmultiselect   1.1.0       1.5.1          OK
HTML_Table                      1.6.1       1.8.3          OK
Auth_SASL                       1.0.1       1.0.6          OK
Net_SMTP                        1.2.8       1.6.1          OK
Net_Traceroute                  0.21        0.21.3         OK
Net_Ping                        2.4.1       2.4.5          OK
Validate                        0.6.2       0.8.4          OK
XML_RPC                         1.4.5       1.5.5          OK
SOAP                            0.10.1      0.12.0         OK
Log                             1.9.11      1.12.7         OK
Check PEAR modules
PEAR                            1.4.9       1.9.4          OK
DB                              1.7.6       1.7.14         OK
DB_DataObject                   1.8.4       1.9.6          OK
DB_DataObject_FormBuilder       1.0.0RC4    1.0.1          OK
MDB2                            2.0.0       2.4.1          OK
Date                            1.4.6       1.4.7          OK
HTML_Common                     1.2.2       1.2.5          OK
HTML_QuickForm                  3.2.5       3.2.13         OK
HTML_QuickForm_advmultiselect   1.1.0       1.5.1          OK
HTML_Table                      1.6.1       1.8.3          OK
Archive_Tar                     1.1         1.3.7          OK
Auth_SASL                       1.0.1       1.0.6          OK
Console_Getopt                  1.2         1.2.3          OK
Net_SMTP                        1.2.8       1.6.1          OK
Net_Socket                      1.0.1       1.0.10         OK
Net_Traceroute                  0.21        0.21.3         OK
Net_Ping                        2.4.1       2.4.5          OK
Validate                        0.6.2       0.8.4          OK
XML_RPC                         1.4.5       1.5.5          OK
SOAP                            0.10.1      0.12.0         OK
Log                             1.9.11      1.12.7         OK
All PEAR modules                                           OK


**** XML_RPC is deprecated ****
install new version to resolve the issue
sudo pear install XML_RPC2


------------------------------------------------------------------------
                Centreon Post Install
------------------------------------------------------------------------
Create /usr/local/centreon/www/install/install.conf.php    OK
Create /etc/centreon/instCentWeb.conf                      OK

------------------------------------------------------------------------
        Start CentStorage Installation
------------------------------------------------------------------------


Where is your Centreon Run Dir directory?
default to [/var/run/centreon]
>

Do you want me to create this directory ? [/var/run/centreon]
[y/n], default to [n]:
> y
Path /var/run/centreon                                     OK

Where is your CentStorage binary directory
default to [/usr/local/centreon/bin]
>
Path /usr/local/centreon/bin                               OK

Where is your CentStorage RRD directory
default to [/var/lib/centreon]
>
Path /var/lib/centreon                                     OK
Finding Nagios group :                                     nagios
Finding Nagios user :                                      nagios
Preparing Centreon temporary files
/tmp/centreon-setup exists, it will be moved...
install www/install/createTablesCentstorage.sql            OK
Creating Centreon Directory '/var/lib/centreon/status'     OK
Creating Centreon Directory '/var/lib/centreon/metrics'    OK
Change macros for centstorage binary                       OK
Install CentStorage binary                                 OK
Install library for centstorage                            OK
Change right : /var/run/centreon                           OK
Change macros for centstorage init script                  OK

Do you want me to install CentStorage init script ?
[y/n], default to [n]:
> y
CentStorage init script installed                          OK

Do you want me to install CentStorage run level ?
[y/n], default to [n]:
> y
update-rc.d: using dependency based boot sequencing
Configuration file /etc/centreon/conf.pm not found.  Exiting.
CentStorage stop                                           FAIL
Change macros for logAnalyser                              OK
Install logAnalyser                                        OK
Change macros for nagiosPerfTrace                          OK
Install nagiosPerfTrace                                    OK
Change macros for purgeLogs                                OK
Install purgeLogs                                          OK
Change macros for purgeCentstorage                         OK
Install purgeCentstorage                                   OK
Change macros for centreonPurge.sh                         OK
Install centreonPurge.sh                                   OK
Change macros for centstorage.cron                         OK
Install CentStorage cron                                   OK
Create /etc/centreon/instCentStorage.conf                  OK

------------------------------------------------------------------------
        Start CentCore Installation
------------------------------------------------------------------------

Where is your CentCore binary directory
default to [/usr/local/centreon/bin]
>
Path /usr/local/centreon/bin                               OK
/usr/bin/ssh                                               OK
/usr/bin/scp                                               OK
Finding Nagios group :                                     nagios
Finding Nagios user :                                      nagios
Preparing Centreon temporary files
/tmp/centreon-setup exists, it will be moved...
Change CentCore Macro                                      OK
Copy CentCore in binary directory                          OK
Change right : /var/run/centreon                           OK
Change right : /var/lib/centreon                           OK
Replace CentCore init script Macro                         OK

Do you want me to install CentCore init script ?
[y/n], default to [n]:
> y
CentCore init script installed                             OK

Do you want me to install CentCore run level ?
[y/n], default to [n]:
> y
update-rc.d: using dependency based boot sequencing
Create /etc/centreon/instCentCore.conf                     OK

------------------------------------------------------------------------
        Start CentPlugins Installation
------------------------------------------------------------------------

Where is your CentPlugins lib directory
default to [/var/lib/centreon/centplugins]
>

Do you want me to create this directory ? [/var/lib/centreon/centplugins]
[y/n], default to [n]:
> y
Path /var/lib/centreon/centplugins                         OK
Finding Nagios user :                                      nagios
Finding Nagios group :                                     nagios
Preparing Centreon temporary files
/tmp/centreon-setup exists, it will be moved...
Change macros for CentPlugins                              OK
Installing the plugins                                     OK
Change right on centreon.conf                              OK
CentPlugins is installed

------------------------------------------------------------------------
        Start CentPlugins Traps Installation
------------------------------------------------------------------------

Where is your SNMP configuration directory
default to [/etc/snmp]
>
/etc/snmp                                                  OK

Where is your SNMPTT binaries directory
default to [/usr/local/centreon/bin/]
>
/usr/local/centreon/bin/                                   OK
Finding Nagios group :                                     nagios
Finding Apache user :                                      www-data
Preparing Centreon temporary files
/tmp/centreon-setup exists, it will be moved...
Change macros for CentPluginsTraps                         OK
Installing the plugins Trap binaries                       OK
Change macros for snmptrapd.conf                           OK
Change macros for snmptt.ini                               OK
Install : snmptrapd.conf                                   OK
Install : snmp.conf                                        OK
Install : snmptt.ini                                       OK
Install : snmptt                                           OK
Install : snmpttconvertmib                                 OK
Create /etc/centreon/instCentPlugins.conf                  OK
#####################################################################
#                                                                   #
#        Go to the URL : http://debian/centreon/                    #
#                  to finish the setup                              #
#                                                                   #
#        Report bugs at http://forge.centreon.com                   #
#                                                                   #
#               Thanks for using Centreon.                          #
#                -----------------------                            #
#              Contact : infos@centreon.com                         #
#                http://www.centreon.com                            #
#                                                                   #
#####################################################################





update-rc.d ndoutils defaults

/etc/init.d/ndoutils start

update-rc.d centstorage defaults

/etc/init.d/centstorage start

```