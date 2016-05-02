
```
apt-get install mailutils postfix
```

When the installation process prompts you to define the type of mail setup you're running, select:
```
 "Internet Site"
```

You will also want to specify the machine specific hostname for this server during the installation process. When asked for "mail name" enter you web-address, for example:
```
slmstudio.dyndns.org
```

Next, you'll need to update the path to the mail binary in the Nagios command file. Change both references from /bin/mail to /usr/bin/mail.

```
vi /etc/nagios3/commands.cfg
```

the file should look like this:

```

# 'notify-host-by-email' command definition
define command{
        command_name    notify-host-by-email
        command_line    /usr/bin/printf "%b" "***** Nagios *****\n\nNotification Type: $NOTIFICATIONTYPE$\nHost: $HOSTNAME$\nState: $HOSTSTATE$\nAddress: $HOSTADDRESS$\nInfo: $HOSTOUTPUT$\n\nDate/Time: $LONGDATETIME$\n" 
| /usr/bin/mail -s "** $NOTIFICATIONTYPE$ Host Alert: $HOSTNAME$ is $HOSTSTATE$ **" $CONTACTEMAIL$
        }

# 'notify-service-by-email' command definition
define command{
        command_name    notify-service-by-email
        command_line    /usr/bin/printf "%b" "***** Nagios *****\n\nNotification Type: $NOTIFICATIONTYPE$\n\nService: $SERVICEDESC$\nHost: $HOSTALIAS$\nAddress: $HOSTADDRESS$\nState: $SERVICESTATE$\n\nDate/Time: $LONGDATETIME$\n\nAdditional Info:\n\n$SERVICEOUTPUT$" 
| /usr/bin/mail -s "** $NOTIFICATIONTYPE$ Service Alert: $HOSTALIAS$/$SERVICEDESC$ is $SERVICESTATE$ **" $CONTACTEMAIL$
        }
```

In order for these changes to take effect, you will need to restart Nagios:
```
/etc/init.d/nagios3 restart
```


Test email works from command line:/usr/bin/printf "%b" "Priority: Immediate\nStatus: New\n\n Noticication from command line" | /usr/bin/mail -s "Notification subjct" foo@gmail.com```